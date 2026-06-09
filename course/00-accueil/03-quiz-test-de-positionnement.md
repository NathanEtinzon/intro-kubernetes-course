# Test de positionnement

Les réponses attendues sont indiquées dans le fichier : [../questions/banque-questions.md](../questions/banque-questions.md).

## Introduction

Ce questionnaire permet d’évaluer le niveau de compréhension initial des concepts clés sur lesquels Kubernetes s’appuie.

## Paramètres

- Note maximale : 9
- Nombre de questions : 9

## Questions

### Question 1

Quel est l’objectif principal de Kubernetes ?

- [ ] Remplacer Docker en tant que moteur de conteneurs
- [ ] Orchestrer automatiquement l’exécution d’applications conteneurisées
- [ ] Fournir un environnement de développement clé en main

### Question 2

Dans Kubernetes, que signifie le fait de “déclarer un état” ?

- [ ] Décrire une suite d’actions à exécuter dans l’ordre
- [ ] Indiquer à Kubernetes ce que l’on souhaite obtenir, pas comment y parvenir
- [ ] Écrire un script exécuté directement sur les nœuds

### Question 3

Quel composant est la *source de vérité* de l’état du cluster Kubernetes ?

- [ ] kube-scheduler
- [ ] kube-apiserver
- [ ] etcd

### Question 4

Pourquoi un pod supprimé manuellement est-il généralement recréé automatiquement ?

- [ ] Parce que le kubelet redémarre systématiquement les conteneurs
- [ ] Parce qu’un controller cherche à faire converger l’état réel vers l’état désiré
- [ ] Parce que les pods sont persistants par défaut

### Question 5

Quelle affirmation décrit le mieux un pod Kubernetes ?

- [ ] Un serveur virtuel durable avec une IP fixe
- [ ] Une unité d’exécution éphémère pouvant contenir un ou plusieurs conteneurs
- [ ] Un conteneur Docker avec des permissions élevées

### Question 6

Quelle est la fonction principale d’un Service Kubernetes ?

- [ ] Stocker les données de l’application
- [ ] Fournir une adresse réseau stable vers des pods dynamiques
- [ ] Surveiller l’état de santé des conteneurs

### Question 7

Quelle est la différence essentielle entre une readiness probe et une liveness probe ?

- [ ] La readiness probe décide si le pod doit être redémarré
- [ ] La liveness probe décide si le pod peut recevoir du trafic
- [ ] La readiness probe conditionne le routage du trafic, la liveness le redémarrage

### Question 8

Pourquoi les données écrites dans le système de fichiers d’un conteneur sont-elles perdues lors de la recréation d’un pod ?

- [ ] Parce que Kubernetes supprime systématiquement les volumes
- [ ] Parce que le système de fichiers du conteneur est éphémère
- [ ] Parce que les permissions Linux sont réinitialisées

### Question 9

Quel est le bon ordre de raisonnement pour diagnostiquer un problème Kubernetes ?

- [ ] logs → events → describe → get
- [ ] get → describe → events → logs
- [ ] describe → logs → get → events
