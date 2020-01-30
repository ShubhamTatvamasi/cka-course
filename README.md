# cka-course

Check `kube-apiserver` on master node inside your cluster
```bash
ps -aux | grep kube-apiserver
```

```bash
ps -aux | grep kube-controller-manager
```

Localtion for cluster configs
```bash
ls /etc/kubernetes/manifests
addon-manager.yaml.tmpl  etcd.yaml  kube-apiserver.yaml  kube-controller-manager.yaml  kube-scheduler.yaml
```
