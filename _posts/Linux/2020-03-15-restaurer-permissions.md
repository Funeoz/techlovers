---
author: Funeoz
title: Restaurer les permissions par défaut d'un répertoire ou d'un fichier
permalink: /linux/restaurer_permissions_fichier_repertoire_linux.html
category: linux
layout: post
redirect_to:
  - https://thelinuxcamp.github.io/linux/restaurer_permissions_fichier_repertoire_linux.html
---

Vous avez sûrement déjà toutes les permissions à un répertoire et tout son contenu avec ```chmod -R 777 .```.
Néanmoins, on peut se rendre compte que c'était une mauvaise idée.

Pour restaurer les droits par défaut d'un fichier:

{% highlight bash %}
$ chmod 644 [fichier] 
{% endhighlight %}

Pour restaurer les droits par défaut d'un répertoire:

{% highlight bash %}
$ chmod 755 [répertoire] 
{% endhighlight %}

Pour restaurer les droits de tous les sous-dossiers d'un répertoire:

{% highlight bash %}
$ find . -type d -exec chmod 775 {} \;
{% endhighlight %}

Pour restaurer les droits de tous les fichiers d'un répertoire:

{% highlight bash %}
$ find . -type f -exec chmod 644 {} \;
{% endhighlight %}
