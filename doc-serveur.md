# Documentation configuration serveur

## Billetterie

`docker-compose/laravel`
conteneurs :

- nginx-lara
- mysql
- php-fpm7.2

sources du site dans `~/billetterie` de l'utilisateur

## Letsencrypt

`docker-compose/letsencrypt`

pour ajouter un sous-domaine (exemple pour ajouter "lesousdomaine") :

- éditer `docker-compose.yml` ajouter le domaine dans `SUBDOMAINS = ... , lesousdomaine, `
- fermer et enregister l'éditeur
-  ` cd docker-compose/letsencrypt/config/nginx/proxy-confs`
- `cp billetterie.subdomain.conf lesousdomaine.subdomain.conf`
- `sudo nano lesousdomaine.subdomain.conf` 
- modifier les valeurs  : `server_name lesousdomaine.*` , `location ~ (/lesousdomaine)?socket`
- changer `proxy_pass` du bloc `location /` pour lui spécifier le port local (exemple : `proxy_pass http://localhost:8080`)
- cd `~/dockerapp/docker-compose/letsencrypt`
- `sudo docker-compose up -d`
- attendre quelques minutes pour que le conteneur se rebuild et démarre
- le nouveau sous-domaine est disponible ! 

