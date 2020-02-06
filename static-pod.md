# Static Pod

Run the command `ps -aux | grep kubelet` and identify the config file - `--config=/var/lib/kubelet/config.yaml`. Then checkin the config file for staticPdPath.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: static-busybox
spec:
  containers:
  - name: busybox
    image: busybox
    command: ["sleep"]
    args: ["1000"]
```
