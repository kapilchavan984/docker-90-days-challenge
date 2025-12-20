# Project 10 – .NET Pod

## Objective
Deploy a .NET application inside a Kubernetes Pod to understand CLR-based
managed runtime behavior and container image selection.

---

## Pod Details
- Image: mcr.microsoft.com/dotnet/sdk:8.0
- Pod Name: dotnet-pod
- Runtime: .NET CLR
- Framework: .NET 8

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl logs dotnet-pod  
kubectl exec -it dotnet-pod -- /bin/sh  

---

## Verification
- Pod reached Running state
- .NET SDK verified
- Application output confirmed via logs

---

## Key Learnings
- SDK images are required for building applications
- Runtime images are used only to execute built binaries
- Managed runtimes consume more memory
- .NET startup is slower than Go/Rust

---

## Production Notes
- Use multi-stage Docker builds
- Run app using dotnet runtime image
- Set memory limits explicitly
- Enable container-aware GC

---

## Comparison
| Aspect | .NET | Java | Go | Rust |
|----|----|----|----|----|
Startup | Medium | Slow | Fast | Very fast |
Memory | High | High | Low | Very low |
Runtime | CLR | JVM | None | None |

---

## Next Improvements
- ASP.NET Core web app
- Multi-stage Dockerfile
- Distroless runtime image
- Convert Pod to Deployment
