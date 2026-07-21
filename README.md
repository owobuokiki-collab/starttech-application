# StartTech Application

A cloud-native backend application deployed to Amazon EKS using Docker, Kubernetes, Amazon ECR, and GitHub Actions.

## Project Overview

This repository contains the application source code and Kubernetes deployment manifests.

### Technologies Used

- Go
- Docker
- Kubernetes
- Amazon EKS
- Amazon ECR
- GitHub Actions
- Trivy Security Scanner

## Project Structure

```
.
├── backend/
│   ├── cmd/
│   ├── internal/
│   ├── Dockerfile
│   ├── go.mod
│   └── go.sum
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
└── .github/workflows/
    ├── backend-ci-cd.yml
    └── frontend-ci-cd.yml
```

## CI/CD Pipeline

The backend GitHub Actions workflow performs the following:

- Checkout source code
- Setup Go environment
- Run Go tests
- Build Docker image
- Scan image using Trivy
- Login to Amazon ECR
- Push image to ECR
- Update Kubernetes deployment image
- Configure kubectl
- Deploy to Amazon EKS
- Verify deployment rollout

## Deployment

Docker image is stored in Amazon ECR.

Deployment is managed using Kubernetes on Amazon EKS.

## Verification

Example commands:

```bash
kubectl get pods
kubectl get deployments
kubectl get svc
kubectl rollout status deployment/backend-api
```

## Security

- GitHub Secrets for AWS credentials
- Docker image vulnerability scanning using Trivy
- Images stored securely in Amazon ECR

## Author

**Owobu Okiki Osemudiame**

Junior DevOps Engineer
