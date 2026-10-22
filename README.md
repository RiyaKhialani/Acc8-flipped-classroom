# Acc8 Flipped Classroom

This project contains a containerized web application, a Kubernetes Deployment
manifest, and a GitHub Actions workflow.

## CI pipeline

Every push to `main` checks out the project, configures Docker Buildx, and
builds and publishes the Docker image as
`riyakhialani/sample-web-app:v1.0.<run-number>`.

The repository must contain an Actions secret named `DOCKERHUB_TOKEN`. Store a
Docker Hub access token there; never commit it to the repository.

Create a Docker Hub repository named `sample-web-app` under the
`RiyaKhialani` account before running the publishing workflow.

## Kubernetes deployment

Apply the manifest with:

```bash
kubectl apply -f deployment.yaml
kubectl get deployment,pods
```

The Deployment starts two replicas and defines CPU and memory requests/limits.
