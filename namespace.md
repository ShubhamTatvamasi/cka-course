### Namespace

Change the default namespace
```
kubectl config get-contexts
kubectl config set-context $(kubectl config current-context) --namespace=dev
```
