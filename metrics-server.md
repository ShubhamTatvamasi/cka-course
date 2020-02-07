# metrics-server

deploy on minikube
```bash
minikube addons enable metrics-server
```

clone metrics-server repo
```bash
git clone https://github.com/kubernetes-incubator/metrics-server.git
```

deploy on k8s cluster
```bash
kubectl create –f deploy/1.8+/
```

check node and pod resource consumption
```bash
kubectl top node
kubectl top pod
```
