---
layout: post
author: Funeoz
title: Installer la suite JetBrains sous Linux
permalink: /linux/installer_suite_jetbrains_linux.html
category: linux
image: /techlovers/assets/2020-04-24/image1jetbrains.webp
redirect_to:
  - https://thelinuxcamp.github.io/linux/installer_suite_jetbrains_linux.html
---

JetBrains est une compagnie qui offre différents IDE pour divers langages de programmation : PyCharm pour Python, PhpStorm pour le Web, IntelliJ IDEA pour Java/Kotlin...

## Installation avec snap

Installez tout d'abord snap (normalement préinstallé sous Ubuntu):

{% highlight bash %}
$ sudo apt-get update
$sudo apt-get install snapd
{% endhighlight %}

Pour installer un IDE JetBrains avec snap, il suffit de taper la commande `snap install [paquet]`:

{% highlight bash %}
# pycharm community
$ sudo snap install pycharm-community --classic

# intellij idea community
$ sudo snap install intellij-idea-community --classic

# etc...
{% endhighlight %}

[Voir la boutique Snapcraft pour voir les autres paquets disponibles](https://snapcraft.io/store)

## Installation avec un PPA

Si vous désirez éviter les paquets snap, vous pouvez aussi utiliser ce [PPA de Jonas Groeger](https://github.com/JonasGroeger/jetbrains-ppa) tenu régulièrement à jour. Celui compile directement les IDE depuis la source et permet un contrôle total de ces logiciels depuis apt.

Téléchargez la clé GPG et ajouter la source du repository aux votres:

{% highlight bash %}
curl -s https://s3.eu-central-1.amazonaws.com/jetbrains-ppa/0xA6E8698A.pub.asc | sudo apt-key add -
echo "deb http://jetbrains-ppa.s3-website.eu-central-1.amazonaws.com bionic main" | sudo tee /etc/apt/sources.list.d/jetbrains-ppa.list > /dev/null
sudo apt-get update
{% endhighlight %}

Installez ensuite l'IDE de votre choix avec `apt-get`:

{% highlight bash %}
# intellij idea community
$ sudo apt-get install intellij-idea-community

# pycharm community
$ sudo apt-get install pycharm-community

# etc...
{% endhighlight %}

[Voir le GitHub de Joanas Groeger pour les IDE disponibles](https://github.com/JonasGroeger/jetbrains-ppa#inofficial-jetbrains-ppa)


