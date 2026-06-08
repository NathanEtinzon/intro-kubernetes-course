# Documentation publique

Cette documentation complète la sauvegarde Moodle. Elle permet de consulter les prérequis, l'architecture générale, les informations d'import Moodle et les repères d'évaluation sans restaurer immédiatement le cours.

La version Moodle reste l'artefact principal. Les documents présents ici sont pensés comme support public complémentaire et comme base pour une éventuelle publication GitHub Pages.

## Accès rapide

- [Pré-requis techniques](prerequis.md)
- [Architecture Kubernetes](architecture.md)
- [Évaluation](evaluation.md)
- [Import Moodle](import-moodle.md)

## Utilisation directe

Les labs peuvent être consultés depuis le dossier `../labs/`. Chaque lab contient des consignes et un fichier `manifests.yaml` réutilisable sur un cluster de test.

Avant toute exécution, vérifier le contexte `kubectl`, relire les manifests, éviter les clusters de production et supprimer les ressources de test à la fin des manipulations.
