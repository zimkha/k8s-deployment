### Persistent Volume with too container

#command. Make both containers mount an emptyDir at '/etc/foo'. Connect to the second busybox,
#write the first column of '/etc/passwd' file to '/etc/foo/passwd'.
#Connect to the first busybox and write '/etc/foo/passwd' file to standard output. Delete pod


### Create busybox pod with two containers, each one will have the image busybox and will run the 'sleep 3600' commande
### run command

<p> 

````bash
kubectl run container-1 --image=busybox --restartPolicy=Never -o yaml --dry-run=client -- /bin/sh -c 'sleep 3600' > mypod.yaml

````
### And edit the pod definition to add a new container with the same specifications 
### You can check the file multi-container.yaml 
### So we have multipl ways to run sh command in the container (check the multi-container.yaml for the first)
### second way

````yaml
containers:
  - name: container-name
    image: busybox
    command: ["/bin/sh", "-c", "sleep 3600"]
````
</p>

### connect to one container
````bash

kubectl exec -it busybox -c container-2 -- /bin/sh
cat /etc/passwd | cut -f 1 -d ':' > /etc/foo/passwd
cat /etc/foo/passwd

````

````bash
kubectl exec -it busybox -c container-2 -- /bin/sh
mount | grep foo 
cat /etc/foo/passwd

````


