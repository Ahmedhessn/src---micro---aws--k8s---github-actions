# Kubernetes manifests (starter)

This folder contains **plain Kubernetes YAML** manifests to deploy the stack.

## What’s included
- `namespace.yaml`: optional namespace
- `mysql.yaml`: MySQL Deployment + Service + PVC + Secret
- `memcached.yaml`: Memcached Deployment + Service
- `rabbitmq.yaml`: RabbitMQ Deployment + Service
- `apps.yaml`: Application (Tomcat) Deployment + Service
- `nginx.yaml`: Nginx Deployment + Service + ConfigMap
- `kustomization.yaml`: simple kustomize entrypoint (optional)

## Before applying
1. Replace the image placeholders:
   - `REPLACE_AWS_ACCOUNT_ID`
   - `REPLACE_AWS_REGION`
   - `REPLACE_IMAGE_TAG` (use the tag you pushed, or prefer a digest)
2. (Recommended) Replace MySQL credentials in `mysql.yaml` secret.

## Apply
```bash
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/
```

## Notes
- These are intended as a **starting point** for moving to Helm later.
- For production, consider:
  - external DB (RDS) instead of in-cluster MySQL
  - NetworkPolicies, resource limits, PodDisruptionBudgets, HPA
  - sealed-secrets / external-secrets for credentials

