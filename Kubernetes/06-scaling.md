# Kubernetes Scaling

## Commands
- Scale deployment manually:
  - `kubectl scale deployment/<deployment-name> --replicas=<count>`
- Check replica count:
  - `kubectl get deployment <deployment-name>`
- Enable Horizontal Pod Autoscaler (HPA):
  - `kubectl autoscale deployment <deployment-name> --min=<min> --max=<max> --cpu-percent=<target>`
- View HPA status:
  - `kubectl get hpa`
- Describe HPA for details:
  - `kubectl describe hpa <hpa-name>`

## Notes
- Scaling adds or removes pod replicas to handle load.
- HPA adjusts replicas automatically based on resource use.
- Manual scaling is useful for fixed capacity changes.
