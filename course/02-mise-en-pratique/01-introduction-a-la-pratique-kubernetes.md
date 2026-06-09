# Introduction à la pratique Kubernetes

La pratique Kubernetes ne consiste pas à “faire tourner une appli”, mais à **observer comment le cluster converge** vers l’état que tu déclares. L’idée des labs, c’est de faire voir les mécanismes internes à l’œuvre (controllers, scheduler, réseau, probes…), pas de réussir du premier coup.

La posture attendue est toujours la même : on **déclare un état simple**, on **observe l’état réel**, on lit les **événements** et les **logs**, puis on déduis quel composant Kubernetes réagit et pourquoi. En exploitation, c’est exactement ce qui fait la différence entre “je tente des trucs” et “je diagnostique”.

L’erreur est donc un **outil pédagogique** : on va volontairement provoquer des situations typiques (selector faux, image introuvable, probe trop agressive, pod en Pending…) pour comprendre ce que Kubernetes fait *automatiquement *et ce qu’il ne peut pas deviner.

Réflexe à garder pendant tous les labs : commencer par `kubectl get`, puis `kubectl describe`, ensuite `kubectl get events`, et enfin `kubectl logs`. Kubernetes fournit des **signaux** ; c’est vous qui faites le diagnostic en les recoupant.
