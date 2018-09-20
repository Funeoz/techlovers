---
author: Funeoz 
layout: post
title: Installer Anonsurf sur Ubuntu 
permalink: /link/anonsurf-ubuntu.html
---

Installer Anonsurf est très simple. 
Il faut d'abord cloner le repository de Anonsurf sur kali

{% highlight bash %} $ git clone https://github.com/Und3rf10w/kali-anonsurf {% endhighlight %}

Puis se diriger dans le dossier nouvellement cloné:

{% highlight bash %} $ cd kali-anonsurf {% endhighlight %}

Faites 

{% highlight bash %} $ sudo sh {% endhighlight %}

Puis exécutez le fichier .sh :

{% highlight bash %} $ ./installer.sh {% endhighlight %}

L'installation va se faire automatiquement.

Pour lancer ou stopper Anonsurf, il suffit de faire:

{% highlight bash %} $ anonsurf start/stop {% endhighlight %}

En désactivant Anonsurf, l'interface peut buguer. Il faut juste se déconnecter et se reconnecter au réseau. Voilà.





