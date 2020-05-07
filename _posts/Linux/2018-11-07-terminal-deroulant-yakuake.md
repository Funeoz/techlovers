---
author: Funeoz
title: Yakuake, un terminal déroulant pour des tâches rapides
permalink: /linux/yakuake_terminal_deroulant_linux.html
category: linux
layout: post
image: /techlovers/assets/2018-11-07/image1yakuake.png
redirect_to:
  - https://thelinuxcamp.github.io/linux/yakuake_terminal_deroulant_linux.html
---
&nbsp;

Yakuake est un terminal déroulant créé par la communauté KDE. Il permet de faire apparaître depuis le haut de l'écran une console avec une simple combinaison de commandes (F12 par défaut). Il peut être personnalisé très facilement.

## Installation

### Depuis les repositories

Il est disponible sur les repos d'Ubuntu, Debian, Parrot et Arch Linux.

Pour l'installer :

{% highlight bash %}
$ sudo apt install yakuake
# pour arch
$ pacman -S yakuake
{% endhighlight %}

### Depuis la source

Pour ce faire, téléchargez la dernière version depuis [Github](https://github.com/KDE/yakuake/releases).

Décompressez l'archive puis ouvrez votre terminal :

{% highlight bash %}
$ cd yakuake-<version>
# créez un dossier build
$ mkdir build
# allez à ce dossier
$ cd build
# choisissez où vous voulez l'installer
$ cmake -DCMAKE_INSTALL_PREFIX=<path to install to> ../
# compilez
$ make
$ make install
# lancez-le
$ yakuake
{% endhighlight %}

Yakuake va ensuite vous demander la touche ou combinaison de touches pour que Yakuake s'ouvre. Moi, j'ai choisi alt+f12. 

Je vous laisse voir cette vidéo pour les différentes options (attention, des problèmes peuvent survenir avec la lecture vidéo avec Chrome ou Opera):

<video width="700" height="auto" controls> <source src="{{ site.baseurl }}/assets/2018-11-07/yakuake.mp4" type="video/mp4"> 
</video>




