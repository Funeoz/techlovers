---
layout: post
author: Funeoz
title: Réduire la lumière bleue de son écran avec Redshift
permalink: /linux/redshift-lumiere-bleue.html
---

![redshift](/techlovers/assets/image1redshift.png)

Si vous travaillez beaucoup la nuit, la lumière bleue peut impacter votre sommeil et donc la production de mélatonine (l'hormone du sommeil). La lumière bleue à aussi des effets d'endommagement sur la rétine ainsi que sur le diabète (étude Harvard disponible [ici](https://www.health.harvard.edu/staying-healthy/blue-light-has-a-dark-side))
Voilà donc une raison de se protéger de cette lumière nocive à notre santé.

Redshift permet donc de diminuer la lumière bleue en changeant la couleur de l'écran en fonction de l'heure dans la journée. Il existe aussi une alternative à Redshift qui est f.lux mais celle-ci sur Linux n'est pas très maintenue. **Il n'est pas nécessaire de l'installer sur Gnome car cette fonctionnalité est disponible dans ses paramètres.**

## Installation de Redshift

### Sur Ubuntu

Il existe déjà sur les dépôts Ubuntu en GTK+. Il suffit donc de faire :

{% highlight bash %}
$ sudo apt-get install redshift-gtk
{% endhighlight %}

### Sur une autre distribution

Pour une autre ditribution, il faut le compiler depuis la source. Mais d'abord il faut installer les dépendances :

{% highlight bash %}
$ sudo apt-get install autotools gettext intltool libtool python3 pygobject pyxdg geoclue-2.0 appindicator libX11 libXxf86vm libxcb libxcb-randr libdrm
# attention : la présence des ces paquets sur les repositories dont geoclue-2.0 dépend de votre distribution. A vous de voir si vous devez les compilez vous-même ou non.
{% endhighlight %}

Passons à la compilation :

{% highlight bash %}
$ git clone https://github.com/jonls/redshift.git
# allez dans le dossier
$ cd redshift
# puis lancez le fichier bootstrap
$ ./bootstrap
# celui-ci va créer le fichier configure pour redshift avec autotools
$ ./configure --prefix=$HOME/redshift/root \ --with-systemduserunitdir=$HOME/.config/systemd/user
# "--prefix=$HOME/redshift/root" permet de l'installer dans le dossier personnel à place de le faire dans le système
$ make
$ make install
{% endhighlight %}

Maintenant lancez le script :

{% highlight bash %}
$ $HOME/redshift/root/bin/redshift-gtk
# c'est un exemple, donc le chemin peut changer
{% endhighlight %}

Si certaines dépendances ont été inutiles, vous pouvez les supprimer en faisant :

{% highlight bash %}
$ sudo apt autoremove
{% endhighlight %}

## Configuration 

Afin que Redshift trouve convenamblement vos cordonnées GPS, il faut que vous autorisiez l'accès à la localisation Geoclue 2. Pour cela, ajouter ces lignes de code au fichier situé à "/etc/geoclue/geoclue.conf": 

{% highlight haskell %}
[redshift]
allowed=true
system=false
users=
{% endhighlight %}

Puis créez dans le dossier .config dans le répertoire personnel le fichier "redshift.conf" (attention ce dossier est caché) et ajouter ce script :

{% highlight haskell %}
; Paramètres globaux pour redshift.
[redshift]
; Régler les températures de jour et de nuit de l'écran.
temp-day=5500
temp-night=3500

; Activer / Désactiver une transition en douceur entre le jour et la nuit.
; 0 provoquera un changement direct de jour à la température de l'écran de nuit.
; 1 va progressivement augmenter ou diminuer la température de l'écran.
transition=1

; Réglez la luminosité de l'écran. Par défaut 1.0.
;brightness=1
; Il est également possible d'utiliser des réglages différents pour le jour et la nuit
; depuis la version 1.8.
;brightness-day=0.7
;brightness-night=0.4
; Réglez le gamma de l'écran (pour toutes les couleurs, ou chaque canal de couleur
; individuellement).
gamma=0.8
;gamma=0.8:0.7:0.8
; Cela peut aussi être réglée individuellement pour le jour et la nuit depuis
; la version 1.10.
;gamma-day=0.8:0.7:0.8
;gamma-night=0.6

; Sélectionner le service de localisation : 'geoclue', 'gnome-clock', 'manual'
; tapez 'redshift -l list' pour voir les valeurs possibles.
; Les paramètres du service de localisation sont dans une section différente.
location-provider=manual

; Sélectionner la méthode d'ajustement : 'randr', 'vidmode'
; tapez 'redshift -m list' pour voir toutes les valeurs possibles.
; 'randr' est la méthode préférée, 'vidmode' est une ancienne API
; mais fonctionne dans certains cas où 'randr' fait défaut.
; Les paramètres de la méthode d'ajustement sont dans une section différente.
adjustment-method=randr

; Configuration du service de localisation :
; tapez 'redshift -l PROVIDER:help' pour voir les paramètres
; exemple : 'redshift -l manual:help'
[manual]
; A changer en fonction de votre positionnement géographique / GPS
lat=48.8
lon=2.3

; Configuration de la méthode d'ajustement
; tapez 'redshift -m METHOD:help' pour voir les paramètres
; exemple : 'redshift -m randr:help'
; Dans cet exemple, randr est configuré pour ajuster l'écran 1.
; Notez que la numérotation commence à partir de 0, donc c'est en fait le premier écran.
[randr]
; Si rien n'est spécifié, Redshift ajustera tous les écrans
;screen=0
{% endhighlight %}

Pensez à changer votre latitude et longitude en fonction de la vôtre grâce au site [www.laglong.net](https://latlong.net). Dans le fichier redsift.conf, ne spécifiez qu'un chiffre après la virgule pour les coordonnées.

Voilà, vos yeux sont maintenant protégées de la nocive lumière bleue.


