# Conclusion

**Ce qu’il faut comprendre**

- Un Deployment encode une stratégie de changement reproductible.

- Une régression se traite en corrigeant l’état désiré (image), pas en modifiant les pods.

- `rollout status/history/undo` sont des commandes d’exploitation.

**Nettoyage du lab**

```bash
kubectl delete deploy rollout-demo --ignore-not-found
```
