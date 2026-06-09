# Évaluation des connaissances - Lab 1

Les réponses attendues sont indiquées dans le fichier : [../questions/banque-questions.md](../questions/banque-questions.md).

## Introduction

Ce questionnaire évalue la compréhension des mécanismes vus dans le lab 1.

## Paramètres

- Note maximale : 3.00000
- Somme des points : 3.00000
- Nombre de questions : 3

## Questions

### Question 1

Pourquoi un pod supprimé manuellement est-il recréé automatiquement ?

- [ ] Parce que le kubelet redémarre toujours les conteneurs
- [ ] Parce qu’un controller cherche à faire converger l’état réel vers l’état désiré 
- [ ] Parce que les pods sont persistants par défaut

### Question 2

Quel objet Kubernetes définit le nombre de pods attendus ?

- [ ] Pod
- [ ] ReplicaSet 
- [ ] Service

### Question 3

Pourquoi supprimer un pod n’est-il pas une action corrective durable ?

- [ ] Parce que le pod est protégé par le scheduler
- [ ] Parce que Kubernetes interdit les suppressions manuelles
- [ ] Parce que l’état désiré n’a pas été modifié 
