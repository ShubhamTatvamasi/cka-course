# cka-course

Check cluster operations on master node inside your cluster
```bash
ps -aux | grep kube-apiserver
ps -aux | grep kube-controller-manager
ps -aux | grep kube-scheduler
```

Localtion for cluster configs
```bash
ls /etc/kubernetes/manifests
addon-manager.yaml.tmpl  etcd.yaml  kube-apiserver.yaml  kube-controller-manager.yaml  kube-scheduler.yaml
```
---

### Practice Test

[Pods](https://katacoda.com/embed/mmumshad2/kubernetes-ckad-pods/)

[ReplicaSets](https://katacoda.com/embed/mmumshad2/kubernetes-ckad-replicasets/)

[Deployment](https://katacoda.com/embed/mmumshad2/kubernetes-ckad-deployment/)

---
