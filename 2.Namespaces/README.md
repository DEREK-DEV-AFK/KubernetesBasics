# Namespaces
## Get namespaces
```
kubectl get namespaces
kubectl get ns // shortcut
```
- Example 
- 1
![list](readmeImages/List.png "list")
- 2 shortcut way
![ListShort](readmeImages/ListShort.png "ListShort")
## Get the pods list
```
kubectl get pods
```
- Example
![ListPods](readmeImages/ListPods.png "ListPods")
- You get the pods from the default namespace. Try getting the pods from the docker namespace. You will get a diffrent list.
```
kubectl get pods --namespace=kube-system
// or
kubectlget pods -n kube-system
```
- Example
- 1
![ListPodsOtherNs](readmeImages/ListPodsOfOtherNs.png "ListPods")
- 2
![ListPodsOtherNsShort](readmeImages/ListPodsOfOtherNsShort.png "ListPods")
## Change namespace
```
kubectl config set-context --current --namespace=kube-system
```
![ChangeNs](readmeImages/changeNs.png)
- see if you gets pods on this namespace
```
kubectl get pods
```
![ListsPods](readmeImages/thenListingPods.png)
- lets chnage back to default
```
kubectl config set-context --current --namespace=default
```
![ChangingBackNs](readmeImages/changingBack.png)
## Create and delete a namespace
```
kubectl create ns [name]  // create
kubectl get ns  // gets lists
kubectl delete ns [name]  // delete // alert while deleteing it 
```
![ChangeNs](readmeImages/createListDelete.png)