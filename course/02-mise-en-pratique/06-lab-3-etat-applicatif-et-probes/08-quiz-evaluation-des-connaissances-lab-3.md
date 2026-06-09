# Évaluation des connaissances - Lab 3

Les réponses attendues sont indiquées dans le fichier : [../questions/banque-questions.md](../questions/banque-questions.md).

## Introduction

Ce questionnaire évalue la compréhension des mécanismes vus dans le lab 3.

## Paramètres

- Note maximale : 3.00000
- Somme des points : 3.00000
- Nombre de questions : 3

## Questions

### Question 1

Quelle est la différence entre un pod `Running` et un pod `Ready` ?

- [ ] `Running` signifie que l’application est disponible
- [ ] `Ready` conditionne le routage du trafic 
- [ ] Les deux états sont équivalents

### Question 2

Pourquoi une liveness probe mal configurée peut-elle provoquer un CrashLoopBackOff ?

- [ ] Parce qu’elle empêche le scheduling
- [ ] Parce qu’elle tue le conteneur avant qu’il ne soit réellement prêt 
- [ ] Parce qu’elle bloque le réseau

### Question 3

À quoi sert une startup probe ?

- [ ] À remplacer la readiness probe
- [ ] À protéger la phase de démarrage des applications lentes 
- [ ] À surveiller la mémoire du conteneur
