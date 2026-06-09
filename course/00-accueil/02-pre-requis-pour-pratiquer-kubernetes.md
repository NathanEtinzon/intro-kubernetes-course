# Pré-requis pour pratiquer Kubernetes

Cette partie décrit ce que Kubernetes **suppose déjà acquis** côté exploitation.

###### Conteneurs et Linux runtime

Un conteneur est avant tout un **processus Linux isolé**. Comprendre les signaux (SIGTERM, SIGKILL), stdout/stderr et le filesystem éphémère est indispensable pour interpréter les comportements Kubernetes.

###### Réseau et configuration

###### Réseau

Ports, IP éphémères, Services comme VIP logiques et Ingress comme reverse-proxy doivent être compris avant toute pratique.

###### Configuration

Le YAML est le support du modèle déclaratif. Labels, selectors, ConfigMaps et Secrets sont des mécanismes fondamentaux.

###### Outils et sécurité minimale

`kubectl` est avant tout un outil d’observation.

La sécurité minimale repose sur namespaces, RBAC et principe du moindre privilège.
