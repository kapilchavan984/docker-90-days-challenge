# Project 03 – Python Pod

## Objective
Deploy a Python-based container running a simple HTTP server using the
official Python base image.

---

## Pod Details
- Image: python:3.12-slim
- Pod Name: python-pod
- Server: Python built-in http.server
- Port: 8000

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it python-pod -- /bin/sh  
kubectl port-forward python-pod 8000:8000  

---

## Verification
- Pod reached Running state
- Python version verified inside container
- HTTP server accessible via browser

---

## Key Learnings
- Python images can run lightweight servers without frameworks
- `python -m http.server` is useful for quick testing
- Slim images reduce size and attack surface
- Container filesystem is ephemeral

---

## Production Notes
- Do not use built-in http.server in production
- Use Gunicorn / uWSGI for real apps
- Add resource requests and limits
- Use ConfigMaps for application code

---

## Comparison
| Aspect | Python | NGINX |
|-----|------|------|
Startup Time | Slower | Faster |
Use Case | App logic | Static content |
Image Size | Medium | Small |

---

## Next Improvements
- Add Flask app
- Mount code via ConfigMap
- Convert Pod to Deployment
