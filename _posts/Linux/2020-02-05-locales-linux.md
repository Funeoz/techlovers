---
author: Funeoz
title: Supprimer des fichiers de langue inutiles sous Linux
permalink: /linux/supprimer_locales_inutiles_linux.html
category: linux
layout: post
---

Lors de l'installation de votre système, celui-ci peut installer toutes les variates de langues (fr_BE,fr_CA...) qui peuvent être inutiles et occuper de l'espace.
On aura simplement besoin d'un émulateur de terminal.

## Supprimer des fichiers de langue inutiles

Pour savoir quels fichiers de langue sont installés, il faut exécuter:

{% highlight bash %}
$ locale -a

C
C.UTF-8
fr_BE.utf8
fr_CA.utf8
fr_CH.utf8
fr_FR.utf8
fr_LU.utf8
POSIX
{% endhighlight %}

Les fichiers de langue qui sont installés sur le système sont définis dans le fichier ```/var/lib/locales/supported.d/fr``` 
(ou ```/var/lib/locales/supported.d/fr```).

Il faut donc modifier ce fichier:

{% highlight bash %}
$ sudo nano /var/lib/locales/supported.d/fr

fr_LU.UTF-8 UTF-8
fr_CH.UTF-8 UTF-8
fr_CA.UTF-8 UTF-8
fr_BE.UTF-8 UTF-8
fr_FR.UTF-8 UTF-8
{% endhighlight %}

On va ensuite conserver le fichier de langue ```fr_FR.UTF-8 UTF-8``` et supprimer les autres lignes.
Sauvegardez ensuite votre fichier.

Exécutez ensuite la commande ```sudo locale-gen``` pour regénérer les fichiers de langue:

{% highlight bash %}
$ sudo locale-gen
Generating locales (this might take a while...)
    fr_FR.UTF8...done
Generation complete
{% endhighlight %}

Après cette commande, les autres fichiers de langue ont bien été supprimés.
