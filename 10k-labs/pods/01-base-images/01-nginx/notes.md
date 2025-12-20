## Project 01 – NGINX Pod

### Objective
Deploy a simple NGINX pod using an official base image.

### Steps Performed
- Created Kubernetes pod using nginx image
- Verified pod status
- Executed into container
- Port-forwarded service locally

### Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it nginx-pod -- /bin/sh  
kubectl port-forward nginx-pod 8080:80  

### Learnings
- kubectl requires active cluster
- Pods are the smallest deployable unit
- kubectl exec replaces docker exec in Kubernetes

### Production Notes
- Prefer slim images
- Add resource requests & limits
- Use Deployments instead of Pods for prod
