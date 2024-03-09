# Exercice Rebase Interactif

L'objectif est d'utiliser la commande `rebase` de manière interactive pour simplifier le plus possible l'historique.

## Déroulé

* Cloner le projet avec la commande `git clone https://gitlab.com/exercices-git/rebase-interactif.git`
* Utiliser la commande `git rebase -i --root` pour démarrer le rebase interactif (en temps normal on utiliserait `git rebase -i` puisque les commits n'auraient pas été poussés vers le dépôt public)

## Résultat

On veut que l'historique final ressemble à :

```
736fde1 feat: voiture.yaml
55c737a feat: societe.yaml
569e625 feat: contact.yaml
94d6bdc chore: .gitkeep logs
cac51b8 chore: .gitignore
1523eaf feat: enoncé de l'exercice
61f4adb chore: commit initial
```

L'ordre et les messages de commit sont importants. Chaque commit ne doit porter que sur un seul fichier (à vérifier avec `git show cac51b8` où `cac51b8` serait le commit hash). Les commit hashes seront bien sûr différents.
