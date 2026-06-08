# Introduction à Kubernetes

Ce dépôt met à disposition un cours d'introduction à Kubernetes sous forme de sauvegarde Moodle importable, accompagnée de ressources techniques et de captures d'écran.

Le cours est conçu pour accompagner des apprenants dans la découverte des concepts fondamentaux de Kubernetes à travers une progression théorique et des labs pratiques.

## Public visé

Ce support s'adresse aux personnes souhaitant découvrir Kubernetes ou réutiliser un cours d'introduction : étudiants, enseignants, formateurs, administrateurs système ou réseau, profils DevOps débutants et personnes préparant une formation Kubernetes.

## Contenu du cours

- Présentation du module
- Pré-requis Kubernetes, K3s et kubectl
- Comprendre Kubernetes
- Architecture générale : Control Plane et Workers
- Introduction à YAML
- Lab 1 - Déploiement et auto-réparation
- Lab 2 - Réseau et exposition
- Lab 3 - État applicatif et probes
- Lab 4 - Stockage persistant et cycle de vie des données
- Lab 5 - Sécurité minimale : namespaces et RBAC
- Lab 6 - Scheduling avancé : taints, tolerations et affinités
- Lab 7 - Mises à jour applicatives et rollback
- Lab 8 - Observabilité et diagnostic
- Évaluation finale
- Références et webographie

## Objectifs pédagogiques

À la fin du cours, l'apprenant doit être capable de 
- Comprendre l'architecture générale de Kubernetes
- Déployer une application avec un Deployment
- Observer l'auto-réparation via Deployment, ReplicaSet et Pod
- Exposer une application avec un Service ClusterIP
- Manipuler labels, selectors et endpoints
- Distinguer les états `Running` et `Ready`
- Utiliser des readiness probes et liveness probes
- Comprendre la différence entre stockage éphémère et stockage persistant
- Créer et utiliser un PersistentVolumeClaim
- Utiliser des namespaces et RBAC
- Tester des droits avec `kubectl auth can-i`
- Appliquer des taints, tolerations, labels et node selectors
- Comprendre l'anti-affinité
- Effectuer une mise à jour applicative et un rollback
- Diagnostiquer des erreurs Kubernetes courantes comme `ImagePullBackOff`, `CrashLoopBackOff`, `Running` mais `NotReady`, ou un Service sans endpoints.

## Pré-requis techniques

Pour importer le cours, une instance Moodle et des droits suffisants de restauration de cours sont nécessaires.

Pour réaliser les labs hors Moodle, il faut disposer d'un cluster Kubernetes fonctionnel, de `kubectl` configuré, d'un environnement K3s, Minikube, Kind ou équivalent, d'un accès shell Linux, d'une StorageClass disponible pour le lab stockage persistant et idéalement de deux noeuds pour le lab scheduling. Les commandes doivent être exécutées avec un compte disposant uniquement des droits nécessaires sur l'environnement de lab.

## Télécharger le fichier Moodle

Le fichier Moodle principal est disponible ici :

```text
moodle/intro-kubernetes-course.mbz
``

## Importer le cours dans Moodle

1. Télécharger le fichier `.mbz` depuis le dossier `moodle/` ou depuis la release GitHub.
2. Se connecter à une instance Moodle avec les droits nécessaires.
3. Créer un nouveau cours ou choisir un cours existant.
4. Utiliser la fonction de restauration de cours.
5. Importer le fichier `intro-kubernetes-course.mbz`.
6. Vérifier les sections, activités, ressources, quiz et captures après restauration.

La procédure détaillée est disponible dans [docs/import-moodle.md](docs/import-moodle.md).

## Utiliser les labs sans Moodle

Le fichier `.mbz` reste l'artefact principal pour Moodle. Les dossiers `labs/`, `docs/` et `screenshots/` peuvent cependant être consultés directement pour utiliser les consignes, les manifests YAML, les commandes Kubernetes et les illustrations sans importer le cours.

Chaque lab contient un fichier `README.md` et un fichier `manifests.yaml`. Les ressources peuvent être appliquées avec :

```bash
kubectl apply -f labs/<nom-du-lab>/manifests.yaml
```

Avant toute exécution, relire les manifests, adapter les namespaces si nécessaire, vérifier le contexte actif avec `kubectl config current-context` et s'assurer que l'environnement cible est bien un cluster de lab.

## Licence et réutilisation

Sauf mention contraire, ce contenu pédagogique est publié sous licence Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International, `CC BY-NC-SA 4.0`.

La réutilisation et la modification sont autorisées avec attribution. L'usage commercial est interdit. Les adaptations doivent être partagées sous la même licence.

Voir [LICENSE](LICENSE).
