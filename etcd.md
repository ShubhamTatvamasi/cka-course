# etcd

```bash
etcdctl snapshot save snapshot.db
```

```bash
etcdctl snapshot status snapshot.db
```

```bash
service kube-apiserver stop
```

```bash
etcdctl snapshot restore snapshot.db
```
