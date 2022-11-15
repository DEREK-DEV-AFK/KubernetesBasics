# Init Container
Let use an init container
## Create the deployment
```
kubectl apply -f myapp.yaml
```
wait for the main pod to come up
```
kubectl get pods
```
## Connect to the Nginx container
```
kubectl exec -it init-demo -- /bin/bash
```
## Hit the default webpage
it should be the one dowloaded by the init container from http://info.cern.sh
```
curl localhost
exit
```
## Cleanup
```
kubectl delete -f myapp.yaml
```