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
