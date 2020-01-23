# k8s-webforce3

## Check
```shell script
  kubectl get nodes
  kubectl get node
  kubectl get node -o wide

## Deployment example
  kubectl create deployment nginx --image=nginx
  kubectl get deployments
  kubectl describe deployment nginx
  kubectl get events
  kubectl get deployment nginx -o yaml 
  kubectl get deployment nginx -o yaml > first.yaml
```
## Deployment with file
kubectl create -f file second.yaml

## afficher la configuration sans déployer
kubectl create deployment two --image=nginx --dry run -o yaml

## afficher la configuration dans le terminal
kubectl get deployment nginx --export -o yaml
kubectl get deployment nginx --export -o json

##mettre à jour un yaml
kubectl replace -f first.yaml



