# Kubernetes Auto-healing

## Commands
- Check pod status:
  - `kubectl get pods`
- Check deployment status:
  - `kubectl get deployment <deployment-name>`
- Describe a pod for error details:
  - `kubectl describe pod <pod-name>`
- Delete a bad pod and let Kubernetes restart it:
  - `kubectl delete pod <pod-name>`

## Notes
- Kubernetes auto-heals by restarting pods that fail or crash.
- Use deployments so failed pods are recreated automatically.
- Auto-healing keeps apps running without manual intervention.
