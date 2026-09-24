# Kubernetes Simple Voting App
A hands-on Kubernetes project created to practise container orchestration, service networking, and troubleshooting using a multi-service voting application.
The application allows users to vote between two options, processes the vote through Redis and a worker service, stores the result in PostgreSQL, and displays the updated result through a separate result application.

## Architecture
Vote App > Redis > Worker > PostgreSQL > Result App

## Tech Stack
- Kubernetes
- Docker
- kind
- kubectl
- Redis
- PostgreSQL
- WSL2
- YAML

## The application consists of
- Vote Pod
- Result Pod
- Worker Pod
- Redis Pod
- PostgreSQL Pod
- Vote Service
- Result Service
- Redis Service
- PostgreSQL Service

## How It Works
1. A user submits a vote through the Vote application.
2. The vote is stored temporarily in Redis.
3. The Worker retrieves the vote from Redis.
4. The Worker writes the vote into PostgreSQL.
5. The Result application reads the data from PostgreSQL.
6. The browser displays the updated voting result.

## What I Implemented
- Kubernetes Deployments for Vote, Result, Worker, Redis and PostgreSQL
- ClusterIP services for internal communication
- NodePort / port-forwarding for frontend access
- Labels and selectors for service discovery
- Redis queue integration
- PostgreSQL persistence layer
- Multi-container service communication

## Troubleshooting Experience
During this project, I practised troubleshooting several Kubernetes and application issues, including:
- HTTP 500 errors caused by backend connectivity problems
- Incorrect Redis and PostgreSQL ports
- Service selector and Pod label mismatches
- PostgreSQL dependency/startup issues
- Immutable Pod specification errors
- Kubernetes YAML validation errors
- Service endpoint and DNS troubleshooting
### Tools used:
- kubectl logs
- kubectl describe
- kubectl get endpoints
- kubectl get svc
- kubectl exec
