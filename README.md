# Exercice Commit

## Créer un nouveau dépôt

Créer un dossier `exercice-git` sur votre disque

Dans un terminal comme Git Bash, utiliser la commande git pour créer un nouveau repository dans `exercice-git`

## Créer un commit initial

Une fois le dépôt créé, ajouter un fichier `contact.yaml` dans le répertoire `exercice-git` avec le contenu suivant :

```
contact:
  prenom: Jean
  nom: Dupont
  ville: Paris
```

Ajouter cette modification au staging area, puis créer votre commit initial avec comme message `feat: contact.yaml`

## Ajouter des modifications

Créer 2 nouveaux fichiers, `voiture.yaml` :

```
voiture:
  marque: Renault
  modele: Clio
```

Et société `societe.yaml` :

```
societe:
  nom: Orange
  ville: Guyancourt
```

Créer les 2 fichiers en premier, puis créer 2 commits (un par fichier) avec comme messages `feat: voiture.yaml` et `feat: societe.yaml` 

## Utiliser les ajouts partiels

Dans le fichier `contact.yaml`, remplacer le prénom `Jean` par `Eric` et la ville `Paris` par `Bordeaux`.

Créer 2 commits (1 pour chaque ligne modifiée) avec comme messages : `fix(contact): prenom` et `fix(contact): ville`

## Déplacer des fichiers

Utiliser la commande `git mv` pour déplacer les 3 fichiers dans un dossier `yaml` (vous devez créer le dossier `yaml` d'abord)

Créer 1 commit avec comme message : `refactor: move yaml files to yaml folder`.

## Renommer le dernier commit

Renommer le dernier commit via la commande `git commit --amend`, l'éditeur configuré doit s'ouvrir et vous pourrez changer le message pour : `refactor: move all yaml files to yaml directory`.

## Supprimer un fichier

Utiliser la commande `git rm` pour supprimer le fichier `voiture.yaml`

Créer 1 commit avec comme message : `refactor!: delete voiture.yaml`.

Attention sur zsh et bash (et donc Git Bash), il faut échapper le caractère `!` : `git commit -m "refactor\!: delete voiture.yaml"`

## Revenir en arrière

Utiliser la commande `git reset HEAD~1 --hard` pour annuler le dernier commit et faire réapparaitre le fichier.

## Afficher des différences

Utiliser la commande `git show` pour afficher le patch du dernier commit

Utiliser la commande `git diff` pour afficher les 2 derniers commits qui portent sur `contact.yaml` (ceux qui ont été créés à partir de la commande `git add -p`)
