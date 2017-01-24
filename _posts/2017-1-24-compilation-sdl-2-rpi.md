--- 
layout: post
title: Compilation SDL2 sans X11 pour RPI
--- 

d'après la doc : <https://solarianprogrammer.com/2015/01/22/raspberry-pi-raspbian-getting-started-sdl-2/>

1. docker run --rm -it resin/rpi-raspbian /bin/bash
2. apt-get update
3. apt-get install wget libraspberrypi-bin libraspberrypi-dev build-essential libfreeimage-dev libopenal-dev libpango1.0-dev libsndfile-dev libudev-dev libasound2-dev libjpeg-dev libtiff-dev libwebp-dev automake
4. cd
5. wget https://www.libsdl.org/release/SDL2-2.0.5.tar.gz
6. tar zxvf SDL2-2.0.5.tar.gz
7. cd  SDL2-2.0.5 && mkdir build && cd build
8. ../configure --host=armv7l-raspberry-linux-gnueabihf --disable-pulseaudio --disable-esd --disable-video-mir --disable-video-wayland --disable-video-x11 --disable-video-opengl
9. make install

pour compiler les tests :

1. cd ../test
2. ./configure
3. on enleve la compilation du programme "testgles" et testshader dans le Makefile car il lui faut les GLesV1 (et nous avons la v2)
4. make 

et voila !

on peut aussi ajouter la lib SDL_Image, et aussi SDL_ttf:
1. cd ~
2. wget http://www.libsdl.org/projects/SDL_image/release/SDL2_image-2.0.0.tar.gz
3. tar zxvf SDL2_image-2.0.0.tar.gz
4. cd SDL2_image-2.0.0 && mkdir build && cd build
5. ../configure
6. make -j 4
7. sudo make install

idem avec http://www.libsdl.org/projects/SDL_ttf/release/SDL2_ttf-2.0.14.tar.gz

idem avec http://www.libsdl.org/projects/SDL_mixer/release/SDL2_mixer-2.0.1.tar.gz
