# Project 02 – Apache HTTP Server Pod

## Objective
Deploy an Apache (httpd) web server inside a Kubernetes Pod to understand
container behavior, default document root, and differences from NGINX.

---

## Pod Details
- Image: httpd:2.4
- Pod Name: apache-pod
- Web Server: Apache HTTPD
- Container Port: 80

---

## Commands Executed
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl describe pod apache-pod  
kubectl exec -it apache-pod -- /bin/sh  
kubectl port-forward apache-pod 8081:80  

---

## Apache Document Root
Default document root inside the container:

