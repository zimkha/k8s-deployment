# PREPARATION CKAD EXAMEN
 Ce projet est uniquement dans le but de ma prépartion des examens de CKAD
 Le projet est décompose en en 11 dossiers. 
 Dans chaque dossier les différents exercice que j'ai eu a réaliser.
 Le fichier readme sera compléte au fur et a mesure de l'avancement de la pratique

 ENJOY



 1. command clusterroles: kubectl get clusterrolebindings --no-headers | wc -l
 1. kuectl get  clusterrolebindings | grep name-clusterrole
 1. kuectl describe  clusterrolebindings  name-clusterrole
 1. create clusterrole: kubectl create clusterrole role-name --verb=get,list,watch --resource=[node,pod,service]
 1. create rolebindind: kubectl create clusterrolebinding name-clusterrolebinding --clusterrole=role-cluster --user=name-user

1. Create a busybox pod (using kubectl command) that runs the command "env". Run it and see the output
``` sh
 kubectl run busybox --image=busybox --command --restart=Never -it --rm -- env # -it will help in seeing the output, --rm will immediately delete the pod after it exits
# or, just run it without -it
kubectl run busybox --image=busybox --command --restart=Never -- env
# and then, check its logs
kubectl logs busybox
```


1. Create a busybox pod that echoes 'hello world' and then exits
``` sh
kubectl run busybox --image=busybox -it --restart=Never -- echo 'hello world'
# or
kubectl run busybox --image=busybox -it --restart=Never -- /bin/sh -c 'echo hello world'

kubectl run busybox --image=busybox -it --rm --restart=Never -- /bin/sh -c 'echo hello world'
# it will delete whene the pod is completed
```|

1. Create TLS secret 

``` sh
 kubectl create secret tsl name-secret-tls --cert "path-tls" --key "path-key"
 
````