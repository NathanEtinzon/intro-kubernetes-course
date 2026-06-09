# Conclusion

**Ce qu’il faut comprendre**

- Sans PVC, les données sont liées au cycle de vie du pod.

- Le PVC découple données et exécution.

- Kubernetes impose cette séparation pour éviter les pertes silencieuses.

**Nettoyage du lab**

```bash
kubectl delete pod ephemeral-writer --ignore-not-found
kubectl delete pod pvc-writer --ignore-not-found
kubectl delete pod pvc-reader --ignore-not-found
kubectl delete pvc data-pvc --ignore-not-found
```
