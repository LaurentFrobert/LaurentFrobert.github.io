--- 
layout: post
title: Compilation BGFX pour RPI
--- 
Avec raspbian sur une machine x86
bgfx : <https://github.com/bkaradzic/bgfx>
doc compilation : <https://bkaradzic.github.io/bgfx/build.html>

j'utilise la méthode "docker arm sur x86" voir autre post 

puis :

1.  docker run --rm -it resin/rpi-raspbian /bin/bash
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
8. génération du makefile (en utilisant sdl car sinon bgfx veux les libs X11)
apt-get install libsdl2-dev libsdl2-ttf-dev libfontconfig-dev
(mais il semble que libsdl est compiler avec la dependence X11 : TODO recompiler la lib SDL pour RPI avec que tu OpenGLES sans X11)

/genie/bin/linux/genie --gcc=rpi --with-examples  --with-sdl gmake

                  



pour info : d'après doc <http://choccyhobnob.com/tutorials/compiling-mame-on-raspberry-pi/> : libSDL 2.0.5 pour avoir le GPU HW

10. puis on build : (-ldl car sinon on a une erreur :  undefined reference to symbol 'dlsym@@GLIBC_2.4')
LDFLAGS="-ldl" make -j4 rpi-release

