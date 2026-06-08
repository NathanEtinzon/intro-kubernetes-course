# Lab 4 - Stockage persistant et cycle de vie des données

Ce lab compare un stockage éphémère avec `emptyDir` et un stockage persistant basé sur un PersistentVolumeClaim.

## Objectifs

- Observer la perte de données avec un volume éphémère.
- Créer un PersistentVolumeClaim.
- Vérifier que les données persistent après recréation d'un Pod.
- Identifier la StorageClass utilisée par le cluster.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl get pods,pvc -n k8s-labs
kubectl exec -n k8s-labs deploy/ephemeral-data-demo -- cat /data/message.txt
kubectl exec -n k8s-labs deploy/persistent-data-demo -- cat /data/message.txt
```

Supprimer ensuite les Pods et observer la recréation :

```bash
kubectl delete pod -n k8s-labs -l app=ephemeral-data-demo
kubectl delete pod -n k8s-labs -l app=persistent-data-demo
kubectl get pods -n k8s-labs -w
```

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```

La suppression du PVC peut entraîner la suppression du volume selon la politique de rétention de la StorageClass. Ce lab doit être réalisé sur un cluster prévu pour les tests.
