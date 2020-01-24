e# k8s-webforce3

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
   
## récupérer le token pour accéder à l'interface kubernetes
   kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}' )

k 
## afficher la configuration dans le terminal
    kubectl get deployment nginx --export -o yaml
    kubectl get deployment nginx --export -o json

## cumettre à jour un yaml
    kubectl replace -f first.yaml

    kubectl deploy,pod

    kubectl expose deployment/nginx
##ouvrir le service nginx
    kubectl get svc nginx
    
## fermer un service nginx
    kubectl delete svc nginx
    
##
    kubectl get ep nginx
    
## detruire un pod
    kubectl delete deploy <pod>

## trouver un pod
    k describe pod nginx-85ff79dd56-jd9gr | grep Node:
   
## deployer trois pod identiques   
    k scale deployment nginx --replicas=3
    
## supprimer tous les pod identiques
    k scale deployment nginx --replicas=0
    
    
## visualiser les pod qui tournent    
    k get pod -o wide
    k get deployment nginx

## inspecter l'état d'un pod
    k exec nginx-xxxx --printenv | grep KUBERNETES
    
## exposer un service vers l'exterieur en publique
    k expose deployment nginx --type=LoadBalancer
 
## interface kubernetesk    
    k get svc -A
    kubernetes-dashboard   kubernetes-dashboard        LoadBalancer   10.100.73.209    <pending>     443:31981/TCP 
   
    kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}' )
    k get po
    k create deployment hog --image vish/stress
    kLS
     get deployment hog --export -o yaml > hog.yaml
    cat hog.yaml
    k deploy
    k get deployment hog
    k get po
    k get pods
    k logs hog-78cf7f9d64-vtkvz
    k get pods -o wide
    
    k create namepsace low-usage-limit
    k get namespace
    https://kubernetes.io/docs/concepts/policy/limit-range/
    k get limitrange -A
    k -n low-usage-limit get pods
    k delete rs rs-one --cascade=false
