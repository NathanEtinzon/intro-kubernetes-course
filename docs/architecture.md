# Architecture Kubernetes

Kubernetes orchestre des applications conteneurisées à partir d'un état désiré décrit par l'utilisateur. Le cluster compare en continu cet état désiré avec l'état réel, puis agit pour rapprocher les deux.

## Control Plane

Le Control Plane porte les composants de pilotage du cluster. L'API Server expose l'interface d'administration, `etcd` stocke l'état, le scheduler choisit les noeuds d'exécution et les controllers réconcilient l'état réel avec l'état attendu.

Les accès au Control Plane doivent être strictement maîtrisés. Les comptes d'administration doivent être nominatifs, les droits doivent être limités, les actions sensibles doivent être tracées et les kubeconfig ne doivent pas être partagés publiquement.

## Workers

Les noeuds workers exécutent les Pods. Le kubelet échange avec l'API Server, le runtime de conteneurs exécute les conteneurs et kube-proxy participe à la connectivité réseau des Services.

Les noeuds doivent être maintenus à jour, durcis, supervisés et séparés selon les usages lorsque le contexte l'exige. Les charges de lab ne doivent pas être mélangées avec des charges de production.

## Objets manipulés dans le cours

Le cours introduit les Pods, Deployments, ReplicaSets, Services, labels, selectors, probes, PersistentVolumeClaims, namespaces, ServiceAccounts, Roles, RoleBindings, tolerations, node selectors, affinités, rollouts et diagnostics de base.

## Flux simplifié

1. L'utilisateur applique un manifest YAML avec `kubectl`.
2. L'API Server valide et enregistre l'objet.
3. Les controllers créent ou mettent à jour les ressources nécessaires.
4. Le scheduler affecte les Pods à des noeuds compatibles.
5. Les kubelets exécutent les Pods.
6. L'utilisateur observe l'état avec `kubectl get`, `kubectl describe` et `kubectl logs`.
