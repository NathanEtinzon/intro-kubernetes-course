# Lab 6 - Scheduling avancé : taints, tolerations et affinités

Ce lab présente les mécanismes qui influencent le placement des Pods sur les noeuds.

## Objectifs

- Observer les labels de noeuds.
- Utiliser un `nodeSelector`.
- Ajouter une toleration.
- Comprendre l'anti-affinité entre Pods.

## Préparation

Lister les noeuds et leurs labels :

```bash
kubectl get nodes --show-labels
```

Si le lab utilise un nom ou un label de noeud spécifique, remplacer les valeurs d'exemple par celles de votre cluster. Éviter de modifier les taints ou labels d'un cluster partagé sans validation préalable.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl get pods -n k8s-labs -o wide
kubectl describe pod -n k8s-labs -l app=scheduling-demo
```

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```
