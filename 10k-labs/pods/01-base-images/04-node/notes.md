# Project 04 – Node.js Pod

## Objective
Deploy a Node.js application inside a Kubernetes Pod using the official
Node.js Alpine base image.

---

## Pod Details
- Image: node:20-alpine
- Pod Name: node-pod
- Runtime: Node.js
- Port: 3000

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it node-pod -- /bin/sh  
kubectl port-forward node-pod 3000:3000  

---

## Verification
- Pod reached Running state
- Node.js version verified
- Application accessible via browser

---

## Key Learnings
- Node.js apps can run without frameworks
- Alpine images are lightweight
- Inline scripts are useful for quick testing
- Pod filesystem is ephemeral

---

## Production Notes
- Use Express/Fastify for real applications
- Do not run apps as root in production
- Add resource requests and limits
- Use Deployments and Services

---

## Comparison
| Aspect | Node.js | Python |
|-----|--------|--------|
Runtime | Event-driven | Interpreter-based |
Use Case | APIs, async apps | Scripts, ML, APIs |
Image Size | Small (alpine) | Medium |

---

## Next Improvements
- Add Express app
- Use ConfigMap for source code
- Convert Pod to Deployment
