---
title: Changer l'apparence de bash
author: Davistar
permalink: /linux/changer_apparence_bash.html
layout: post
category: linux
---

## Changer l'apparence du shell (bash) sous les systèmes d'exploitation Linux ou Unix

Vous pouvez changer l'apparence de votre shell pour impressionner votre ami ou pour vous simplifier la vie en travaillant avec le terminal. Le shell BASH est la configuration par défaut sous Linux et Mac OS. Votre paramètre d'invite actuel est stocké dans une variable shell appelée PS1. Il existe également d'autres variables, telles que PS2, PS3 et PS4.

Bash affiche l'invite principale PS1 lorsqu'elle est prête à lire une commande et l'invite secondaire PS2 lorsqu'elle nécessite davantage d'entrées pour exécuter une commande. Bash permet de personnaliser ces chaînes d'invite en insérant un certain nombre de caractères spéciaux protégés par une barre oblique inverse.

## Afficher l’invite BASH actuelle (PS1)

Utilisez la commande echo pour afficher l'invite BASH actuelle:

{% highlight bash %}
# retourne l'invite principale
$ echo $PS1
{% endhighlight %}

Une fois cette commande executée, il vous sortira une chaine de caractères BASH comme ceci:

## Exemples de sortie:

![outputps1](/techlovers/assets/2018-11-28/ps1capture.png)

Par défaut, l'invite de commande est définie sur [\u@\h \W] \$. Les caractères spéciaux échappés par une antislash sont décodés comme suit:

* \u : Affiche le nom d'utilisateur actuel.
* \h : affiche le nom d'hôte
* \w : Affiche la base du répertoire de travail actuel.
* \\$ : (indique l'utilisateur root) si l'UID effectif est 0, sinon affiche un $.
* \H : Affiche le nom d'hôte FQDN.
* \@ : Affiche l'heure actuelle au format 12 heures am/pm

## Tâche: Ajouter des couleurs à l'invite:

* \e[  : Démarrer le jeu de couleurs (ou on peut utiliser \033).
* x;y  : Paire de couleurs à utiliser (x; y)
* $PS1 : Votre variable d’invite du shell.
* \e[m : Arrête le jeu de couleurs.

### Liste des codes couleurs:

* Couleur (classic) : Code
* noir : 0;30
* rouge : 0;31
* vert : 0;32
* marron : 0;33
* bleu : 0;34
* violet : 0;35
* cyan : 0;36
* blanc : 0;37

* Couleur (light) : Code
* noir : 1;90
* rouge : 1;91
* vert : 1;92
* jaune : 1;93
* bleu : 1;94
* violet : 1;95
* cyan : 1;96
* blanc : 1;97


## Pour définir une apparence, tapez la commande suivante :

{% highlight bash %}
$ export PS1="\033[1;92m[\u@\h \033[1;94m\w\033[1;92m]~:\033[1;97m\$ "
{% endhighlight %}

Sortie : 

![capture2ps1](/techlovers/assets/2018-11-28/capture2ps1.png)

### Activer notre thème au démarrage de bash :

{% highlight bash %}
$ echo $HOME
# ceci renvoie /root
# on va maintenant installer nano pour modifier le fichier .bashrc
$ sudo apt-get update && apt-get upgrade -y && apt-get install nano -y
# puis ouvrir le fichier
$ sudo nano /root/.bashrc
# ensuite, collez le thème PS1 avec la commande export en bas de .bashrc
$ export PS1="\[\033[1;97m\]\342\224\214\342\224\200[\[\033[1;97m\]\u\[\033[1;97m\]@\[\033[1;97m\]\h\[\033[1;97m\]]\342\224\200[\[\033[1;97m\]\w\[\033[1;97m\]]\n\[\033[0;97m\]\342\224\224\342\224\200\342\224\200\342\225\274 \[\033[0m\]\[\e[01;97m\]$\[\e[0m\]"
{% endhighlight %}

Voilà ce que cela donne :

![capture3ps1](/techlovers/assets/2018-11-28/capture3ps1.png)