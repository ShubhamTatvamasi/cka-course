# etcd

Backup
```bash
ETCDCTL_API=3 etcdctl --endpoints=https://[127.0.0.1]:2379 --cacert=/etc/kubernetes/pki/etcd/ca.crt \
     --cert=/etc/kubernetes/pki/etcd/server.crt --key=/etc/kubernetes/pki/etcd/server.key \
     snapshot save /tmp/snapshot-pre-boot.db
```

Restore
```bash
ETCDCTL_API=3 etcdctl --endpoints=https://[127.0.0.1]:2379 --cacert=/etc/kubernetes/pki/etcd/ca.crt \
     --name=master \
     --cert=/etc/kubernetes/pki/etcd/server.crt --key=/etc/kubernetes/pki/etcd/server.key \
     --data-dir /var/lib/etcd-from-backup \
     --initial-cluster=master=https://127.0.0.1:2380 \
     --initial-cluster-token etcd-cluster-1 \
     --initial-advertise-peer-urls=https://127.0.0.1:2380 \
     snapshot restore /tmp/snapshot-pre-boot.db
```

### Modify /etc/kubernetes/manifests/etcd.yaml

Update ETCD POD to use the new data directory and cluster token by modifying the pod definition file at `/etc/kubernetes/manifests/etcd.yaml`. When this file is updated, the ETCD pod is automatically re-created as thisis a static pod placed under the `/etc/kubernetes/manifests` directory.

Update --data-dir to use new target location

```
--data-dir=/var/lib/etcd-from-backup
```

Update new initial-cluster-token to specify new cluster

```
--initial-cluster-token=etcd-cluster-1
```

Update volumes and volume mounts to point to new path

```
    volumeMounts:
    - mountPath: /var/lib/etcd-from-backup
      name: etcd-data
    - mountPath: /etc/kubernetes/pki/etcd
      name: etcd-certs
  hostNetwork: true
  priorityClassName: system-cluster-critical
  volumes:
  - hostPath:
      path: /var/lib/etcd-from-backup
      type: DirectoryOrCreate
    name: etcd-data
  - hostPath:
      path: /etc/kubernetes/pki/etcd
      type: DirectoryOrCreate
    name: etcd-certs
```
---

### Other commands

```bash
etcdctl backup --data-dir /var/lib/etcd --backup-dir /tmp/snapshot-pre-boot.db
```

```bash
ETCDCTL_API=3 etcdctl snapshot save snapshot.db
```

```bash
ETCDCTL_API=3 etcdctl snapshot status snapshot.db
```

```bash
service kube-apiserver stop
```

```bash
ETCDCTL_API=3 etcdctl snapshot restore snapshot.db
```
