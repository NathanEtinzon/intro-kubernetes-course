# Conclusion

**Ce qu’il faut comprendre**

- Bon réflexe : `get` → `describe` → `events` → `logs`.

- Les événements expliquent souvent *pourquoi *Kubernetes ne converge pas.

- Les logs expliquent souvent *pourquoi *l’application se comporte mal.

- Le diagnostic repose sur la corrélation de plusieurs signaux.

**Nettoyage du lab**

```bash
kubectl delete deploy bad-image --ignore-not-found
kubectl delete pod crashy --ignore-not-found
kubectl delete deploy not-ready --ignore-not-found
kubectl delete svc broken-service --ignore-not-found
```
