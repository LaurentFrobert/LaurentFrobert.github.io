--- 
layout: post
title: Compilation libopenmpt (player audio s3m, xtm) pour RPI sous alpine linux
--- 

<http://lib.openmpt.org/libopenmpt/>

1. apk update
2. apk add build-base openssl-dev mpg123-dev  libogg-dev libvorbis-dev portaudio-dev  libsndfile-dev
3. wget https://lib.openmpt.org/files/libopenmpt/src/libopenmpt-0.2.6774-beta20-autotools.tar.gz
4. ./configure  --without-portaudiocpp --without-pulseaudio  --without-ltdl


