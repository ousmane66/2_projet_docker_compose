# projet_docker_compose
docker compose MySQL, tomcat, et java dans des conteneurs séparés
Dans ce projet j'ai utilisé docker-compose pour lier les conteneurs decrite dans des dockerfiles differente.
le repertoire qui comporte le dockerfile pour le conteneur tomcat déploi et execute le fichier pom.xml.
Apres execution il va éssayer de se connecter au conteneur où est installé le serveur mysql via l'adresse IP 172.17.0.3:3306 pour créer et initialiser  la base de données distante.

Les dockerfile sont commentés pour plus d'eclairecissement. 

#pour executer le projet:

commande: docker-compose up -d 
