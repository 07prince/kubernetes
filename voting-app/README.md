# Voting App with Kubernetes

This project demonstrates a distributed architecture using Kubernetes. It consists of the following components:
- **Voting App (Frontend)**: A Python app where users can vote.
- **Result App (Frontend)**: A Node.js app that shows the voting results.
- **Redis**: Used for counting the votes.
- **Postgres**: Stores the voting data.
- **Worker**: Collects votes from Redis and transfers them to Postgres.

## Architecture Overview

![Architecture Overview](./images/Screenshot-from-2024-09-30-22-12-04.png)


The architecture consists of the following pods:
- **Voting App**: Exposed on port 80 for users to cast votes.
- **Result App**: Exposed on port 80 for users to view the results.
- **Redis**: Backend for storing votes temporarily.
- **Postgres**: Backend for permanently storing vote results.
- **Worker**: Responsible for moving data from Redis to Postgres.

## Prerequisites

- Kubernetes Cluster
- `kubectl` installed and configured

## Setup Instructions

### Clone the Repository


### git clone https://github.com/07prince/kubernetes
### cd voting-app

## Apply Kubernetes Manifests
To deploy all the components (voting app, result app, Redis, Postgres, worker), use the following command:
- kubectl apply -f voting-deployment.yaml
- kubectl apply -f result-deployment.yaml
- kubectl apply -f redis-deployment.yaml
- kubectl apply -f postgres-deployment.yaml
- kubectl apply -f worker-deployment.yaml
- kubectl apply -f voting-service.yaml
- kubectl apply -f result-service.yaml
- kubectl apply -f redis-service.yaml
- kubectl apply -f postgres-service.yaml
## Clean Up
To delete all the resources, use:
- kubectl delete -f voting-deployment.yaml
- kubectl delete -f result-deployment.yaml
- kubectl delete -f redis-deployment.yaml
- kubectl delete -f postgres-deployment.yaml
- kubectl delete -f worker-deployment.yaml
- kubectl delete -f voting-service.yaml
- kubectl delete -f result-service.yaml
- kubectl delete -f redis-service.yaml
- kubectl delete -f postgres-service.yaml
