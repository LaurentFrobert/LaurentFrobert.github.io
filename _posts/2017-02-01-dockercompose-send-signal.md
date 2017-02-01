---
layout: post
title : Envoyer un signal à un container Docker
---

Pour envoyer un signal unix a une instance docker-compose :

exemple relancer la lecture de la conf de nginx : (ici "frontal" est le nom du service dans le docker-compose.yml, le nginx)

`docker-compose kill -s SIGHUP frontal`


