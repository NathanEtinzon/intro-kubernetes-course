# Lab 5 - Sécurité minimale : namespaces et RBAC

Ce lab introduit l'isolation par namespace et l'attribution de droits minimaux avec RBAC.

## Objectifs

- Créer un namespace dédié.
- Créer un ServiceAccount.
- Accorder uniquement des droits de lecture ciblés.
- Tester les permissions avec `kubectl auth can-i`.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl auth can-i get pods --as=system:serviceaccount:app:app-reader -n app
kubectl auth can-i delete pods --as=system:serviceaccount:app:app-reader -n app
kubectl get role,rolebinding,serviceaccount -n app
```

Le premier test doit être autorisé, le second doit être refusé.

Le ServiceAccount est créé sans montage automatique de token dans les Pods. Pour ce lab, les tests d'autorisation s'effectuent avec `kubectl auth can-i --as`, ce qui évite de manipuler un token de compte de service.

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```

Ne pas accorder de droits globaux ou permanents pour un simple exercice. Les comptes de service doivent rester limités au namespace et aux verbes nécessaires.
