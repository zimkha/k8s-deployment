### Core concepts

# Create a namespace called 'mynamespace' and a pod with image nginx called nginx on this namespace

create namespace: kubectl create ns mynamespace
create pod with namespace: kubectl run nginx --image =nginx -n=mynamespace
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