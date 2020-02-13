# rbac

check `--authorization-mode`
```bash
kubectl get pod kube-apiserver-master -n kube-system -o yaml
kubectl get pod kube-apiserver-master -n kube-system -o jsonpath={.spec.containers[0].command}
```

Get list of roles
```bash
kubectl get roles
```


