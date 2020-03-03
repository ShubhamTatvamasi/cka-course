# exam


## CKA Mock Exam - 2

### Take a backup of the etcd cluster and save it to /tmp/etcd-backup.db

check the etcd version
```bash
ETCDCTL_API=3 etcdctl version
```

move to the manifests folder
```bash
cd /etc/kubernetes/manifests
```

check the etcd command working
```bash
ETCDCTL_API=3 etcdctl \
  --endpoints=https://172.17.0.41:2379 \
  --cacert="/etc/kubernetes/pki/etcd/ca.crt" \
  --cert="/etc/kubernetes/pki/etcd/server.crt" \
  --key="/etc/kubernetes/pki/etcd/server.key" \
  member list
```

take backup
```bash
ETCDCTL_API=3 etcdctl \
  --endpoints=https://172.17.0.41:2379 \
  --cacert="/etc/kubernetes/pki/etcd/ca.crt" \
  --cert="/etc/kubernetes/pki/etcd/server.crt" \
  --key="/etc/kubernetes/pki/etcd/server.key" \
  snapshot save /tmp/etcd-backup.db
```

verify backup
```bash
ETCDCTL_API=3 etcdctl \
  --endpoints=https://172.17.0.41:2379 \
  --cacert="/etc/kubernetes/pki/etcd/ca.crt" \
  --cert="/etc/kubernetes/pki/etcd/server.crt" \
  --key="/etc/kubernetes/pki/etcd/server.key" \
  snapshot status /tmp/etcd-backup.db -w table
```


