---
layout: post
title : Envoyer un signal à un container Docker
---

Pour envoyer un signal unix a une instance docker-compose :

exemple relancer la lecture de la conf de nginx :
docker-compose kill -s SIGHUP frontal


