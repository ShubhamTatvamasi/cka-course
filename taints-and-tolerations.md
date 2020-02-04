### Taints and Tolerations

Check the taint on master node
```bash
kubectl describe node master | grep Taints
```

Create a taint on node01 with key of `spray`, value of `mortein` and effect of `NoSchedule`
```bash
kubectl taint nodes node01 spray=mortein:NoSchedule
```

Create another pod named `bee` with the NGINX image, which has a toleration set to the taint Mortein
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: bee
spec:
  containers:
  - image: nginx
    name: bee
  tolerations:
  - key: spray
    value: mortein
    effect: NoSchedule
    operator: Equal
```
