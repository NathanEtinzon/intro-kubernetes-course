# Banque de questions

Export des questions multichoix présentes dans l'archive Moodle. Les réponses attendues sont marquées pour permettre la maintenance du cours.

## Test de positionnement

### Question 1

Quel est l’objectif principal de Kubernetes ?

- [ ] Remplacer Docker en tant que moteur de conteneurs
- [x] Orchestrer automatiquement l’exécution d’applications conteneurisées (réponse attendue)
- [ ] Fournir un environnement de développement clé en main

### Question 2

Dans Kubernetes, que signifie le fait de “déclarer un état” ?

- [ ] Décrire une suite d’actions à exécuter dans l’ordre
- [x] Indiquer à Kubernetes ce que l’on souhaite obtenir, pas comment y parvenir (réponse attendue)
- [ ] Écrire un script exécuté directement sur les nœuds

### Question 3

Quel composant est la *source de vérité* de l’état du cluster Kubernetes ?

- [ ] kube-scheduler
- [ ] kube-apiserver
- [x] etcd (réponse attendue)

### Question 4

Pourquoi un pod supprimé manuellement est-il généralement recréé automatiquement ?

- [ ] Parce que le kubelet redémarre systématiquement les conteneurs
- [x] Parce qu’un controller cherche à faire converger l’état réel vers l’état désiré (réponse attendue)
- [ ] Parce que les pods sont persistants par défaut

### Question 5

Quelle affirmation décrit le mieux un pod Kubernetes ?

- [ ] Un serveur virtuel durable avec une IP fixe
- [x] Une unité d’exécution éphémère pouvant contenir un ou plusieurs conteneurs (réponse attendue)
- [ ] Un conteneur Docker avec des permissions élevées

### Question 6

Quelle est la fonction principale d’un Service Kubernetes ?

- [ ] Stocker les données de l’application
- [x] Fournir une adresse réseau stable vers des pods dynamiques (réponse attendue)
- [ ] Surveiller l’état de santé des conteneurs

### Question 7

Quelle est la différence essentielle entre une readiness probe et une liveness probe ?

- [ ] La readiness probe décide si le pod doit être redémarré
- [ ] La liveness probe décide si le pod peut recevoir du trafic
- [x] La readiness probe conditionne le routage du trafic, la liveness le redémarrage (réponse attendue)

### Question 8

Pourquoi les données écrites dans le système de fichiers d’un conteneur sont-elles perdues lors de la recréation d’un pod ?

- [ ] Parce que Kubernetes supprime systématiquement les volumes
- [x] Parce que le système de fichiers du conteneur est éphémère (réponse attendue)
- [ ] Parce que les permissions Linux sont réinitialisées

### Question 9

Quel est le bon ordre de raisonnement pour diagnostiquer un problème Kubernetes ?

- [ ] logs → events → describe → get
- [x] get → describe → events → logs (réponse attendue)
- [ ] describe → logs → get → events

## Connaissances conceptuelles

### Question 10

Quel est le rôle principal du *control plane* dans un cluster Kubernetes ?

- [ ] Exécuter les conteneurs applicatifs
- [x] Décider et maintenir l’état désiré du cluster (réponse attendue)
- [ ] Assurer le routage réseau entre les pods

### Question 11

Pourquoi Kubernetes sépare-t-il strictement le plan de décision (control plane) et le plan d’exécution (worker nodes) ?

- [ ] Pour améliorer les performances réseau
- [x] Pour permettre la résilience, la cohérence et l’automatisation à grande échelle (réponse attendue)
- [ ] Pour simplifier la configuration des conteneurs

### Question 12

Quel est le rôle exact du kube-apiserver ?

- [ ] Lancer et arrêter les conteneurs sur les nœuds
- [ ] Orchestrer le placement des pods
- [x] Centraliser, valider et exposer l’état du cluster via l’API (réponse attendue)

### Question 13

Pourquoi etcd est-il considéré comme un composant critique de Kubernetes ?

- [ ] Il exécute les contrôleurs internes
- [x] Il contient l’état complet et désiré du cluster (réponse attendue)
- [ ] Il gère le réseau entre les pods

### Question 14

Dans le modèle déclaratif Kubernetes, que représente le champ `spec` d’une ressource ?

- [ ] L’état réel observé par le cluster
- [ ] Les actions que Kubernetes doit exécuter
- [x] L’état désiré défini par l’utilisateur (réponse attendue)

### Question 15

Pourquoi la modification manuelle d’un pod (suppression, changement direct) est-elle généralement inefficace ?

- [ ] Parce que les pods sont persistants
- [ ] Parce que le kubelet empêche toute modification manuelle
- [x] Parce qu’un controller cherche en permanence à faire converger l’état réel vers l’état désiré (réponse attendue)

### Question 16

Quelle affirmation décrit le mieux la nature d’un pod Kubernetes ?

- [ ] Une machine virtuelle légère avec stockage persistant
- [x] Une unité d’exécution éphémère regroupant un ou plusieurs conteneurs (réponse attendue)
- [ ] Un conteneur Docker avec des privilèges élevés

### Question 17

Pourquoi Kubernetes introduit-il l’objet Service ?

- [ ] Pour sécuriser les communications réseau
- [x] Pour fournir une adresse réseau stable vers des pods éphémères (réponse attendue)
- [ ] Pour surveiller l’état de santé des applications

### Question 18

Quel est le rôle fondamental des controllers dans Kubernetes ?

- [ ] Superviser les performances du cluster
- [ ] Exécuter les applications utilisateurs
- [x] Comparer l’état réel et l’état désiré et corriger les écarts (réponse attendue)

### Question 19

Quel comportement est attendu si un champ est modifié manuellement dans `status` d’une ressource ?

- [ ] Kubernetes applique la modification
- [ ] Kubernetes ignore la ressource
- [x] Kubernetes écrase la modification (réponse attendue)

## Lab 1

### Question 20

Pourquoi un pod supprimé manuellement est-il recréé automatiquement ?

- [ ] Parce que le kubelet redémarre toujours les conteneurs
- [x] Parce qu’un controller cherche à faire converger l’état réel vers l’état désiré (réponse attendue)
- [ ] Parce que les pods sont persistants par défaut

### Question 21

Quel objet Kubernetes définit le nombre de pods attendus ?

- [ ] Pod
- [x] ReplicaSet (réponse attendue)
- [ ] Service

### Question 22

Pourquoi supprimer un pod n’est-il pas une action corrective durable ?

- [ ] Parce que le pod est protégé par le scheduler
- [ ] Parce que Kubernetes interdit les suppressions manuelles
- [x] Parce que l’état désiré n’a pas été modifié (réponse attendue)

## Lab 2

### Question 23

Pourquoi Kubernetes utilise-t-il des Services pour exposer les applications ?

- [ ] Pour chiffrer automatiquement le trafic
- [x] Pour fournir une adresse réseau stable malgré des pods éphémères (réponse attendue)
- [ ] Pour remplacer les firewalls

### Question 24

Sur quoi repose le routage d’un Service vers des pods ?

- [ ] Les adresses IP des nœuds
- [ ] Les noms des pods
- [x] Les labels et selectors (réponse attendue)

### Question 25

Pourquoi un Service peut-il exister sans router aucun trafic ?

- [ ] Parce que le Service est désactivé
- [x] Parce qu’aucun endpoint ne correspond à son selector (réponse attendue)
- [ ] Parce que le kube-proxy est arrêté

## Lab 3

### Question 26

Quelle est la différence entre un pod `Running` et un pod `Ready` ?

- [ ] `Running` signifie que l’application est disponible
- [x] `Ready` conditionne le routage du trafic (réponse attendue)
- [ ] Les deux états sont équivalents

### Question 27

Pourquoi une liveness probe mal configurée peut-elle provoquer un CrashLoopBackOff ?

- [ ] Parce qu’elle empêche le scheduling
- [x] Parce qu’elle tue le conteneur avant qu’il ne soit réellement prêt (réponse attendue)
- [ ] Parce qu’elle bloque le réseau

### Question 28

À quoi sert une startup probe ?

- [ ] À remplacer la readiness probe
- [x] À protéger la phase de démarrage des applications lentes (réponse attendue)
- [ ] À surveiller la mémoire du conteneur

## Lab 4

### Question 29

Pourquoi les données écrites dans le système de fichiers d’un conteneur sont-elles perdues ?

- [ ] Parce que Kubernetes supprime les fichiers au redémarrage
- [x] Parce que le conteneur est lié au cycle de vie du pod (réponse attendue)
- [ ] Parce que les permissions Linux sont réinitialisées

### Question 30

Quel est le rôle d’un PersistentVolumeClaim (PVC) ?

- [ ] Définir un quota CPU
- [x] Découpler le stockage du cycle de vie des pods (réponse attendue)
- [ ] Exposer une application sur le réseau

### Question 31

Que se passe-t-il si un pod utilisant un PVC est recréé ?

- [ ] Les données sont perdues
- [ ] Le PVC est supprimé
- [x] Les données restent accessibles (réponse attendue)

## Lab 5

### Question 34

Quel est le rôle principal d’un namespace ?

- [ ] Sécuriser le réseau
- [x] Isoler logiquement les ressources (réponse attendue)
- [ ] Augmenter les performances

### Question 35

À quoi sert un ServiceAccount dans Kubernetes ?

- [ ] À créer des utilisateurs humains
- [x] À représenter une identité applicative (réponse attendue)
- [ ] À stocker des secrets

## Lab 6

### Question 36

Quel outil permet de vérifier les droits RBAC sans tester en production ?

- [ ] `kubectl exec`
- [x] `kubectl auth can-i` (réponse attendue)
- [ ] kubectl logs

### Question 37

Pourquoi Kubernetes est-il dit “nativement multi-tenant” ?

- [ ] Parce qu’il supporte plusieurs clusters
- [x] Parce qu’il isole applications et permissions via namespaces et RBAC (réponse attendue)
- [ ] Parce qu’il chiffre tout le trafic

### Question 38

À quoi sert un taint sur un nœud ?

- [ ] À forcer le placement des pods
- [x] À interdire le scheduling par défaut (réponse attendue)
- [ ] À augmenter la priorité du nœud

### Question 39

Que permet une toleration ?

- [ ] De supprimer un taint
- [x] D’autoriser un pod à être planifié malgré un taint (réponse attendue)
- [ ] De redémarrer un pod

### Question 40

Pourquoi un pod peut-il rester en état `Pending` ?

- [ ] Parce que l’image n’existe pas
- [x] Parce qu’aucune contrainte de scheduling n’est satisfaite (réponse attendue)
- [ ] Parce que le Service est absent

### Question 41

Quel est l’objectif principal de l’anti-affinité ?

- [ ] Regrouper les pods sur un même nœud
- [x] Répartir les pods pour améliorer la disponibilité (réponse attendue)
- [ ] Réduire la consommation mémoire

## Lab 7

### Question 42

Quel objet Kubernetes gère les mises à jour progressives ?

- [ ] Pod
- [ ] ReplicaSet
- [x] Deployment (réponse attendue)

### Question 43

Quelle est la bonne manière de corriger une régression applicative ?

- [ ] Modifier directement les pods
- [x] Corriger l’état désiré et effectuer un rollback (réponse attendue)
- [ ] Supprimer le cluster

### Question 44

Quelle commande permet de revenir à une version précédente ?

- [ ] kubectl delete pod
- [x] kubectl rollout undo (réponse attendue)
- [ ] kubectl scale

## Lab 8

### Question 45

Quel est l’ordre de diagnostic recommandé en Kubernetes ?

- [ ] logs → events → describe → get
- [x] get → describe → events → logs (réponse attendue)
- [ ] events → logs → get → describe

### Question 46

À quoi servent principalement les événements Kubernetes ?

- [ ] À stocker les logs applicatifs
- [x] À expliquer pourquoi Kubernetes ne converge pas (réponse attendue)
- [ ] À mesurer les performances

### Question 47

Quelle information fournit `kubectl logs` ?

- [ ] Les actions des controllers
- [x] Les messages de l’application dans le conteneur (réponse attendue)
- [ ] L’état du scheduler

# Évaluation finale

### Question 48

Pourquoi le diagnostic repose-t-il sur la corrélation de plusieurs sources ?

- [ ] Parce qu’aucune commande n’est fiable seule
- [ ] Parce que Kubernetes ne fournit jamais d’erreurs
- [x] Parce que chaque signal explique une partie du problème (réponse attendue)

### Question 49

Pourquoi Kubernetes impose-t-il l’usage d’une API centrale (kube-apiserver) pour toute modification du cluster ?

- [ ] Pour améliorer les performances réseau
- [x] Pour garantir cohérence, sécurité et traçabilité de l’état (réponse attendue)
- [ ] Pour empêcher toute automatisation externe

### Question 50

Quel comportement est attendu si un champ est modifié manuellement dans `status` d’une ressource ?

- [ ] Kubernetes applique la modification
- [ ] Kubernetes ignore la ressource
- [x] Kubernetes écrase la modification (réponse attendue)

### Question 51

Quelle relation existe entre Deployment et ReplicaSet ?

- [ ] Le Deployment remplace définitivement le ReplicaSet
- [ ] Le ReplicaSet pilote le Deployment
- [x] Le Deployment crée et gère les ReplicaSets (réponse attendue)

### Question 52

Pourquoi Kubernetes ne fournit-il pas directement l’état métier d’une application ?

- [ ] Pour des raisons de sécurité
- [x] Parce qu’il est volontairement agnostique de l’application (réponse attendue)
- [ ] Parce que etcd ne peut pas stocker ces informations

### Question 53

Quel élément déclenche réellement une action de correction dans Kubernetes ?

- [ ] Une commande kubectl
- [x] Un écart entre état réel et état désiré (réponse attendue)
- [ ] Une alerte de supervision

### Question 54

Dans un manifest Deployment, pourquoi `spec.selector.matchLabels` est-il critique ?

- [ ] Il définit les ports exposés
- [x] Il lie le Deployment aux pods qu’il contrôle (réponse attendue)
- [ ] Il active l’auto-scaling

### Question 55

Quel est l’effet direct d’un selector incorrect dans un Service ?

- [ ] Le Service ne peut pas être créé
- [x] Le Service existe mais ne route vers aucun pod (réponse attendue)
- [ ] Les pods sont supprimés

### Question 56

Pourquoi les endpoints d’un Service peuvent-ils changer sans modification du Service lui-même ?

- [ ] Parce que le Service est redéployé
- [x] Parce que les pods sont éphémères (réponse attendue)
- [ ] Parce que kube-proxy redémarre

### Question 57

Quelle situation justifie l’usage d’une startup probe ?

- [ ] Une application qui consomme beaucoup de CPU
- [ ] Une application exposée sur plusieurs ports
- [x] Une application avec un temps de démarrage long (réponse attendue)

### Question 58

Quel est le principal risque d’une liveness probe trop agressive ?

- [ ] Une perte de données
- [x] Un CrashLoopBackOff (réponse attendue)
- [ ] Une saturation réseau

### Question 59

Pourquoi Kubernetes force-t-il la séparation entre pods et stockage persistant ?

- [ ] Pour limiter l’usage disque
- [x] Pour permettre la portabilité et l’auto-réparation (réponse attendue)
- [ ] Pour simplifier le réseau

### Question 60

Quel est le rôle exact d’un PersistentVolumeClaim ?

- [ ] Créer physiquement un disque
- [x] Décrire un besoin de stockage persistant (réponse attendue)
- [ ] Chiffrer les données applicatives

### Question 61

Quel mécanisme garantit qu’un pod ne sera pas planifié sur un nœud donné par défaut ?

- [ ] NodeSelector
- [x] Taint (réponse attendue)
- [ ] Affinité

### Question 62

Quelle est la fonction d’une toleration ?

- [ ] Supprimer un taint d’un nœud
- [x] Autoriser un pod à ignorer un taint (réponse attendue)
- [ ] Forcer le scheduling sur un nœud

### Question 63

Quel problème l’anti-affinité cherche-t-elle principalement à résoudre ?

- [ ] Le manque de ressources CPU
- [x] Le risque de point de défaillance unique (réponse attendue)
- [ ] Le routage réseau

### Question 64

Pourquoi un rollout peut-il rester bloqué lors d’une mise à jour applicative ?

- [ ] Parce que le Service n’est plus accessible
- [x] Parce que la nouvelle version ne converge pas (réponse attendue)
- [ ] Parce que les pods existants sont protégés

### Question 65

Quelle est la bonne approche pour corriger une mise à jour applicative défaillante ?

- [ ] Modifier manuellement les pods
- [ ] Supprimer le Deployment
- [x] Revenir à un état désiré valide (rollback) (réponse attendue)

### Question 66

Quel est le premier réflexe face à un pod en état `Pending` ?

- [ ] Consulter les logs du conteneur
- [x] Vérifier les événements et contraintes de scheduling (réponse attendue)
- [ ] Redémarrer le cluster

### Question 67

Pourquoi les événements Kubernetes sont-ils essentiels au diagnostic ?

- [ ] Ils contiennent les logs applicatifs
- [x] Ils expliquent les décisions et blocages du cluster (réponse attendue)
- [ ] Ils remplacent la supervision

### Question 68

Quelle affirmation décrit le mieux une bonne posture d’exploitation Kubernetes ?

- [ ] Corriger directement ce qui ne fonctionne pas
- [x] Observer, comprendre les mécanismes, puis ajuster l’état désiré (réponse attendue)
- [ ] Automatiser toutes les actions manuelles
