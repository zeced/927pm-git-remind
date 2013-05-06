# Quelques commandes GIT à retenir

## Si vous avez :

> needs merge
> error: you need to resolve your current index first 

It's worth understanding what those error messages mean - needs merge and error: you need to resolve your current index first indicate that a merge failed, and that there are conflicts in those files. If you've decided that whatever merge you were trying to do was a bad idea after all, you can put things back to normal with:

    git reset --merge

## Si vous voulez :
> supprimer un fichier du repo sans supprimer le ichier localement 

    git rm --cached filename

> Remettre à zéro l'historique d'un projet (au moment de la livraison par exemple)

http://stackoverflow.com/questions/9683279/how-do-i-remove-all-version-history-for-a-git-github-repository

    Step 1: remove all history.

    rm -rf .git
    Step 2: reconstruct the Git repo with only the current content.

    git init
    git add .
    git commit -m "Initial commit"
    
    Step 3: push it to GitHub.
    git remote add origin <github-uri>
    git push -u --force origin master


> Rapatrier une branche distante

Il faut bien sûr que la branche soit présente sur le remote.

    git fetch
    git branch mabranche origin/mabranche

> Créer un tag

    git tag -a vx.x -m "message"

> Livrer un tag sur le serveur (à vérifier car cela va plus créer une branch sur le remote)

    git push delivery livraison:X.X (local)
    git checkout x.x (remote)


> AJOUTER UN REPO distante
    
    git remote add ALIASNAME -f <git-repo-url>

> merger un un repo de maniere récursive en appliquant nos modifs
    
    git merge ALIAS/master -s recursive -X ours

> revenir de 2 commit 
    
    git reset HEAD@{2}

> supprimer une branche distante

    git push origin :membership_processing

## Quelques ressources

http://nvie.com/posts/a-successful-git-branching-model/