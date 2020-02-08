# secret

```yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    name: webapp-pod
  name: webapp-pod
  selfLink: /api/v1/namespaces/default/pods/webapp-pod
spec:
  containers:
  - image: kodekloud/simple-webapp-mysql
    imagePullPolicy: Always
    envFrom:
    - secretRef:
        name: db-secret
    name: webapp
```
