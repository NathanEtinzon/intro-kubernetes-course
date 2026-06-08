# Lab 8 - Observabilité et diagnostic

Ce lab regroupe des situations classiques de diagnostic Kubernetes.

## Objectifs

- Lire les événements avec `kubectl describe`.
- Consulter les logs.
- Identifier `ImagePullBackOff`.
- Identifier `CrashLoopBackOff`.
- Comprendre un Pod `Running` mais `NotReady`.
- Diagnostiquer un Service sans endpoints.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl get pods,svc,endpoints -n k8s-labs
kubectl describe pod imagepull-demo -n k8s-labs
kubectl describe pod crashloop-demo -n k8s-labs
kubectl logs crashloop-demo -n k8s-labs
kubectl describe pod -n k8s-labs -l app=notready-demo
kubectl describe service service-without-endpoints -n k8s-labs
```

Certains objets sont volontairement en erreur. C'est le comportement attendu pour l'exercice.

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```

Ne pas laisser de ressources volontairement défaillantes sur un cluster partagé afin d'éviter du bruit de supervision inutile.
