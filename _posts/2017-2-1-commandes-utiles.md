---
layout: post
title : Liste de commandes unix utiles
---


* consommation mémoire d'un process (ou plusieurs) (ici tous les python)

  source : <https://www.vincentliefooghe.net/content/r%C3%A9cup%C3%A9rer-la-consommation-m%C3%A9moire-dun-process-sous-linux>

  `ps aux | grep python | grep -v grep | awk 'BEGIN { sum=0 } {sum=sum+$6; } END {printf("Taille RAM utilisée: %s Mo\n",sum / 1024)}'`
  
* Docker : clear logs

  source : <https://yuks.me/blog/quick-clear-docker-logs>, les * correspondent aux id des containers 

  `truncate -s 0 /var/lib/docker/containers/*/*-json.log`

* Docker : remove stopped container

  `docker rm $(docker ps -a -q)`

* Docker : Remove all intermediate images

  `docker rmi $(docker images -f "dangling=true" -q)`

* Voir en temps réel le nombre de connexion réseau

  `watch ss -r -a -s`

* pour voir les fichier ouvert (ici avec -i interface reseau, equivalent a netstat)

  `sudo watch -n 1 lsof -i`

  


