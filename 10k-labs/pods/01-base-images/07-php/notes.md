# Project 07 – PHP Pod

## Objective
Deploy a PHP-based HTTP server inside a Kubernetes Pod using the official
PHP CLI image.

---

## Pod Details
- Image: php:8.3-cli
- Pod Name: php-pod
- Server: PHP built-in server
- Port: 8080

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it php-pod -- /bin/sh  
kubectl port-forward php-pod 8080:8080  

---

## Verification
- Pod reached Running state
- PHP version verified
- index.php served successfully

---

## Key Learnings
- PHP has a built-in development server
- Server must run in foreground for Kubernetes
- PHP containers are common in legacy systems
- Files created inside pods are ephemeral

---

## Production Notes
- Do NOT use php -S in production
- Use PHP-FPM + NGINX/Apache
- Add resource requests and limits
- Use Deployments instead of Pods

---

## Comparison
| Aspect | PHP | Ruby |
|----|----|----|
Startup | Medium | Medium |
Use Case | Legacy apps | Web apps |
Execution | Request-based | Interpreter |

---

## Next Improvements
- Use PHP-FPM
- Add NGINX sidecar
- Mount code via ConfigMap
