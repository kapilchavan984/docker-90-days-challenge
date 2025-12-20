# Project 06 – Ruby Pod

## Objective
Deploy a Ruby-based HTTP server inside a Kubernetes Pod using the official
Ruby Alpine base image.

---

## Pod Details
- Image: ruby:3.3-alpine
- Pod Name: ruby-pod
- Server: Ruby stdlib httpd
- Port: 4567

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it ruby-pod -- /bin/sh  
kubectl port-forward ruby-pod 4567:4567  

---

## Verification
- Pod reached Running state
- Ruby version verified
- HTTP server accessible via browser

---

## Key Learnings
- Ruby includes a built-in HTTP server
- Alpine-based images reduce size
- Interpreted languages have moderate startup time
- Pod filesystem is ephemeral

---

## Production Notes
- Do not use built-in httpd in production
- Use Puma/Unicorn with Rails/Sinatra
- Add resource requests and limits
- Use Deployments instead of Pods

---

## Comparison
| Aspect | Ruby | Python |
|----|----|----|
Startup | Medium | Medium |
Use Case | Web apps | APIs, ML |
Image Size | Medium | Medium |

---

## Next Improvements
- Add Sinatra app
- Mount app via ConfigMap
- Convert Pod to Deployment

## Issue Faced
ruby-pod failed with Error state

## Root Cause
Ruby 3.x does not include WEBrick by default

## Resolution
Installed webrick gem at container startup before launching server

## Learning
Runtime-level dependency issues can cause pod failures even when Kubernetes is healthy


kubectl delete pod ruby-pod
kubectl apply -f pod.yaml
kubectl get pods
