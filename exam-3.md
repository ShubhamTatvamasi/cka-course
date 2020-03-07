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

