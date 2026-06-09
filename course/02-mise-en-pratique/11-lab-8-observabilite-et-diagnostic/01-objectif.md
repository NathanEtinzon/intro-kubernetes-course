# Objectif

Ce lab fournit des scénarios d’incidents contrôlés pour entraîner les réflexes.

Apprendre un diagnostic “production-like” en utilisant uniquement :

- l’état des ressources (`kubectl get`),

- les détails (`kubectl describe`),

- les événements (`kubectl get events`),

- les logs (`kubectl logs`).

**Méthode de diagnostic recommandée** :

1. *Identifier l’état global* : `kubectl get pods,deploy,svc`

2. *Observer les détails de la ressource* : `kubectl describe pod <pod>`

3. *Lire les événements* : `kubectl get events --sort-by=.metadata.creationTimestamp`

4. *Lire les logs applicatifs* :
`kubectl logs <pod>kubectl logs <pod> --previous`

5. *Corréler les signaux* : état Kubernetes, événements, probes, logs applicatifs et configuration YAML.
