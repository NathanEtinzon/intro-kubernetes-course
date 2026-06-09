# Kubernetes, en une phrase (et pourquoi il existe)

Kubernetes est un **système de pilotage automatique pour applications conteneurisées**.

Il existe pour répondre à une limite structurelle de l’exploitation classique : au-delà d’un certain seuil, il devient impossible de gérer manuellement le placement des applications, leur redémarrage, leur montée en charge et leur exposition réseau.

Kubernetes part d’un postulat fondamental : **les pannes sont normales**. Il ne cherche pas à les éviter, mais à organiser le système pour **revenir automatiquement à un état attendu**.

**Pourquoi Kubernetes agit ainsi ?**

Comme pour les GPO, les outils de configuration déclarative ou les moteurs de conformité, on ne décrit pas une suite d’actions mais un **état cible**. Kubernetes observe ensuite le système en continu et agit pour réduire l’écart entre l’état réel et l’état désiré.
