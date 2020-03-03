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

### Create a Pod called redis-storage with image: redis:alpine with a Volume of type emptyDir that lasts for the life of the Pod. Specs on the right.

```bash
kubectl run redis-storage --restart=Never --image=redis:alpine --dry-run -o yaml
```
```yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: redis-storage
  name: redis-storage
spec:
  containers:
  - image: redis:alpine
    name: redis-storage
    resources: {}
    volumeMounts:
    - mountPath: /data/redis
      name: redis-storage
  volumes:
  - name: redis-storage
    emptyDir: {}    
  dnsPolicy: ClusterFirst
  restartPolicy: Never
status: {}
```

