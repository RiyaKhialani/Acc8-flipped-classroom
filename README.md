# Acc8 Flipped Classroom

This project contains a containerized web application, a Kubernetes Deployment
manifest, and a GitHub Actions workflow.

## CI pipeline

Every push to `main` checks out the project, configures Docker Buildx, and
builds the Docker image. The workflow is intentionally configured without
Docker Hub credentials, so it can run successfully without repository secrets.

## Kubernetes deployment

Apply the manifest with:

```bash
kubectl apply -f deployment.yaml
kubectl get deployment,pods
```

The Deployment starts two replicas and defines CPU and memory requests/limits.
