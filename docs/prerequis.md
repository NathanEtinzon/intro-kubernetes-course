# Pré-requis techniques

## Moodle

Pour restaurer le cours Moodle, il faut disposer d'une instance Moodle accessible, d'un compte autorisé à restaurer des cours et d'un espace de cours cible. L'import doit être réalisé avec un compte nominatif disposant de droits adaptés, puis contrôlé après restauration afin de vérifier les sections, activités, ressources, quiz et médias.

## Kubernetes

Pour réaliser les labs, il faut disposer d'un cluster Kubernetes fonctionnel et isolé d'un environnement de production. K3s, Minikube, Kind ou un cluster de formation équivalent conviennent.

Le poste d'administration doit disposer de `kubectl`, d'un kubeconfig dédié au cluster de lab, d'un accès shell Linux et d'un accès réseau vers l'API Server Kubernetes. Le contexte actif doit être vérifié avant chaque manipulation :

```bash
kubectl config current-context
kubectl cluster-info
kubectl get nodes
```

## Points spécifiques aux labs

Le lab stockage persistant nécessite une StorageClass disponible :

```bash
kubectl get storageclass
```

Le lab scheduling est plus lisible avec au moins deux noeuds. Si un worker nommé `kubernetes-worker` n'existe pas, utiliser un nom de noeud réel obtenu avec :

```bash
kubectl get nodes -o wide
```

Les labs utilisent principalement le namespace courant ou `k8s-labs`. Le lab RBAC utilise le namespace `app`.

## Précautions d'exploitation

Utiliser un cluster de lab, éviter les privilèges cluster-admin permanents, limiter les droits au strict nécessaire, ne jamais publier de kubeconfig ni de token, et nettoyer les ressources après les exercices. Les valeurs sensibles doivent être remplacées par des placeholders comme `<IP_DU_SERVEUR>`, `<TOKEN>`, `<NOM_DU_NOEUD>` ou `<USERNAME>`.
