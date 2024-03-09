# Exercice Branches

Vous vous trouvez sur une branch de feature et souhaitz vous remettre à jour avec la branche main.

## Créer un nouveau dépôt

`git clone -b 03-remote/feat/velo https://github.com/ConveyCode/git-exercices.git 03-remote`

## Pull par défaut

Utiliser la commande pull pour mettre à jour la branche `03-remote/feat/velo` avec la branche `03-remote/main`

Visualiser votre historique avec `git log --oneline --graph --branches`

Vous devriez vous retrouvez comme ceci :

```
*   b6c7384 (HEAD -> 03-remote/feat/velo) Merge branch '03-remote/main' of https://github.com/ConveyCode/git-exercices into 03-remote/feat/velo
|\  
| * 83f75c4 (origin/03-remote/main) feat: fix prenom in contact.yaml
* | 3f5f0bb (origin/03-remote/feat/velo) feat: velo.yaml
|/  
* 60cfc50 refactor: move all yaml files to yaml directory
* c409c1e fix(contact): ville
* 74d48d5 fix(contact): prenom
* b30dd98 feat: societe.yaml
* 82ee407 feat: voiture.yaml
* edcf77c feat: contact.yaml
* 262589f initial commit

```
## Pull en rebase

Utiliser la commande pull avec l'option `--rebase` pour mettre à jour la branche `03-remote/feat/velo` avec la branche `03-remote/main`

Visualiser votre historique avec `git log --oneline --graph --branches`

Vous devriez vous retrouvez comme ceci :

```
* de46e3a (HEAD -> 03-remote/feat/velo) feat: velo.yaml
* 83f75c4 (origin/03-remote/main) feat: fix prenom in contact.yaml
* 60cfc50 refactor: move all yaml files to yaml directory
* c409c1e fix(contact): ville
* 74d48d5 fix(contact): prenom
* b30dd98 feat: societe.yaml
* 82ee407 feat: voiture.yaml
* edcf77c feat: contact.yaml
* 262589f initial commit
```

## Régler des conflits

Nous allons simuler le fait que la branch main a été mise à jour par un collaborateur

Depuis la branche `03-remote/feat/velo`, récupérer les modifications de la branche `03-remote/main-up-to-date`

Régler les conflits et faites un commit de merge

## Régler des conflits avec un rebase

Annulons les modifications précédentes avec `git reset --hard HEAD~1`

Refaison la mise à jour mais avec l'option `--rebase`

Visualiser votre historique.

Vous devriez vous retrouvez avec ceci :

```
* 00203b6 (HEAD -> 03-remote/feat/velo) feat: velo.yaml
* 608aa73 (origin/03-remote/main-up-to-date) feat: velo.yaml
* 83f75c4 (origin/03-remote/main) feat: fix prenom in contact.yaml
* 60cfc50 refactor: move all yaml files to yaml directory
* c409c1e fix(contact): ville
* 74d48d5 fix(contact): prenom
* b30dd98 feat: societe.yaml
* 82ee407 feat: voiture.yaml
* edcf77c feat: contact.yaml
* 262589f initial commit
```
