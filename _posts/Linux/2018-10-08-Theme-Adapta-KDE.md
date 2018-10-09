---
layout: post
author: Funeoz
title: Installer le thème Adapta sur KDE (Kubuntu)
permalink: /linux/adapta-kde.html
---

![Adapta9](/techlovers/assets/image9adapta.png) 


Adapta est un thème propre, moderne et soigné permettant de travailler dans un bon environnement. Il existe en GTK pour Gnome mais une équipe de développeurs a réussi à le porter sur KDE. Ils l'ont mis à disposition sur [GitHub](https://github.com/PapirusDevelopmentTeam/adapta-kde).

Pour installer le thème Adapta sur KDE, il suffira d'installer quelques dépendances et taper quelques lignes dans le terminal.

Tout d'abord, il faut installer Adapta depuis son PPA : 

{% highlight bash %}
$ sudo add-apt-repository ppa:papirus/papirus
$ sudo apt-get update
$ sudo apt-get install --install-recommends adapta-kde
{% endhighlight %}

Ensuite, installez les dépendances du moteur Kvantum afin de donner un meilleur look à votre bureau et téléchargez le compilateur cmake :

{% highlight bash %}
$ sudo apt-get install g++ libx11-dev libxext-dev qtbase5-dev libqt5svg5-dev libqt5x11extras5-dev qttools5-dev-tools cmake
{% endhighlight %}

Puis cloner le repository de Kvantum :

{% highlight bash %}
$ git clone https://github.com/tsujan/Kvantum.git
{% endhighlight %}

Dans le terminal, dirigez-vous dans le dossier précédemment cloné puis compilez :
{% highlight bash %}
$ cd /lenomdudossier
$ mkdir build && cd builds
$ cmake .. CMakeLists.txt
$ make
{% endhighlight %}

Tout ceci fini, vous pouvez donc installer Kvantum :
{% highlight bash %}
$ sudo make install
{% endhighlight %}

Après ceci, il suffit d'appliquer les icônes:

![Adapta1](/techlovers/assets/image1adapta.png) 

Les couleurs :

![Adapta2](/techlovers/assets/image2adapta.png) 

Les polices de caractères Noto SANS (en police à chasse fixe, choisissez celle que vous préférez):

![Adapta3](/techlovers/assets/image3adapta.png) 

En apparence, Adapta :

![Adapta4](/techlovers/assets/image4adapta.png) 

En thème de bureau, la même chose :

![Adapta5](/techlovers/assets/image5adapta.png) 

En style de composant graphique, Kvantum :

![Adapta6](/techlovers/assets/image6adapta.png) 

Et en décorations de fenêtres, Adapta:

![Adapta7](/techlovers/assets/image7adapta.png) 

Et pour la fin, il faut sélectionner Adapta Nokto dans la fenêtre Kvantum Manager après avoir tapé <<kvantummanager>> dans le terminal :

![Adapta8](/techlovers/assets/image8adapta.png) 









