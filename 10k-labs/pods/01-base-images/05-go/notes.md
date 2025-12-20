# Project 05 – Go Pod

## Objective
Deploy a Go-based HTTP server inside a Kubernetes Pod using the official
Go Alpine base image.

---

## Pod Details
- Image: golang:1.22-alpine
- Pod Name: go-pod
- Runtime: Go
- Port: 8080

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it go-pod -- /bin/sh  
kubectl port-forward go-pod 8080:8080  

---

## Verification
- Pod reached Running state
- Go version verified inside container
- HTTP endpoint accessible via browser

---

## Key Learnings
- Go binaries start very fast
- Alpine images reduce container size
- Inline Go code is useful for demos
- Containers can compile & run code dynamically

---

## Production Notes
- Use multi-stage builds for Go apps
- Run compiled binary, not `go run`
- Use distroless or scratch images
- Add resource requests and limits

---

## Comparison
| Aspect | Go | Node.js |
|----|----|----|
Startup Time | Very fast | Fast |
Concurrency | Goroutines | Event loop |
Binary | Static | Runtime required |

---

## Next Improvements
- Build binary using multi-stage Dockerfile
- Convert Pod to Deployment
- Add readiness & liveness probes
