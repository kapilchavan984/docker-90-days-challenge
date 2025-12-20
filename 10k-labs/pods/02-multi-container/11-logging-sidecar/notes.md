# Project 11 – Logging Sidecar Pattern

## Objective
Demonstrate logging sidecar pattern where application logs are written
to a shared volume and consumed by a sidecar container.

---

## Pod Design
- Main container writes logs
- Sidecar tails logs
- Shared emptyDir volume

---

## Containers
| Container | Role |
|--------|------|
app | Generates logs |
log-sidecar | Consumes logs |

---

## Key Learnings
- Containers in a Pod share volumes
- Sidecars run independently
- Logging sidecars decouple app & logging logic

---

## Production Usage
- Fluent Bit / Fluentd
- Vector
- Logstash

---

## Interview Notes
- Sidecar pattern enables separation of concerns
- Logging sidecars are very common in legacy apps
