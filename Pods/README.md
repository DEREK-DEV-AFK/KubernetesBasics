# Pods
Lets first create a node running Nginx by using hte imperative way
## Create the pod
```
kubectl run mynginx --image=nginx
```
![Create](readmeImages/podCreate.png)
## Get a list of running pods
```
kubectl get pods
```
![List](readmeImages/podGet.png)
## Get more info
```
kubectl get pods -o wide
kubectl describe pod mynginx
```
![ListWide](readmeImages/podGetWide.png)
## Delete the pod
```
kubectl delete pod mynginx
```
![Delete](readmeImages/podDelete.png)
## Create a pod running BusyBox
Lets now create a node running BusyBox, this time attaching bash to our terminal
```
kubectl run mybox --image=busybox -it -- /bin/sh
```
## List the folders and use command
```
ls
echo -n 'A Secret' | base64
exit
```
![BusyboxCreate](readmeImages/podBusyboxInstance.png)
## Cleanup
```
kubectl delete pod mybox --wait-false
```
or
```
kubectl delete pod mybox --grace-period=0 --force
```
![BusyboxDelete](readmeImages/podBusyboxDelete.png)
## Create a pod using the declarative way
let's now create a node using a YAML file
```
kubectl create -f myapp.yaml
```
![DeclarativeCreate](readmeImages/podDeclarativeCreate.png)
## Get some info
```
kubectl get pods -o wide
kubectl describe pod myapp-pod
```
![DeclarativeList](readmeImages/podDeclrativeGetPods.png)
## Attach our terminal
```
kubectl exec -it myapp-pod -- bash
```
print the DBCON environment variable that was set in the YAML file
```
echo $DBCON
```
![DeclarativeTerminal](readmeImages/podDeclarativeInstance.png)
## Detach from the instance 
```
exit
```
## Cleanup
```
kubectl delete -f myapp.yaml
```
![DeclarativeExit](readmeImages/podDeclarativeDelete.png)
