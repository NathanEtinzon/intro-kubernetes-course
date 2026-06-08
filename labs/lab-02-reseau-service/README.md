# Lab 2 - Réseau et exposition

Ce lab introduit l'exposition interne d'une application avec un Service `ClusterIP`.

## Objectifs

- Déployer une application web.
- Créer un Service.
- Comprendre les labels, selectors et endpoints.
- Tester l'accès au Service depuis le cluster.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl get pods,svc,endpoints -n k8s-labs
kubectl run curl-test -n k8s-labs --rm -it --image=curlimages/curl:8.8.0 --restart=Never -- curl -s http://web-demo:8080
```

## Points d'observation

Si le Service ne possède aucun endpoint, vérifier que le selector du Service correspond bien aux labels des Pods :

```bash
kubectl describe service web-demo -n k8s-labs
kubectl get pods -n k8s-labs --show-labels
```

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```
