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

[Practice Test - Pods](https://kodekloud.com/courses/certified-kubernetes-administrator-with-practice-tests-labs/lectures/12038860)

[Practice Test - ReplicaSets](https://kodekloud.com/courses/kubernetes-certification-course/lectures/6743646)
