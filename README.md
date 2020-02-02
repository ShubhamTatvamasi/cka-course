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
Services | https://katacoda.com/embed/mmumshad2/kubernetes-for-beginners-services/
Imperative Commands | https://katacoda.com/embed/mmumshad2/kubernetes-cka-imperative-1/
Manual Scheduling | https://katacoda.com/embed/mmumshad2/kubernetes-cka-scheduler-manual/
Readiness and Liveness Probes | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-readiness-probe/
Labels & Selectors | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-labels-selectors/
Taints and Tolerations | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-taints-tolerations/
Node Affinity | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-node-affinity/
Resource Limits | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-resource-limits/
Service Account | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-serviceaccounts/
DaemonSets | https://katacoda.com/embed/mmumshad2/kubernetes-cka-scheduler-daemonset/
Static PODs | https://katacoda.com/embed/mmumshad2/kubernetes-cka-scheduler-staticpods/
Multiple Schedulers | https://katacoda.com/embed/mmumshad2/kubernetes-cka-scheduler-multiple/
Monitor Cluster Components | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-monitoring/
Managing Application Logs | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-logging/
Rolling Updates and Rollbacks | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-rolling-rollbacks-updates/
Commands and Arguments | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-commands-args/
ConfigMaps | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-env-vars/
Env Variables | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-env-vars/
Secrets | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-secrets/
Multi-Container Pods | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-multi-container-pods/
Init Containers | https://katacoda.com/embed/mmumshad2/kubernetes-cka-init-containers/
OS Upgrades | https://katacoda.com/embed/mmumshad2/kubernetes-cka-cluster-maintenance-node/
Cluster Upgrade Process | https://katacoda.com/embed/mmumshad2/kubernetes-cka-cluster-upgrade/
Backup and Restore Methods | https://katacoda.com/embed/mmumshad2/kubernetes-cka-backup-etcd/
View Certificate Details | https://katacoda.com/embed/mmumshad2/kubernetes-cka-security-tls-1-read-certs/
Certificates API | https://katacoda.com/embed/mmumshad2/kubernetes-cka-security-certificates-api/
KubeConfig | https://katacoda.com/embed/mmumshad2/kubernetes-cka-security-kubeconfig/
Role Based Access Controls | https://katacoda.com/embed/mmumshad2/kubernetes-cka-security-authorization-rbac/
Cluster Roles | https://katacoda.com/embed/mmumshad2/kubernetes-cka-security-authorization-clusterroles/
Image Security | https://katacoda.com/embed/mmumshad2/kubernetes-cka-security-image-security/
Security Contexts | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-security-contexts/
Network Policies | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-network-policies/
Persistent Volume Claims | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-persistent-volumes/
Explore Environment | https://katacoda.com/embed/mmumshad2/kubernetes-cka-networking-10-read-env/
Explore CNI Weave 1 | https://katacoda.com/embed/mmumshad2/kubernetes-cka-networking-20-cni-read-weave/
Explore CNI Weave 2 | https://katacoda.com/embed/mmumshad2/kubernetes-cka-networking-30-read-weave-2/
Deploy Network Solution | https://katacoda.com/embed/mmumshad2/kubernetes-cka-networking-35-deploy-weave/
Networking Weave | https://katacoda.com/embed/mmumshad2/kubernetes-cka-networking-30-read-weave-2/
Service Networking | https://katacoda.com/embed/mmumshad2/kubernetes-cka-networking-50-service-networking/
CoreDNS in Kubernetes | https://katacoda.com/embed/mmumshad2/kubernetes-cka-networking-40-read-dns/
CKA - Ingress Networking - 1 | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-ingress/
CKA - Ingress Networking - 2 | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-ingress-2-deploy-controller/
Cluster Installation using kubeadm | https://katacoda.com/embed/mmumshad2/kubernetes-cka-cluster-install/
Application Failure | https://katacoda.com/embed/mmumshad2/kubernetes-cka-troubleshooting-app-1/
Control Plane Failure | https://katacoda.com/embed/mmumshad2/kubernetes-cka-troubleshooting-cluster-1/
Worker Node Failure | https://katacoda.com/embed/mmumshad2/kubernetes-cka-troubleshooting-worker-1/
Advanced Kubectl Commands | https://katacoda.com/embed/mmumshad2/kubernetes-cka-kubectl-advanced/
Kubernetes Challenge - Wordpress | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-challenge-1-wordpress/
CKAD Practice Exam - 1 | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-exam-1/
CKAD Practice Exam - 2 | https://katacoda.com/embed/mmumshad2/kubernetes-ckad-exam-2/
CKA Practice Exam - 1 | https://katacoda.com/embed/mmumshad2/kubernetes-cka-exam-1/
CKA Practice Exam - 2 | https://katacoda.com/embed/mmumshad2/kubernetes-cka-exam-2/
CKA Practice Exam - 3 | https://katacoda.com/embed/mmumshad2/kubernetes-cka-exam-3/

Reference: https://katacoda.com/mmumshad2/

