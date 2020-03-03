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

### Create a new pod called super-user-pod with image busybox:1.28. Allow the pod to be able to set system_time

```bash
kubectl run super-user-pod --restart=Never --image=busybox:1.28 --dry-run -o yaml --command -- sleep 4800
```
```yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: super-user-pod
  name: super-user-pod
spec:
  containers:
  - command:
    - sleep
    - "4800"
    image: busybox:1.28
    securityContext:
      capabilities:
        add: ["SYS_TIME"]
    name: super-user-pod
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Never
status: {}
```

### A pod definition file is created at /root/use-pv.yaml. Make use of this manifest file and mount the persistent volume called pv-1. Ensure the pod is running and the PV is bound.

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pv-1
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Mi
```

```yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: use-pv
  name: use-pv
spec:
  containers:
  - image: nginx
    name: use-pv
    resources: {}
    volumeMounts:
    - mountPath: "/data"
      name: my-pvc
  volumes:
    - name: my-pvc
      persistentVolumeClaim:
        claimName: pv-1
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

### Create a new deployment called nginx-deploy, with image nginx:1.16 and 1 replica. Record the version. Next upgrade the deployment to version 1.17 using rolling update. Make sure that the version upgrade is recorded in the resource annotation.


```bash
kubectl run nginx-deploy --image=nginx:1.16
```
```bash
kubectl set image deploy nginx-deploy nginx-deploy=nginx:1.17
```

### Create a new user called john. Grant him access to the cluster. John should have permission to create, list, get, update and delete pods in the development namespace . The private key exists in the location: /root/john.key and csr at /root/john.csr

```bash
kubectl create role developer --verb=create,list,get,update,delete --resource=pods --namespace=development
```

```
kubectl create rolebinding john-developer --user=john --role=developer --namespace=development
```








