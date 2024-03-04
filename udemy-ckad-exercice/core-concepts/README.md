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
### Get the YAML for a new namespace called 'myns' without creating it

<details><summary>show</summary>
<p>

````bash
 # type this command on your terminal 
 kubectl create namespace myns -o yaml --dry-run=client > new-ns.yaml
 # cat new-ns.yaml for seeing the out put
 # Or, type this command for seeing on the console the output without save this on a yaml file
 kubectl create namespace myns -o yaml --dry-run=client
````
</p>
</details>

### Create the YAML for a new ResourceQuota called 'myrq' with hard limits of 1 CPU, 1G memory and 2 pods without creating it

<details><summary>show</summary>
<p>

````bash
kubectl create quota myrq --hard=cpu=1,memory=1G,pods=2 --dry-run=client -o yaml

````
</p>
</details>


### Get pods on all namespaces

<details><summary>show</summary>
<p>

````bash
kubectl get pods --all-namespace
````
</p>

</details>

### Create a pod with image nginx called nginx and expose traffic on port 80

<details>

#### see these files pod-nginx.yaml and service-nginx.yaml or
```` bash
kubectl run nginx --image=nginx --restart=Never --port=80

````
</details>

