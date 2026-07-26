# Kubernetes Configuration Files

## Deployment YAML
```yaml
apiVersion: apps/v1          # API version for Deployment
kind: Deployment             # Resource type
metadata:                    # Metadata for the object
  name: my-app               # Name of the deployment
spec:                        # Desired state
  replicas: 2                # Number of pod replicas
  selector:                  # Selects pods managed by this deployment
    matchLabels:
      app: my-app
  template:                  # Pod template
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-container    # Container name
        image: my-image:latest
```

## Service YAML
```yaml
apiVersion: v1              # API version for Service
kind: Service               # Resource type
metadata:
  name: my-service          # Name of the service
spec:                       # Service configuration
  selector:
    app: my-app             # Sends traffic to pods with this label
  ports:
  - port: 80                # Service port
    targetPort: 8080       # Container port
    protocol: TCP
```

## Commands
- Apply deployment YAML:
  - `kubectl apply -f deployment.yaml`
- Apply service YAML:
  - `kubectl apply -f service.yaml`
- Check resources:
  - `kubectl get deploy,svc`
- Delete deployment:
  - `kubectl delete deployment my-app`
- Delete service:
  - `kubectl delete service my-service`
- Delete both with one file:
  - `kubectl delete -f deployment.yaml`
