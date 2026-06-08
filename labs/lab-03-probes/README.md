# Lab 3 - État applicatif et probes

Ce lab explique la différence entre un conteneur démarré, un Pod `Running` et une application réellement prête à recevoir du trafic.

## Objectifs

- Ajouter une readiness probe.
- Ajouter une liveness probe.
- Observer l'état `Ready`.
- Comprendre l'impact des probes sur les endpoints d'un Service.

## Exécution

```bash
kubectl apply -f manifests.yaml
kubectl get pods -n k8s-labs
kubectl describe pod -n k8s-labs -l app=probes-demo
kubectl get endpoints probes-demo -n k8s-labs
```

Pour provoquer un état non prêt, modifier temporairement le chemin de la readiness probe vers `/not-ready`, appliquer le manifest, puis observer les événements et les endpoints.

## Nettoyage

```bash
kubectl delete -f manifests.yaml
```
