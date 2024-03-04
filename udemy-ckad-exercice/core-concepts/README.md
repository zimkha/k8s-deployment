# Core concepts

### Create a namespace called 'mynamespace' and a pod with image nginx called nginx on this namespace

create namespace: kubectl create ns mynamespace
create pod with namespace: kubectl run nginx --image =nginx -n=mynamespace

### Create the pod that was just described using YAML
``` yaml
apiVersion: v1
kind: Pod
metadata: 
  name: nginx
spec:
  containers:
    - name: mypod
      image: nginx
  restartPolicy: Always
```

### Create a busybox pod (using kubectl command) that runs the command "env". Run it and see the output
<details><summary>show</summary>
<p>

```bash
# just run it without -it
kubectl run busybox --image=busybox --command --restart=Never -- env
# and then, check its logs
kubectl logs busybox
```
</p>
</details>

### Create the pod that was just described using YAML
<details><summary>show</summary>
 <p>

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: busybox
  labels:
    run: busybox
spec:
  containers:
    - name: busybox
      image: nginx
      command:
      - env
  restartPolicy: Never
  dnsPolicy: ClusterFirst
status: {}
```
</p>
</details>

