# Objectif

Comprendre comment Kubernetes expose des applications dont les pods sont **éphémères**, et pourquoi le routage repose sur des abstractions logiques (Services) plutôt que sur des IP fixes.

À l’issue de ce lab, vous devez comprendre :

- le rôle des labels et selectors,

- pourquoi une IP de pod ne doit jamais être utilisée comme point d’entrée,

- comment diagnostiquer un Service qui ne route plus.
