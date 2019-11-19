---
layout: post
author: Funeoz
title: Installer Discord sur Ubuntu
permalink: /linux/discord_linux.html
category: linux
---

![Wall](/techlovers/assets/image2discord.png)

Discord est un logiciel propriétaire VoIP (Transmission de voix par Internet) apparu en 2015. Il a été conçu à ses débuts pour les gamers mais diverses communautés se mettent à l'utiliser à leurs fins respectives (développeurs, associations...).

### Installation

Connectez-vous au site web de [Discord](https://discordapp.com). Et cliquez sur le bouton **Télécharger pour Linux** puis **.deb**.

![image1](/techlovers/assets/image1discord.png)

Téléchargez le fichier puis ouvrez votre terminal :

{% highlight bash %}
# allez au dossier du fichier téléchargé 
$ cd Téléchargements/ (ou autre répertoire)
# installez Discord
$ sudo dpkg -i discord-X.X.X.deb
{% endhighlight %}

Des dépendances sont peut-être manquantes à Discord. Pour résoudre ce problème:

{% highlight bash %}
$ sudo apt-get install -f
{% endhighlight %}

Vous pouvez maintenant lancer l'application Discord.