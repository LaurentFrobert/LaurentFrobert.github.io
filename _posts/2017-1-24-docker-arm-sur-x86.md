--- 
layout: post
title: Executer une image ARM sur un proc x86 avec Docker
--- 
Pour pouvoir faire une compilation de paquet RPI par exemple

Méthode provenant de : 

<https://github.com/multiarch/qemu-user-static>

1. enregistrement des mapping binaire "magic code" <-> executable à lancer (attention la machine Hôte est altérée)
  * `docker run --rm --privileged multiarch/qemu-user-static:register --reset`
2. test avec : 
  * `docker run --rm -it resin/rpi-raspbian /bin/bash`
  * `arch : armv7l` :-)

