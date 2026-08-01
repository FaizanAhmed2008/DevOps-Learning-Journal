# Kubernetes Volumes

## Key Concepts
- **Volume**: On-disk directory accessible to containers in a Pod.
- **PersistentVolume (PV)**: Cluster-level storage resource provisioned by admin or cloud.
- **PersistentVolumeClaim (PVC)**: Storage request by a user/Pod that binds to a PV.
- **StorageClass**: Defines storage types and enables dynamic provisioning.

## PVC & Pod YAML Example
```yaml
# PersistentVolumeClaim
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
---
# Pod Volume Mount
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  volumes:
  - name: my-storage
    persistentVolumeClaim:
      claimName: my-pvc
  containers:
  - name: app-container
    image: nginx
    volumeMounts:
    - mountPath: /usr/share/nginx/html
      name: my-storage
```

## Commands
- Check Persistent Volumes:
  - `kubectl get pv`
- Check Persistent Volume Claims:
  - `kubectl get pvc`
- Check Storage Classes:
  - `kubectl get sc`
- Describe PVC details:
  - `kubectl describe pvc <pvc-name>`
- Delete PVC:
  - `kubectl delete pvc <pvc-name>`

## Notes
- **emptyDir**: Temporary volume; created when Pod starts, cleared when Pod is removed.
- **hostPath**: Mounts a file/directory from the node's local filesystem into the Pod.
- **PV / PVC**: Separates storage configuration from Pod definitions for data persistence.
