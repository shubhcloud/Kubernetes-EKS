# ReplicaSet - Single Replicaset

```
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/1-singlereplica.yml
```
```
kubectl get all -n twitter
```
```
kubectl describe replicas -n twitter
```
``` 
kubectl get pod,service,replicaset -n twitter -o wide
```
- labels --> service -- selector , replica -- match ---> should be same

```
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/1-singlereplica.yml
```
# ReplicaSet - Multi Replicaset

```
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/3-multireplica.yaml
```

```
kubectl get all -n facebook
```
```
kubectl describe replicas -n facebook
```
```
kubectl get pod,service,replicaset -n facebook -o wide
```
- labels --> service -- selector , replica -- match ---> should be same

```
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/3-multireplica.yaml
```
# Deployements  
```  
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class9-Deployments/deployments/1-deployment-facebook.yaml
```
```
kubectl get all -n facebook -o wide
```
```  
kubectl describe deploy
```
```  
kubectl get pod,service,replicaset,deploy -n facebook -o wide
```
- to understand please delete one pod (before delete in another master ssh window keep run the watch -n 1 kubectl get all -n facebook -o wide command)
```
kubectl delete pod/nginx-74fcc59689-kn5j2 -n facebook
```
then 
run the below command again
```  
kubectl get pod,service,replicaset,deploy -n facebook -o wide
```
change the new version of image in the existing 1-deployment-facebook.yaml --> 
image: nginx:1.17.6 (goto hub.docker.com and get the 1.17.6 version from nginx image)
from hub.docker.com you note the available image tags like below from nginx image.

1.20.1
1.21-perl
1.20-alpine
```
kubectl rollout status deployment/nginx -n facebook
```
```  
kubectl rollout history deploy/nginx -n facebook
```
```
kubectl rollout undo deployment nginx --to-revision=1 -n facebook
```
  
```
kubectl scale deployment/nginx --replicas=12
```
