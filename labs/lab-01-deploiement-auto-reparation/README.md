# Lab 1 - Déploiement et auto-réparation

Ce lab montre comment Kubernetes maintient l'état désiré d'une application avec un Deployment et un ReplicaSet.

## Objectifs

- Créer un Deployment.
- Observer les Pods répliqués.
- Supprimer un Pod et constater son remplacement automatique.
- Comprendre la relation Deployment, ReplicaSet et Pod.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl get deployment,replicaset,pods -n k8s-labs
kubectl delete pod -n k8s-labs -l app=auto-repair-demo
kubectl get pods -n k8s-labs -w
```

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```

Ce lab doit être exécuté sur un cluster de test. Ne pas utiliser de namespace de production pour les manipulations d'apprentissage.
