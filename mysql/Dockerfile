# Image base
FROM ubuntu:16.10 

# mise à jour de l'image
RUN apt-get update && apt-get -y upgrade

#création d'un repertoire de travail 
WORKDIR /code

#installation de mysql serveur et client en mode non interactive
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get -yq install mysql-server mysql-client
RUN rm -rf /var/lib/apt/lists/*

#copie du fichier de configuration de mysql
COPY my.cnf /etc/mysql/my.cnf
RUN if [ ! -f /usr/share/mysql/my-default.cnf ] ; then cp /etc/mysql/my.cnf /usr/share/mysql/my-default.cnf; fi

# Exposition du port 3306
EXPOSE 3306

RUN apt-get update
# Installation du supervisor
RUN apt-get -y install supervisor

# Copie du fichier de configuration  supervisor.conf pour le demarrage de mysql
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
VOLUME ["/etc/mysql" ,"/var/lib/mysql"]

# Execution mysql service
CMD ["/usr/bin/supervisord"]
