# K8s context
## get current context
```
kubectl config current-context
```
- Example 
![Current context](readmeImages/currentContext.png "current Context")
## List all contexts
```
kubectl config get-contexts
```
- Example
![context lists](readmeImages/currentContext.png "context lists")

## Change context
```
kubectl config use-context [contextName]
```

## Rename context
```
kubectl config rename-context [old-name] [new-name]
```

## Delete context
```
kubectl config delete context [contextName]
```