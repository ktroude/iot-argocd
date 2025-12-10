# ktroude-iot-argocd

Application configuration for IOT Part 3 - ArgoCD continuous deployment

## Structure
```
app/
└── deployment.yaml  # Namespace, Deployment, and Service for wil42/playground
```

## Application

- **Image**: `wil42/playground`
- **Versions**: `v1`, `v2`
- **Port**: 8888

## Usage

This repository is monitored by ArgoCD. Any changes pushed to `app/deployment.yaml` will be automatically synchronized to the Kubernetes cluster.

### Switch to v2

Edit `app/deployment.yaml`:
```yaml
image: wil42/playground:v2  # Change from v1 to v2
```

Commit and push:
```bash
git add app/deployment.yaml
git commit -m "Update to v2"
git push
```

ArgoCD will automatically deploy the new version.
