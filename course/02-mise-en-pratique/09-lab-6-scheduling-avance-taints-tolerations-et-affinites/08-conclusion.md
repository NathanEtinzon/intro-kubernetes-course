# Conclusion

**Ce qu’il faut comprendre**

- `Pending` est souvent un symptôme de **contraintes** (taints, ressources, affinités).

- Taints = “interdit par défaut”, tolerations = “exception contrôlée”.

- NodeSelector/affinités servent à répondre à des contraintes d’exploitation (réservation, isolation, HA).

**Nettoyage du lab**

```bash
kubectl delete pod with-toleration --ignore-not-found
kubectl delete pod node-selected --ignore-not-found
kubectl delete pod no-toleration --ignore-not-found
kubectl delete deploy spread-demo --ignore-not-found
```

```bash
kubectl taint nodes kubernetes-worker dedicated=lab:NoSchedule- || true
kubectl label node kubernetes-worker role- || true
```
