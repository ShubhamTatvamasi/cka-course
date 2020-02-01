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

[Practice Tests List](https://kodekloud.com/courses/certified-kubernetes-administrator-with-practice-tests-labs/lectures/12038860)

Resource | Practice Exam Link 
--- | --- 
Pods | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-pods/
ReplicaSets | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-replicasets/
Deployments | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-deployments/
Namespaces | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-namespaces/
Services |
Imperative Commands |
Manual Scheduling |
Labels & Selectors | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-labels-selectors/
Taints and Tolerations | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-taints-tolerations/
Node Affinity | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-node-affinity/
Resource Limits | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-resource-limits/
DaemonSets |
Static PODs |
Multiple Schedulers |
Security Contexts | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-security-contexts/
Secrets | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-secrets/

