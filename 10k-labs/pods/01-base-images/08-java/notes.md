# Project 08 – Java Pod

## Objective
Deploy a Java application inside a Kubernetes Pod to understand JVM
behavior, image selection, and container runtime characteristics.

---

## Pod Details
- Image: eclipse-temurin:21-jre
- Pod Name: java-pod
- Runtime: Java JVM
- Java Version: 21

---

## Commands Used
kubectl apply -f pod.yaml  
kubectl get pods  
kubectl exec -it java-pod -- /bin/sh  
kubectl logs java-pod  

---

## Verification
- Pod reached Running state
- Java version verified
- Application logs confirmed

---

## Key Learnings
- JVM startup is slower compared to Go/Node
- Java containers consume more memory
- JRE images are smaller than JDK images
- JVM must run a long-living foreground process

---

## Production Notes
- Always set JVM memory limits explicitly
- Use -Xms and -Xmx
- Enable container awareness (-XX:+UseContainerSupport)
- Prefer distroless Java images

---

## Comparison
| Aspect | Java | Go |
|----|----|----|
Startup | Slow | Very fast |
Memory | High | Low |
Binary | JVM | Native |

---

## Next Improvements
- Add Java HTTP server
- Set JVM memory flags
- Convert Pod to Deployment


## Issue Faced
Java pod failed during startup

## Root Cause
Used JRE image but attempted to compile Java code with javac

## Resolution
Switched to JDK image for compilation

## Learning
JDK is required for building Java applications; JRE is runtime-only
