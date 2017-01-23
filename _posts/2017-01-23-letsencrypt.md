---
layout: post
title: Mise en place certificat gratuit SSL avec let's encrypt
---
Avec docker et un nginx

Suivant l'article : 

<https://devsidestory.com/lets-encrypt-with-docker/>

commentaires :

* pas réussi à utiliser le fichier docker-compose fourni (problème avec les volumes)
* la ligne de génération du certificat temporaire (openssl xxxx) ne sert donc pas (car stockées dans l'image, et ensuite je monte un volume externe donc perte du cert tempo)
* attention : pas de certificat tempo donc avant d'avoir le premier certificat il ne faut pas de bloc server (443 )avec ssl_certificate dans le fichier nginx.conf

