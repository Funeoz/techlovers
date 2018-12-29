---
layout: post
author: Funeoz
title: Installer Sublime Text sur Ubuntu
permalink: /code/sublime-text-ubuntu.html
---

![WALL](/techlovers/assets/image1sublime.png)

Sublime Text est un éditeur de texte très populaire des développeurs du fait de son interface très légère et de la possibilité d'ajouter des thèmes ou des plugins. Celui-ci supporte 44 langages de programmation. Il est disponible sur Mac OS, Windows et Linux. 

### Installation

Tout d'abord, il faut ouvrir son terminal et ajouter la clé GPG pour Sublime Text.

{% highlight bash %}
$ wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
{% endhighlight %}

Puis vérifier que APT peut fonctionner avec des sources sécurisées.

{% highlight bash %}
$ sudo apt-get install apt-transport-https
{% endhighlight %}

Il y a ensuite deux canaux de développement : **Stable** ou **Dev**. Sélectionnez-en qu'une.

Pour le canal **Stable**:

{% highlight bash %}
$ echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
{% endhighlight %}

Pour le canal **Dev**:

{% highlight bash %}
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
{% endhighlight %}

Rafraîchissez la liste des repositories et installez Sublime Text.

{% highlight bash %}
$ sudo apt-get update
$ sudo apt-get install sublime-text
{% endhighlight %}

*Notez que pour installer Sublime text depuis le canal **Dev**, il faut avoir une license Sublime Text achetée sur le site.*

Il ne suffit plus qu'à lancer Sublime Text depuis le menu d'applications.