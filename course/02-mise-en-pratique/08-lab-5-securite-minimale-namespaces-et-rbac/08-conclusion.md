# Conclusion

**Ce qu’il faut comprendre**

- Le **namespace** délimite un périmètre logique (ressources et RBAC).

- RBAC est appliqué **centralement** par l’API Server.

- `kubectl auth can-i` est un réflexe d’exploitation.

**Nettoyage du lab**

```bash
kubectl delete namespace app --ignore-not-found
```

*Alternative si on veut conserver le namespace :*

```bash
kubectl -n app delete deploy web --ignore-not-found
kubectl -n app delete svc web --ignore-not-found
kubectl -n app delete role read-only --ignore-not-found
kubectl -n app delete rolebinding reader-binding --ignore-not-found
kubectl -n app delete sa reader --ignore-not-found
```
