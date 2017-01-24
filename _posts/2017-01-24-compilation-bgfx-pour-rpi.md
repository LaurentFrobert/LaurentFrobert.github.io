--- 
layout: post
title: Compilation BGFX pour RPI
--- 
Avec raspbian sur une machine x86
bgfx : <https://github.com/bkaradzic/bgfx>
doc compilation : <https://bkaradzic.github.io/bgfx/build.html>

j'utilise la méthode "docker arm sur x86" voir autre post 

puis :

1. docker run -it resin/raspbian /bin/bash
2. apt-get update
3. apt-get install  libraspberrypi-bin libraspberrypi-dev build-essential git
4. d'après la doc il faut (git clone git://github.com/bkaradzic/bx.git) mais il semble que la commande genie dans bx ne soit pas pour du rpi
cette commande permet de generer les makefile de bgfx

5. donc on compile nous meme genie :
* git clone https://github.com/bkaradzic/genie
* cd genie
* make
* le binaire "genie" se trouve dans : /genie/bin/linux/


6. git clone git://github.com/bkaradzic/bgfx.git
7. cd /bgfx
8. on modifie le makefile pour préciser ou se trouve notre commande genie : GENIE=/genie/bin/$(OS)/genie
9. puis on build : make rpi-release

