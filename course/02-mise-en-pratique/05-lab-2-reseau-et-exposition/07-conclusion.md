# Conclusion

**Ce qu’il faut comprendre**

- Un Service applique strictement une correspondance labels ↔ selectors.

- Kubernetes ne corrige pas une logique réseau incorrecte.

- Les IP des pods sont éphémères ; celles des Services sont stables.

**Nettoyage du lab**

```bash
kubectl delete svc web-demo --ignore-not-found
```
