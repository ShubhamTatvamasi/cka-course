# metrics-server

deploy on minikube
```bash
minikube addons enable metrics-server
```

clone metrics-server repo
```bassh
git clone https://github.com/kubernetes-incubator/metrics-server.git
```

deploy on k8s cluster
```
kubectl create –f deploy/1.8+/
```
