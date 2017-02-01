---
layout: post
title : Liste de commandes unix utiles
---


* consommation mémoire d'un process (ou plusieurs) (ici tous les python)

  source : <https://www.vincentliefooghe.net/content/r%C3%A9cup%C3%A9rer-la-consommation-m%C3%A9moire-dun-process-sous-linux>

  `ps aux | grep python | grep -v grep | awk 'BEGIN { sum=0 } {sum=sum+$6; } END {printf("Taille RAM utilisée: %s Mo\n",sum / 1024)}'`
  
* xx  
