# Conclusion

**Ce qu’il faut comprendre**

- Supprimer un pod n’est pas une correction durable.

- Le controller détecte un écart entre l’état réel (0 pod) et l’état désiré (1 pod).

- Kubernetes **ne protège pas les pods**, il protège l’état désiré.

**Nettoyage du lab**

```bash
kubectl delete deploy web-demo --ignore-not-found
```

*Attention : vous avez besoin de ce déploiement pour le lab suivant*
