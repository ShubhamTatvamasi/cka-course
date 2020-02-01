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
Readiness and Liveness Probes | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-readiness-probe/
Labels & Selectors | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-labels-selectors/
Taints and Tolerations | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-taints-tolerations/
Logging | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-logging/
Node Affinity | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-node-affinity/
Resource Limits | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-resource-limits/
DaemonSets |
Static PODs |
Multiple Schedulers |
Monitor Cluster Components |
Managing Application Logs |
Rolling Updates and Rollbacks |
Commands and Arguments |
Env Variables |
Secrets | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-secrets/
Multi-Container Pods | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-multi-container-pods/
Init Containers |
OS Upgrades |
Cluster Upgrade Process |
Backup and Restore Methods |
View Certificate Details |
Certificates API |
KubeConfig |
Role Based Access Controls |
Cluster Roles |
Image Security |
Security Contexts | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-security-contexts/
Network Policies | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-network-policies/
Persistent Volume Claims |
Explore Environment |
Explore CNI Weave 1 |
Explore CNI Weave 2 |
Deploy Network Solution |
Networking Weave |
Service Networking |
CoreDNS in Kubernetes |
CKA - Ingress Networking - 1 |
CKA - Ingress Networking - 2 |
Cluster Installation using kubeadm |
Application Failure |
Control Plane Failure |
Worker Node Failure |
Advanced Kubectl Commands |



