# Introduction à Kubernetes

Ce dépôt publie un cours d'introduction à Kubernetes sous deux formes complémentaires : l'archive Moodle restaurable et un export Markdown proche de la structure pédagogique originale.

Le cours introduit les concepts fondamentaux de Kubernetes, puis les met en pratique au travers de labs progressifs : modèle déclaratif, architecture Control Plane et Workers, Pods, Deployments, Services, probes, stockage persistant, RBAC, scheduling, rollout/rollback, observabilité et diagnostic.

## Contenu principal

- Archive Moodle : `moodle/intro-kubernetes-course.mbz`
- Export Markdown complet : [course/README.md](course/README.md)
- Labs pratiques : [labs/](labs/)
- Documentation complémentaire : [docs/](docs/)
- Captures : [screenshots/](screenshots/)

## Parcours Moodle exporté

L'export Markdown reprend les sections et sous-sections du cours Moodle original : accueil, compréhension de Kubernetes, mise en pratique, évaluation finale et références. Les quiz sont exportés avec leurs questions afin de faciliter la maintenance pédagogique hors Moodle.

Les informations d'identification non nécessaires à une diffusion publique ont été neutralisées dans les fichiers Markdown. L'archive `.mbz` reste l'artefact source et doit être contrôlée avant toute publication externe.

## Importer le cours dans Moodle

1. Télécharger le fichier `moodle/intro-kubernetes-course.mbz`.
2. Se connecter à Moodle avec un compte autorisé à restaurer des cours.
3. Créer un nouveau cours ou choisir un cours existant.
4. Utiliser la fonction de restauration de cours.
5. Importer le fichier `.mbz`.
6. Contrôler les sections, activités, quiz, médias et droits après restauration.

La procédure détaillée est disponible dans [docs/import-moodle.md](docs/import-moodle.md).

## Utiliser les labs sans Moodle

Chaque dossier de lab contient un README proche des étapes Moodle originales. Les manifests YAML fournis dans le dépôt servent de support pratique hors Moodle et doivent être relus avant exécution.

Avant toute manipulation, vérifier le contexte actif et utiliser un cluster de lab isolé :

```bash
kubectl config current-context
kubectl cluster-info
kubectl get nodes
```

Ne pas exécuter ces labs sur un cluster de production. Les accès doivent rester limités au strict nécessaire, les ressources de test doivent être nettoyées, et aucun secret réel ne doit être ajouté au dépôt.

## Licence et réutilisation

Sauf mention contraire, ce contenu pédagogique est publié sous licence Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International, `CC BY-NC-SA 4.0`.

Voir [LICENSE](LICENSE).
