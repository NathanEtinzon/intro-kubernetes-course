# Évaluation finale

Les réponses attendues sont indiquées dans le fichier : [../questions/banque-questions.md](../questions/banque-questions.md).

## Paramètres

- Note maximale : 20.00000
- Somme des points : 20.00000
- Nombre de questions : 20

## Questions

### Question 1

Pourquoi Kubernetes impose-t-il l’usage d’une API centrale (kube-apiserver) pour toute modification du cluster ?

- [ ] Pour améliorer les performances réseau
- [ ] Pour garantir cohérence, sécurité et traçabilité de l’état
- [ ] Pour empêcher toute automatisation externe

### Question 2

Quel comportement est attendu si un champ est modifié manuellement dans `status` d’une ressource ?

- [ ] Kubernetes applique la modification
- [ ] Kubernetes ignore la ressource
- [ ] Kubernetes écrase la modification

### Question 3

Quelle relation existe entre Deployment et ReplicaSet ?

- [ ] Le Deployment remplace définitivement le ReplicaSet
- [ ] Le ReplicaSet pilote le Deployment
- [ ] Le Deployment crée et gère les ReplicaSets

### Question 4

Pourquoi Kubernetes ne fournit-il pas directement l’état métier d’une application ?

- [ ] Pour des raisons de sécurité
- [ ] Parce qu’il est volontairement agnostique de l’application
- [ ] Parce que etcd ne peut pas stocker ces informations

### Question 5

Quel élément déclenche réellement une action de correction dans Kubernetes ?

- [ ] Une commande kubectl
- [ ] Un écart entre état réel et état désiré
- [ ] Une alerte de supervision

### Question 6

Dans un manifest Deployment, pourquoi `spec.selector.matchLabels` est-il critique ?

- [ ] Il définit les ports exposés
- [ ] Il lie le Deployment aux pods qu’il contrôle
- [ ] Il active l’auto-scaling

### Question 7

Quel est l’effet direct d’un selector incorrect dans un Service ?

- [ ] Le Service ne peut pas être créé
- [ ] Le Service existe mais ne route vers aucun pod
- [ ] Les pods sont supprimés

### Question 8

Pourquoi les endpoints d’un Service peuvent-ils changer sans modification du Service lui-même ?

- [ ] Parce que le Service est redéployé
- [ ] Parce que les pods sont éphémères
- [ ] Parce que kube-proxy redémarre

### Question 9

Quelle situation justifie l’usage d’une startup probe ?

- [ ] Une application qui consomme beaucoup de CPU
- [ ] Une application exposée sur plusieurs ports
- [ ] Une application avec un temps de démarrage long

### Question 10

Quel est le principal risque d’une liveness probe trop agressive ?

- [ ] Une perte de données
- [ ] Un CrashLoopBackOff
- [ ] Une saturation réseau

### Question 11

Pourquoi Kubernetes force-t-il la séparation entre pods et stockage persistant ?

- [ ] Pour limiter l’usage disque
- [ ] Pour permettre la portabilité et l’auto-réparation
- [ ] Pour simplifier le réseau

### Question 12

Quel est le rôle exact d’un PersistentVolumeClaim ?

- [ ] Créer physiquement un disque
- [ ] Décrire un besoin de stockage persistant
- [ ] Chiffrer les données applicatives

### Question 13

Quel mécanisme garantit qu’un pod ne sera pas planifié sur un nœud donné par défaut ?

- [ ] NodeSelector
- [ ] Taint
- [ ] Affinité

### Question 14

Quelle est la fonction d’une toleration ?

- [ ] Supprimer un taint d’un nœud
- [ ] Autoriser un pod à ignorer un taint
- [ ] Forcer le scheduling sur un nœud

### Question 15

Quel problème l’anti-affinité cherche-t-elle principalement à résoudre ?

- [ ] Le manque de ressources CPU
- [ ] Le risque de point de défaillance unique
- [ ] Le routage réseau

### Question 16

Pourquoi un rollout peut-il rester bloqué lors d’une mise à jour applicative ?

- [ ] Parce que le Service n’est plus accessible
- [ ] Parce que la nouvelle version ne converge pas
- [ ] Parce que les pods existants sont protégés

### Question 17

Quelle est la bonne approche pour corriger une mise à jour applicative défaillante ?

- [ ] Modifier manuellement les pods
- [ ] Supprimer le Deployment
- [ ] Revenir à un état désiré valide (rollback)

### Question 18

Quel est le premier réflexe face à un pod en état `Pending` ?

- [ ] Consulter les logs du conteneur
- [ ] Vérifier les événements et contraintes de scheduling
- [ ] Redémarrer le cluster

### Question 19

Pourquoi les événements Kubernetes sont-ils essentiels au diagnostic ?

- [ ] Ils contiennent les logs applicatifs
- [ ] Ils expliquent les décisions et blocages du cluster
- [ ] Ils remplacent la supervision

### Question 20

Quelle affirmation décrit le mieux une bonne posture d’exploitation Kubernetes ?

- [ ] Corriger directement ce qui ne fonctionne pas
- [ ] Observer, comprendre les mécanismes, puis ajuster l’état désiré
- [ ] Automatiser toutes les actions manuelles
