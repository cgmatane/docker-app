# Configuration du remote git

configuration reprise en partie de : https://blog.tristanfarneau.com/deployer-sur-un-dedie-avec-github/

```
git init --bare ~/billetterie.git
cd ~/billetterie.git/hooks
nano post-update // editer pour faire les actions que l'on veut
chmod +x post-update
```

après cela on peut ajouter ce nouveau repo depuis les postes :

Example de post-update dans se trouve dans répertoire

# Push directement du le site de la billetterie

## Ajouter le remote repo

aller de le répertoire de laravel sur votre poste et ajouter le remote repo :

```
git remote add demo ssh://realit@real-it.duckdns.org:10122/home/realit/billetterie.git
```

Après l'ajout il faut continuer de push sur github ==> `git push` si on a envie on peut aussi push sur le site de démonstration en faisant `git push demo master` il faut ensuite se connecter.

Après le push le site de la billetterie (https://billetterie.real-it.duckdns.org/accueil) se met à jour tout seul ! 


