# Introduction

Cette première partie pose les **fondations conceptuelles** nécessaires pour comprendre Kubernetes en tant que système distribué d’orchestration. L’objectif n’est pas de savoir “utiliser Kubernetes”, mais de comprendre **comment Kubernetes pense et agit**.

Kubernetes est issu de travaux industriels menés par Google bien avant l’essor du cloud moderne. Dès les années 2000, Google développe des orchestrateurs internes (notamment **Borg**, puis **Omega**) pour exécuter et maintenir des charges applicatives massives sur des infrastructures où la défaillance matérielle est fréquente.
Kubernetes est la **mise à disposition open-source** de ces principes d’orchestration, adaptée à l’écosystème des conteneurs et publiée en 2014. Le projet est ensuite confié à la **Cloud Native Computing Foundation (CNCF)** afin d’en garantir l’indépendance et la pérennité.

Le nom *Kubernetes* provient du grec *kubernḗtēs*, désignant le pilote d’un navire. Cette métaphore illustre son rôle : maintenir un cap fonctionnel malgré un environnement instable. L’abréviation **K8s** suit une convention courante consistant à conserver la première et la dernière lettre d’un mot, en remplaçant les lettres intermédiaires par leur nombre.

Avec l’adoption croissante de Kubernetes, plusieurs distributions ont émergé. **K3s** est une déclinaison allégée, pensée pour des environnements contraints (edge, laboratoires, sites distants). Elle conserve la compatibilité avec l’API Kubernetes tout en réduisant drastiquement la complexité opérationnelle et les besoins en ressources. K3s ne remet pas en cause le modèle Kubernetes : il en est une implémentation optimisée.

Kubernetes devient pertinent lorsque les contraintes opérationnelles dépassent les capacités d’une gestion manuelle ou semi-automatisée : multiplication des services, besoins de haute disponibilité, déploiements fréquents, équipes multiples, ou infrastructures distribuées. À l’inverse, son adoption n’est pas justifiée pour des architectures simples, statiques ou à faible enjeu de résilience. Kubernetes répond avant tout à un **problème d’échelle et de gouvernance**, pas à un besoin fonctionnel isolé.
