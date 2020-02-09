# etcd

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
