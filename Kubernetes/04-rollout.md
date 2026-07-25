# Kubernetes Rollout

## Commands
- Update deployment image to a new version:
  - `kubectl set image deployment/<deployment-name> <container-name>=<new-image>:<tag>`
- Check rollout status:
  - `kubectl rollout status deployment/<deployment-name>`
- Check deployment history:
  - `kubectl rollout history deployment/<deployment-name>`
- Undo last rollout:
  - `kubectl rollout undo deployment/<deployment-name>`

## Notes
- This helps achieve zero-downtime deployment.
- The old pods are replaced gradually with new ones.
- Use a new image version to deploy updates safely.
