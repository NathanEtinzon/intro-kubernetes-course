# Le modèle déclaratif (le cœur de Kubernetes)

Dans Kubernetes, **tout est ressource API**.

```yaml
apiVersion:
kind:
metadata:
  name:
spec:
  # état désiré
status:
  # état réel (géré par le cluster)
```

L’utilisateur définit l’intention (`spec`). Kubernetes observe l’état réel (`status`) et agit pour réduire l’écart.

**Erreur fréquente**
Corriger un problème en modifiant manuellement l’état réel (pods, conteneurs) au lieu de corriger l’état désiré.
