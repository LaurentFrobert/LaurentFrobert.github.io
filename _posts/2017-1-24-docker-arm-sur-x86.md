--- 
layout: post
title: Docker executer une image ARM sur un proc x86
--- 
Pour pouvoir faire une compilation de paquet RPI par exemple

Méthode provenant de : 

<https://github.com/multiarch/qemu-user-static>

1. enregistrement des mapping binaire "magic code" <-> executable à lancer
  * docker run --rm --privileged multiarch/qemu-user-static:register --reset
2. test avec : 
  * docker run --rm -it resin/rpi-raspbian /bin/bash
  * arch : armv7l :-)

