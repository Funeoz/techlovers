---
layout: post
author: Funeoz
title: Personnaliser Spotify avec Spicetify
category: linux
image: /techlovers/assets/2020-01-22/wall.png
permalink: /linux/spicetify_custom_spotify_linux.html
---

Spicetify permet de personnaliser Spotify en injectant du code CSS ou Javascript directement dans l'application. Il permet donc par exemple de supprimer la barre de publicités de l'application. 

## Installation 

**Remarque: Spicetify supporte uniquement les versions de Spotify installées via un fichier .deb ou Flatpak (Snap non supporté).**

1) Téléchargez Spicetify depuis son repository: [https://github.com/khanhas/spicetify-cli/releases](https://github.com/khanhas/spicetify-cli/releases)
et prenez la version ```linux-amd64```.

2) Créez un répertoire ```spicetify``` et extrayez le fichier:

{% highlight bash %}
$ mkdir ~/spicetify
$ tar xzf ~/Téléchargements/spicetify-x.x.x-linux-amd64.tar.gz -C ~/spicetify
{% endhighlight %}

3) Optionnel: Déplacer Spicetify dans le répertoire ```/usr/bin/spicetify/``` pour le lancer n'importe où:

{% highlight bash %}
$ sudo ln -s ~/spicetify/spicetify /usr/bin/spicetify
{% endhighlight %}

4) Créez le fichier de configuration de Spicetify et une sauvegarde de Spotify:

{% highlight bash %}
$ spicetify
$ spicetify backup apply enable-devtool
{% endhighlight %}

### Notes importantes 

#### Pour Spotify en .deb

Si vous avez installé Spotify depuis un fichier .deb, vous devez autoriser l'accès écriture sur les fichiers de Spotify: 

{% highlight bash %}
$ sudo chmod 777 /usr/share/spotify -R
{% endhighlight %}

#### Pour Flatpak

1) Il faut déterminer où Flatpak à installer Spotify:

{% highlight bash %}
$ flatpak --installations 
{% endhighlight %}

Puis aller jusqu'au répertoire où est installé Spotify. Par défaut: ```/var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/```

2) Renseignez ensuite ce répertoire dans le fichier de configuration précédemment créé (```.config/spicetify/config.ini```):

![image1](/techlovers/assets/2020-01-22/image1spicetify.png)

3) Donnez les permissions d'écriture: 

{% highlight bash %}
$ sudo chmod 777 -R /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/
{% endhighlight %}

## Personnalisation 

### Appliquer un thème personnalisé

Un repository recensant la plupart des thèmes est disponible sur GitHub: [https://github.com/morpheusthewhite/spicetify-themes](https://github.com/morpheusthewhite/spicetify-themes). Un aperçu des thèmes est disponible [ici](https://github.com/morpheusthewhite/spicetify-themes/wiki/Themes-preview).

1) Clonez le repo:

{% highlight bash %}
$ git clone https://github.com/morpheusthewhite/spicetify-themes
{% endhighlight %}

2) Déplacez le dossier du thème choisi dans celui de Spicetify (```.config/spicetify/Themes/```):

{% highlight bash %}
$ mv spicetify-themes/[nom_du_dossier]/ .config/spicetify/Themes/
{% endhighlight %}

3) Mettez à jour spicetify pour qu'il applique le thème:

{% highlight bash %}
$ spicetify config current_theme [nom_du_thème]
$ spicetify update
{% endhighlight %}

4) Relancez Spotify si besoin avec ```Ctrl```+```shift```+```R```.

### Supprimer la barre de publicités (thème personnalisé uniquement)

Si le thème personnalisé ne bloque pas au préalable la barre de publicités, ajoutez ces lignes suivantes dans le fichier  ```user.css``` présent dans le répertoire du thème:

{% highlight css %}
#view-leaderboard-ad {
    display: none !important;
}
{% endhighlight %}

Mettez à jour Spicetify: 

{% highlight bash %}
$ spicetify update
{% endhighlight %}