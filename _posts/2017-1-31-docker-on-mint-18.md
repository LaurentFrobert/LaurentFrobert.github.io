--- 
layout: post
title: Installation de docker sur linux mint 18
--- 



1. installation :

    `sudo apt install docker.io`

2. lancement du service :

    `sudo systemctl start docker`

3. verif :

    `sudo systemctl status docker`

    docker.service - Docker Application Container Engine
       Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: e
       Active: active (running) since mar. 2017-01-31 23:13:23 CET; 3min 55s ago

4. ajout service docker au boot :

    `sudo systemctl enable docker`
    
    
Pour éviter de devoir être root ou utiliser sudo à chaque commande docker il faut rajouter l'utilisateur dans le group docker :
> problème de sécurité potentiel : d'après <http://askubuntu.com/questions/477551/how-can-i-use-docker-without-sudo>
> Warning: The docker group (or the group specified with -G) is root-equivalent; see [Docker Daemon Attack Surface details](https://docs.docker.com/engine/security/security/#/docker-daemon-attack-surface)

1. `sudo groupadd docker`

2. `sudo gpasswd -a ${USER} docker`

3. `sudo systemctl restart docker`

4. logout et login car l'ajout dans un nouveau groupe n'est actif qu'après

 
 
