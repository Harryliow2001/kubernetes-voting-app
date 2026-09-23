# Kubernetes Voting App
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

## The application consists of:
- Vote Pod
- Result Pod
- Worker Pod
- Redis Pod
- PostgreSQL Pod
- Vote Service
- Result Service
- Redis Service
- PostgreSQL Service
The frontend applications are exposed using NodePort / local port forwarding, while Redis and PostgreSQL communicate internally through ClusterIP services.

## How It Works:
1. A user submits a vote through the Vote application.
2. The vote is stored temporarily in Redis.
3. The Worker retrieves the vote from Redis.
4. The Worker writes the vote into PostgreSQL.
5. The Result application reads the data from PostgreSQL.
6. The browser displays the updated voting result.

## Troubleshooting Experience:
During this project, I practised troubleshooting several Kubernetes and application issues, including:
- Incorrect Kubernetes YAML fields
- Incorrect container and service ports
- Service selector and Pod label mismatches
- Redis connectivity issues
- PostgreSQL connectivity issues
- Pod recreation after immutable specification changes
- Application HTTP 500 errors
- Service endpoint verification
- Container log analysis
