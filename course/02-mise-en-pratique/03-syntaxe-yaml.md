# Syntaxe YAML

###### 1. Structure commune

Tous les fichiers YAML des labs suivent cette structure de base :

```yaml
apiVersion: ...
kind: ...
metadata:
  name: ...
spec:
  ...
```

**À retenir**

- `apiVersion` + `kind` = type exact de ressource

- `metadata.name` = identité (unique dans un namespace)

- `spec` = état désiré (tout ce qui est ici est maintenu par Kubernetes)

###### 2. Deployment

Structure minimale utilisée dans les labs

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-demo
spec:
  replicas: 1
  selector:
    matchLabels:
      app: web
  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
      - name: nginx
        image: nginx:stable
```

**Explication champ par champ**

***`spec.replicas`***

```text
replicas: 1
```

- Nombre désiré de pods

- Si l’état réel ≠ ce nombre → controller agit

`***spec.selector.matchLabels***`

```text
selector:
  matchLabels:
    app: web
```

- Définit quels pods appartiennent au Deployment

- Doit correspondre exactement aux labels du pod template

Erreur critique si mismatch → comportement incohérent

`***spec.template***`

```text
template:
  metadata:
    labels:
      app: web
  spec:
    ...
```

- Décrit le pod modèle

- Tout ce qui est ici sera utilisé pour créer/recréer les pods

`***containers***`

```text
containers:
- name: nginx
  image: nginx:stable
```

- Liste obligatoire

- `name` : identifiant interne

- `image` : état désiré applicatif

###### 3. Service

**Service ClusterIP utilisé dans les labs**

```yaml
apiVersion: v1
kind: Service
metadata:
  name: web-demo
spec:
  selector:
    app: web
  ports:
  - port: 80
    targetPort: 80
```

**Champs essentiels**

`***spec.selector***`

```text
selector:
  app: web
```

- Lien Service → Pods

- Kubernetes ne fait aucune magie :

  - si aucun pod n’a ce label → pas d’endpoints

`***spec.ports***`

```text
ports:
- port: 80
  targetPort: 80
```

- `port` : port du **Service**

- `targetPort` : port du **conteneur**

`targetPort` doit correspondre à `containerPort`

###### 4. Probes

**Readiness probe (routage)**

```text
readinessProbe:
  httpGet:
    path: /
    port: 80
  periodSeconds: 2
```

- Conditionne l’entrée dans les endpoints

- Tant que la probe échoue → pas de trafic

**Liveness probe (redémarrage)**

```text
livenessProbe:
  tcpSocket:
    port: 80
  failureThreshold: 3
```

- Détermine si le conteneur doit être tué

- Mauvais réglage → `CrashLoopBackOff`

**Startup probe (démarrage lent)**

```text
startupProbe:
  httpGet:
    path: /
    port: 80
  failureThreshold: 15
  periodSeconds: 2
```

- Protège les applications lentes

- Tant qu’elle n’a pas réussi :

  - liveness ignorée

  - readiness ignorée

###### 5. Pod simple

**Pod utilisé pour tests / démos**

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: ephemeral-writer
spec:
  containers:
  - name: busybox
    image: busybox:1.36
    command: ["/bin/sh","-c"]
    args:
    - |
      echo test
      sleep 3600
```

**Champs clés**

`command` / `args`

- Remplacent `ENTRYPOINT` / `CMD`

- Utilisés dans les labs pour :

  - simuler un crash

  - écrire des données

  - ralentir le démarrage

###### 6. PersistentVolumeClaim

**PVC minimal des labs**

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: data-pvc
spec:
  accessModes:
  - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
```

**À comprendre**

- Le PVC est une demande, pas un disque

- Kubernetes s’occupe du binding

**Montage dans un pod**

```text
volumeMounts:
- name: data
  mountPath: /data

volumes:
- name: data
  persistentVolumeClaim:
    claimName: data-pvc
```

Toujours :

- `volumes` dans `spec`

- `volumeMounts` dans le conteneur

###### 7. Namespace

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: app
```

- Portée logique :

  - noms

  - RBAC

  - visibilité

###### 8. RBAC

**Role**

```yaml
kind: Role
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get","list","watch"]
```

- `apiGroups: [""]` = API core

- `verbs` = **actions autorisées**

**RoleBinding**

```yaml
kind: RoleBinding
subjects:
- kind: ServiceAccount
  name: reader
roleRef:
  kind: Role
  name: read-only
```

- Lie qui → quoi

- Jamais de logique implicite

###### 9. Scheduling

**Toleration**

```text
tolerations:
- key: dedicated
  operator: Equal
  value: lab
  effect: NoSchedule
```

- Autorise un pod à ignorer un taint

**NodeSelector**

```text
nodeSelector:
  role: dedicated
```

- Contrainte simple

- Tous les labels doivent matcher

**Anti-affinité**

```text
podAntiAffinity:
  requiredDuringSchedulingIgnoredDuringExecution:
  - labelSelector:
      matchLabels:
        app: spread
    topologyKey: kubernetes.io/hostname
```

- Force la **répartition**

- Utilisé pour HA

###### 10. Rollout / image

```text
containers:
- name: nginx
  image: nginx:1.25
```

- Changer `image` = changer l’état désiré

- Le reste est géré par Kubernetes

###### Règle d’or pour lire le YAML

Si ce champ est dans `spec`, Kubernetes l’imposera
Si on modifie autre chose, Kubernetes annulera
