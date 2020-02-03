---
layout: post
author: Funeoz
permalink: /linux/discord_terminal_linux.html
category: linux
title: Avoir Discord sous un terminal (Cordless)
image: /techlovers/assets/2019-12-24/image1cordless.jpg
hero_image: /techlovers/assets/2019-12-24/image1cordless.jpg
---

Discord peut être une application qui utilise beaucoup de mémoire vive. Pour cause, Discord se base sur Electron. Il existe donc des alternatives à Discord qui fonctionnent dans un terminal: [Cordless](https://github.com/Bios-Marcel/cordless), [terminal-discord](https://github.com/xynxynxyn/terminal-discord), [6cord](https://gitlab.com/diamondburned/6cord)...

## Cordless

Cordless est à l'origine un client destiné aux machines peu performantes et qui veut impacter le moins possible les performances de l'appareil. Pour le moment, vous pouvez envoyez des messages privés ou sur des serveurs. Vous pouvez aussi envoyer des emojis ou des ping. Certaines fonctionnalitées comme l'insertion d'images ou le chat vocal sont en cours de développement. 

## Installation de Cordless

**Remarque: Un terminal supportant UTF-8 est recommandé pour le rendu des caractères (Termite, Konsole...)

### Via Snap 

{% highlight bash %}
$ sudo snap install cordless
{% endhighlight %}

Pour le lancer:

{% highlight bash %}
$ snap run cordless
{% endhighlight %}

### Avec la source

Installez d'abord le langage Go et ```xclip``` (ou ```wl-clipboard``` sous Wayland) pour que le copier-coller fonctionne sous X11:

{% highlight bash %}
$ sudo apt-get update && sudo apt-get install golang
{% endhighlight %}

Clonez le repo et compilez ensuite la source:

{% highlight bash %}
$ git clone https://github.com/Bios-Marcel/cordless
$ cd cordless
$ go build .
{% endhighlight %}

Lancez cordless:

{% highlight bash %}
$ chmod +x cordless
$ ./cordless
{% endhighlight %}

## Connexion

Pour se connecter, il suffit d'entrer son adresse e-mail et son mot de passe. 

## Personnalisation 

Si le thème de base ne vous convient pas, vous pouvez créer le vôtre grâce à cette page du wiki: [https://github.com/Bios-Marcel/cordless/wiki/Themes](https://github.com/Bios-Marcel/cordless/wiki/Themes) ou utiliser le mien disponible ici: [gist](https://gist.github.com/Funeoz/4d4a2a65530f970d8e00665968405d05). Vous devez le placer dans le dossier ```.config/cordless/```.





