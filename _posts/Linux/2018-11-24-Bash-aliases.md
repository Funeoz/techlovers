---
layout: post
author: Funeoz
permalink: /linux/bash/aliases.html
title: Les alias Bash pour abréger des commandes
---

![Bash](/techlovers/assets/image1aliasbash.png)


Les alias Bash permettent de réduire ou abréger des commandes afin de les taper plus rapidement.

## Mise en place

Pour les créer, il suffit de créer un fichier .bash_aliases dans votre dossier personnel:

{% highlight bash %}
$ touch .bash_aliases
{% endhighlight %}

Ouvrez-le avec un éditeur de texte puis suivez la syntaxe suivante:

{% highlight txt %}
alias c='clear'
{% endhighlight %}

* "alias" est le nom de la commande
* "c" correspond au nouveau nom de la commande
* "clear" qui est la commande sous alias (attention aux apostrophes)

Je vais vous donnez quelques idées d'alias :

{% highlight txt %}
alias update='sudo apt update && sudo apt full-upgrade'
alias aptlist='apt list --upgradable'
alias idle='idle-python3.7'
alias remove='sudo apt-get remove'
{% endhighlight %}

Voilà, je pense que vous pouvez mainenant les utliser pleinement.
