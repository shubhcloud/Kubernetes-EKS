# Creation of Namspace and pods

# create name space

```
kubectl create ns cloudnloud
```

```
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class4-namespace-Pod/namespace/namespace.yaml
```

```
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class4-namespace-Pod/namespace/namespace.yaml
```

# create pods...

```
kubectl create ns twitter
```
```
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/1-singlepod.yml
```

```
kubectl apply -f 1-singlepod.yml
```
```
kubectl get all -n twitter -l app=nginx
```
```
kubectl get all -n twitter -l version=v1
```

```
kubectl exec -it pod/webserver bash -n twitter
```

- now you need to understand that lablels will help you to create exact report and find the particular resources

```
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/1-singlepod.yml
``` 
  
# Multipod.

```
kubectl create ns facebook

```

```
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/2-multipods.yml
```

```
kubectl get all -n facebook -l app=httpd
```

```
kubectl describe pod/multicontainer-pods -n facebook
```

```
kubectl exec -it pod/multicontainer-pods bash -n facebook
```

```
kubectl exec -it pod/multicontainer-pods bash -n facebook -c web
```

```
kubectl exec -it pod/multicontainer-pods bash -n facebook -c db
```
```
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/2-multipods.yml
```
