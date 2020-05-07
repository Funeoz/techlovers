---
layout: post
author: Funeoz
title: Désactiver snapd (Ubuntu)
category: linux
permalink: /linux/desactiver_snapd.html
redirect_to:
  - https://thelinuxcamp.github.io/linux/desactiver_snapd.html
---
 
 Snapd est un service offrant des paquets fonctionnant sur la plupart des distributions Linux développé par Canonical. 


## Pourquoi désactiver Snapd ?

Tout d'abord, lorsque vous ouvrez le gestionnaire de tâches, vous pouvez voir par vous-même la quantité excessive de mémoire vive consommée par snapd. De plus, lorsqu'une application est installée via snap, ce dernier va faire une sauvegarde de deux versions précédentes en plus de la version actuelle. Prenons pour exemple Pycharm, selon la documentation officielle, la mémoire disque minimale est 2,5Go + 1 Go pour le cache. Donc cela ferait ~10Go utilisés par Pycharm via Snap. 

Conclusion: Installer via les sources ou un simple fichier .deb vous fera économiser beaucoup de mémoire vive et d'espace disque !

## Désactiver Snapd

Tout d'abord, il faut savoir quels services devront être arrêtés en parallèle du service snapd:

{% highlight bash %}
$ systemctl list-unit-files | grep snap
snap-core-4486.mount                   disabled
snap-core-4830.mount                   disabled
snapd.autoimport.service               enabled
snapd.core-fixup.service               enabled
snapd.seeded.service                   disabled
snapd.service                          enabled
snapd.snap-repair.service              static
snapd.system-shutdown.service          enabled
snapd.socket                           disabled
snapd.snap-repair.timer                enabled
{% endhighlight%}

On peut voir que beaucoup de services sont encore actifs.

Pour les désactiver, il suffit d'appliquer la commande *sudo systemctl disable*... Pour l'exemple ci-dessus:

{% highlight bash %}
$ sudo systemctl disable snapd.service
$ sudo systemctl disable snapd.core-fixup.service
$ sudo systemctl disable snapd.socket
$ sudo systemctl disable snapd.autoimport.service
$ sudo systemctl disable snapd.snap-repair.timer
{% endhighlight%}

Appliquez cette commande à tous les services actifs.