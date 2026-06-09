# ReplicaSets, Deployments et auto-réparation

###### ReplicaSet (RS)

- Garantit qu’un **nombre défini de pods** est toujours en cours d’exécution.

- Si un pod meurt ou est supprimé, le ReplicaSet **le recrée automatiquement** pour respecter le nombre souhaité.

- **À retenir :** le ReplicaSet **ne gère pas les mises à jour** des pods, il se concentre uniquement sur la quantité.

###### Deployment

- Ajoute une **couche de gestion applicative** par-dessus le ReplicaSet.

- Permet :

  - **Mises à jour progressives** (rolling updates)

  - **Rollback** en cas de problème

  - **Supervision et auto-réparation** des pods et ReplicaSets

###### Principe clé d’auto-réparation

```text
Supprimer un pod manuellement n’est jamais une solution durable.
```

- Kubernetes détecte la perte et **recrée immédiatement le pod** pour maintenir l’état désiré défini par le Deployment.

**A noter** :

- **ReplicaSet** = assure la quantité de pods

- **Deployment** = assure la quantité + la version + la gestion du cycle de vie

![Deployment & ReplicaSet](https://images.viblo.asia/full/08353e3f-c04d-46c6-899d-33d6eb43ad67.png)
