# Évaluation des connaissances conceptuelles

Les réponses attendues sont indiquées dans le fichier : [../questions/banque-questions.md](../questions/banque-questions.md).

## Introduction

Ce questionnaire évalue la partie conceptuelle du cours (architecture, modèle déclaratif, composants, objets fondamentaux).

## Paramètres

- Note maximale : 9.00000
- Somme des points : 10.00000
- Nombre de questions : 10

## Questions

### Question 1

Quel est le rôle principal du *control plane* dans un cluster Kubernetes ?

- [ ] Exécuter les conteneurs applicatifs
- [ ] Décider et maintenir l’état désiré du cluster
- [ ] Assurer le routage réseau entre les pods

### Question 2

Pourquoi Kubernetes sépare-t-il strictement le plan de décision (control plane) et le plan d’exécution (worker nodes) ?

- [ ] Pour améliorer les performances réseau
- [ ] Pour permettre la résilience, la cohérence et l’automatisation à grande échelle
- [ ] Pour simplifier la configuration des conteneurs

### Question 3

Quel est le rôle exact du kube-apiserver ?

- [ ] Lancer et arrêter les conteneurs sur les nœuds
- [ ] Orchestrer le placement des pods
- [ ] Centraliser, valider et exposer l’état du cluster via l’API

### Question 4

Pourquoi etcd est-il considéré comme un composant critique de Kubernetes ?

- [ ] Il exécute les contrôleurs internes
- [ ] Il contient l’état complet et désiré du cluster
- [ ] Il gère le réseau entre les pods

### Question 5

Dans le modèle déclaratif Kubernetes, que représente le champ `spec` d’une ressource ?

- [ ] L’état réel observé par le cluster
- [ ] Les actions que Kubernetes doit exécuter
- [ ] L’état désiré défini par l’utilisateur

### Question 6

Pourquoi la modification manuelle d’un pod (suppression, changement direct) est-elle généralement inefficace ?

- [ ] Parce que les pods sont persistants
- [ ] Parce que le kubelet empêche toute modification manuelle
- [ ] Parce qu’un controller cherche en permanence à faire converger l’état réel vers l’état désiré

### Question 7

Quelle affirmation décrit le mieux la nature d’un pod Kubernetes ?

- [ ] Une machine virtuelle légère avec stockage persistant
- [ ] Une unité d’exécution éphémère regroupant un ou plusieurs conteneurs
- [ ] Un conteneur Docker avec des privilèges élevés

### Question 8

Pourquoi Kubernetes introduit-il l’objet Service ?

- [ ] Pour sécuriser les communications réseau
- [ ] Pour fournir une adresse réseau stable vers des pods éphémères
- [ ] Pour surveiller l’état de santé des applications

### Question 9

Quel est le rôle fondamental des controllers dans Kubernetes ?

- [ ] Superviser les performances du cluster
- [ ] Exécuter les applications utilisateurs
- [ ] Comparer l’état réel et l’état désiré et corriger les écarts

### Question 10

Quel comportement est attendu si un champ est modifié manuellement dans `status` d’une ressource ?

- [ ] Kubernetes applique la modification
- [ ] Kubernetes ignore la ressource
- [ ] Kubernetes écrase la modification
