# IoT Part 3 - ArgoCD GitOps

This repository contains Kubernetes manifests for IoT project part 3.

## Structure
- `k8s-manifests/`: Kubernetes YAML files monitored by ArgoCD
- `argocd/`: ArgoCD application configuration

## Application
- **Image**: ktroude42/playground:v1 (will be updated to v2 for GitOps demo)
- **Port**: 8888
- **Namespace**: dev

## GitOps Workflow
1. Modify `k8s-manifests/deployment.yaml`
2. Change image tag from `v1` to `v2`
3. Commit and push
4. ArgoCD automatically syncs the changes
5. Application updates without manual intervention

## Usage
```bash
# Test the application
kubectl port-forward svc/ktroude-playground-service -n dev 8888:8888
curl http://localhost:8888
```
