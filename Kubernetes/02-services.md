# Kubernetes Services

## Commands
- Expose deployment as a service:
  - `kubectl expose deployment <name> --type=NodePort --port=80`
- Check services:
  - `kubectl get services`
- Get service details:
  - `kubectl describe service <name>`
