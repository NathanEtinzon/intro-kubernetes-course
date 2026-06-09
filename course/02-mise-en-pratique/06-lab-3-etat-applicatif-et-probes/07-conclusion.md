# Conclusion

**Ce qu’il faut comprendre**

- `Running` signifie uniquement que le conteneur s’exécute.

- `Ready` conditionne le routage du trafic via les Services.

- Une liveness probe mal réglée peut provoquer des redémarrages en boucle.

- Les probes sont la seule interface entre Kubernetes et l’état applicatif réel.

**Nettoyage du lab**

```bash
kubectl delete deploy slow-app --ignore-not-found
```
