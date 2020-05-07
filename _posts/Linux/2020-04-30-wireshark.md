---
layout: post
author: Funeoz
title: Installer Wireshark sous Linux
permalink: /hacking/installer_wireshark_linux.html
image: /techlovers/assets/2020-04-30/image1wireshark.webp
category: hacking
redirect_to:
  - https://thelinuxcamp.github.io/hacking/installer_wireshark_linux.html
---

Wireshark est un outil très utilisé par les professionels de la cybersécurité. Il permet d'analyser les paquets transitant sur un réseau informatique.

## Installation sous Linux

L'installation est très simple puisque Wireshark est disponible dans les repositories des distributions Linux les plus populaires.

Sous **Ubuntu** / **Debian** / **Kali** :

{% highlight bash %}
$ sudo apt-get update
$ sudo apt-get install wireshark
{% endhighlight %}

**Remarque (Ubuntu uniquement)**: Vous pourriez utiliser le PPA des développeurs de l'outil pour avoir une version plus à jour de Wireshark:

{% highlight bash %}
$ sudo add-apt-repository ppa:wireshark-dev/stable
$ sudo apt-get update
$ sudo apt-get install wireshark
{% endhighlight %}

Sous **Fedora** / **Redhat** :

{% highlight bash %}
$ sudo dnf upgrade --refresh
$ sudo dnf install wireshark-qt
{% endhighlight %}

Sous **Arch** / **Manjaro** :

{% highlight bash %}
$ sudo pacman -Syu
$ sudo pacman -S wireshark-qt
{% endhighlight %}
