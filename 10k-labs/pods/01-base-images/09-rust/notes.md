# Project 09 – Rust Pod

## Objective
Deploy a Rust-based HTTP server inside a Kubernetes Pod to understand
native binary execution and container performance characteristics.

---

## Pod Details
- Image: rust:1.77-alpine
- Pod Name: rust-pod
- Runtime: Native Rust binary
- Port: 8080

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it rust-pod -- /bin/sh  
kubectl port-forward rust-pod 8080:8080  

---

## Verification
- Pod reached Running state
- Rust compiler version verified
- HTTP response received successfully

---

## Key Learnings
- Rust compiles to a native binary
- No runtime or VM required
- Very fast startup time
- Low memory footprint

---

## Production Notes
- Use multi-stage Docker builds
- Run binary in scratch/distroless image
- Add liveness/readiness probes
- Excellent choice for high-performance services

---

## Comparison
| Aspect | Rust | Go | Java |
|----|----|----|----|
Startup | Very fast | Very fast | Slow |
Memory | Very low | Low | High |
Runtime | None | None | JVM |

---

## Next Improvements
- Multi-stage Dockerfile
- Distroless image
- Convert Pod to Deployment
