# Pré‑requis

- Un cluster Kubernetes fonctionnel (kind, minikube, k3s…)

- `kubectl` configuré

- Namespace de travail dédié

```bash
kubectl create namespace k8s-labs || true
kubectl config set-context --current --namespace=k8s-labs
```
