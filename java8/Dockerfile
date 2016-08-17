# Image base
FROM ubuntu:16.10 

# mise à jour de l'image
RUN apt-get update && apt-get -y upgrade

# Install Oracle Java
RUN apt-get install -y --no-install-recommends openjdk-8-jdk 
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64