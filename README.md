# Exercice Branches

## Créer un nouveau dépôt

Cloner la branch du dépôt git contenant le corrigé de l'exercice précédent à l'aide de la commande suivante :

`git clone -b 02-branch/main https://github.com/ConveyCode/git-exercices.git 02-branch`

## Créer une nouvelle branche

Utiliser la commande checkout pour créer un nouvelle branche `02-branch/feat/velo` en partant de `02-branch/main`

## Ajouter des commits dans 02-branch/feat/velo

Créer un fichier `velo.yaml` dans le dossier `yaml` avec comme contenu :

```
velo:
  marque: Look
  modele: 576
```

Ajouter ce fichier à l'index et créer un commit avec le message `feat: velo.yaml`

## Merge Fast Forward

Placer vous sur la branche `02-branch/main`

Visualiser votre historique pré-fusion avec `git log --oneline --graph --branches`

Utiliser la commande `git merge --ff-only 02-branch/feat/velo` pour fusionner la branche `02-branch/feat/velo` sur la branch `02-branch/main`

Visualiser votre historique post-fusion avec `git log --oneline --graph --branches`

Vous devriez voir une liste de commits linéaire comme celle-ci : 

```
* 19321be (HEAD -> 02-branch/main, 02-branch/feat/velo) feat: velo.yaml
* a8824de (origin/02-branch/main) refactor: move all yaml files to yaml directory
* 0d91fe4 fix(contact): ville
* 9c02cd0 fix(contact): prenom
* 20fc684 feat: societe.yaml
* d8d68cf feat: voiture.yaml
* 9ef4c19 feat: contact.yaml
* 7509e80 initial commit
```

## Merge sans Fast Forward

Défaire le dernier commit avec `git reset HEAD~1 --hard`

Visualiser votre historique pré-fusion avec `git log --oneline --graph --branches`

Utiliser la commande `git merge --no-ff 02-branch/feat/velo` pour fusionner la branche `02-branch/feat/velo` sur la branch `02-branch/main`

Visualiser votre historique post-fusion avec `git log --oneline --graph --branches`

Vous devriez voir une liste de commits non linéaire comme celle-ci : 

```
*   5c2fa4f (HEAD -> 02-branch/main) Merge branch '02-branch/feat/velo' into 02-branch/main
|\  
| * 19321be (02-branch/feat/velo) feat: velo.yaml
|/  
* a8824de (origin/02-branch/main) refactor: move all yaml files to yaml directory
* 0d91fe4 fix(contact): ville
* 9c02cd0 fix(contact): prenom
* 20fc684 feat: societe.yaml
* d8d68cf feat: voiture.yaml
* 9ef4c19 feat: contact.yaml
* 7509e80 initial commit
```

## Merge par défault

Défaire le dernier commit avec `git reset HEAD~1 --hard`

Sur la branch `02-branch/main` modifier le fichier `contact.yaml` en changeant par exemple le prénom.

Créer un commit `feat: fix prenom in contact.yaml` sur master

Visualiser votre historique pré-fusion avec `git log --oneline --graph --branches`

Utiliser la commande `git merge 02-branch/feat/velo` pour fusionner la branche `02-branch/feat/velo` sur la branch `02-branch/main`

Visualiser votre historique post-fusion avec `git log --oneline --graph --branches`

Vous devriez voir une liste de commits non linéaire comme celle-ci : 

```
*   d62dd47 (HEAD -> 02-branch/main) Merge branch '02-branch/feat/velo' into 02-branch/main
|\  
| * 19321be (02-branch/feat/velo) feat: velo.yaml
* | fc5ce99 feat: fix prenom in contact.yaml
|/  
* a8824de (origin/02-branch/main) refactor: move all yaml files to yaml directory
* 0d91fe4 fix(contact): ville
* 9c02cd0 fix(contact): prenom
* 20fc684 feat: societe.yaml
* d8d68cf feat: voiture.yaml
* 9ef4c19 feat: contact.yaml
* 7509e80 initial commit
```

## Rebase

Défaire le dernier commit avec `git reset HEAD~1 --hard`

Visualiser votre historique pré-fusion avec `git log --oneline --graph --branches`

Placer vous sur la branche `02-branch/feat/velo` avec `git checkout 02-branch/feat/velo`

Utiliser la commande `git rebase 02-branch/main` pour réécrire l'historique de la branche `02-branch/feat/velo` à partir de la branche `02-branch/main`

Visualiser votre historique suite au rebase avec `git log --oneline --graph --branches`

Placer vous sur la branche `02-branch/main` avec `git checkout 02-branch/main`

Utiliser la commande `git merge --ff-only 02-branch/feat/velo` pour fusionner la branche `02-branch/feat/velo` sur la branch `02-branch/main`

Visualiser votre historique post-fusion avec `git log --oneline --graph --branches`

Vous devriez voir une liste de commits linéaire comme celle-ci : 

```
* 4c7f2f5 (HEAD -> 02-branch/main, 02-branch/feat/velo) feat: velo.yaml
* fc5ce99 feat: fix prenom in contact.yaml
* a8824de (origin/02-branch/main) refactor: move all yaml files to yaml directory
* 0d91fe4 fix(contact): ville
* 9c02cd0 fix(contact): prenom
* 20fc684 feat: societe.yaml
* d8d68cf feat: voiture.yaml
* 9ef4c19 feat: contact.yaml
* 7509e80 initial commit
```
