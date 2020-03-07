# CKA Mock Exam - 3

### Create a new service account with the name pvviewer. Grant this Service account access to list all PersistentVolumes in the cluster by creating an appropriate cluster role called pvviewer-role and ClusterRoleBinding called pvviewer-role-binding.

create a service account
```bash
kubectl create serviceaccount pvviewer
```

```bash
kubectl create clusterrole pvviewer-role --verb=list --resource=pv
```

```bash
kubectl create clusterrolebinding pvviewer-role-binding --clusterrole=pvviewer-role --serviceaccount=default:pvviewer
```

```bash
kubectl run pvviewer --restart=Never --image=redis --serviceaccount=pvviewer
```

### List the InternalIP of all nodes of the cluster. Save the result to a file /root/node_ips

```bash
kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="InternalIP")].address}' > /root/node_ips
```

### Create a pod called multi-pod with two containers. Container 1, name: alpha, image: nginx. Container 2: beta, image: busybox, command sleep 4800.

```bash
kubectl run alpha --restart=Never --image=nginx --dry-run -o yaml > alpha.yaml
kubectl run beta --restart=Never --image=busybox --dry-run -o yaml --command -- sleep 4800 > beta.yaml
```
```
cat << EOF | kubectl apply -f -
apiVersion: v1
kind: Pod
metadata:
  labels:
    run: multi-pod
  name: multi-pod
spec:
  containers:
  - command:
    - sleep
    - "4800"
    image: busybox
    name: beta
  - image: nginx
    name: alpha
EOF
```





