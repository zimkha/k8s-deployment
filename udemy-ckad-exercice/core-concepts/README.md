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
<details>
<summary> Solution </summary>
```
  kubectl run busybox --image=busybox --command --restartPolicy=Never --env

  kubectl run busybox --image=busybox --command --restart=Never -it --rm -- env # Pour voir les output
  kubectl logs busybox
```
  </details>