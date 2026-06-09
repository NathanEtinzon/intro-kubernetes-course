# Objectif

Comprendre comment Kubernetes décide **où** placer les pods et pourquoi un pod peut rester en `Pending`.

Ce lab couvre :

- **taints** (protéger un nœud),

- **tolerations** (autoriser une exception),

- **nodeSelector** (contrainte simple),

- **podAntiAffinity** (répartition pour HA).
