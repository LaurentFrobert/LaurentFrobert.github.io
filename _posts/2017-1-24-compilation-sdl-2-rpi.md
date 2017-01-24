--- 
layout: post
title: Compilation SDL2 pour RPI sans X11
--- 

d'après la doc : <https://solarianprogrammer.com/2015/01/22/raspberry-pi-raspbian-getting-started-sdl-2/>

1. docker run --rm -it resin/rpi-raspbian /bin/bash
2. apt-get update
3. apt-get install wget libraspberrypi-bin libraspberrypi-dev build-essential libfreeimage-dev libopenal-dev libpango1.0-dev libsndfile-dev libudev-dev libasound2-dev libjpeg-dev libtiff-dev libwebp-dev automake
4. cd
5. wget https://www.libsdl.org/release/SDL2-2.0.5.tar.gz



