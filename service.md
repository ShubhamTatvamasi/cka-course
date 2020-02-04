### Service

create service yaml template
```bash
kubectl expose deploy webapp --name webapp-service --port=8080 --type=NodePort
kubectl create service nodeport webapp-service --tcp=8080:8080 --node-port=30080 --dry-run -o yaml
```
