# Lab 7 - Mises à jour applicatives et rollback

Ce lab montre comment suivre un déploiement applicatif et revenir à une version précédente.

## Objectifs

- Observer l'historique d'un Deployment.
- Mettre à jour une image.
- Suivre un rollout.
- Réaliser un rollback.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl rollout status deployment/rollout-demo -n k8s-labs
kubectl set image deployment/rollout-demo -n k8s-labs web=nginxinc/nginx-unprivileged:1.26-alpine
kubectl rollout status deployment/rollout-demo -n k8s-labs
kubectl rollout history deployment/rollout-demo -n k8s-labs
kubectl rollout undo deployment/rollout-demo -n k8s-labs
```

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```

En environnement réel, une mise à jour doit être préparée, tracée, testée et associée à une procédure de retour arrière validée.
