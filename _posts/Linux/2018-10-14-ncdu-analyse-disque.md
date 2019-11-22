---
author: Funeoz
layout: post
permalink: /linux/ncdu-analyse-dique.html
title: NCDU, un analyseur de disque pour Linux
category: linux
---

NCDU est une alternative à Qdirstat ou encore Baobab venant avec Gnome mais en version terminal. Il permet de lister les fichiers présents dans un certain dossier et des les classer par taille. Il est disponible sur plusieurs distibutions telles que Debian, Ubuntu,FreeBSD... Et aussi Mac OS.

## Signification 

NCDU signifie NCurses Disk Usage, NCurses étant une bibliothèque en C pour le développement d'environnements en texte seulement (cela est similaire au CLI qui traite lignes par lignes des commandes mais n'y est pas limité).

DU pour l'analyse de la taille d'un dossier ou fichier.

## Installation

Pour l'exemple, je vais l'installer sur Ubuntu depuis le terminal car il est déjà présent dans les repos :

{% highlight bash %}
$ sudo apt-get install ncdu
{% endhighlight %}

## Utilisation

Puis pour le lancer dans la console:

{% highlight bash %}
$ ncdu /
#le slash correspond au point de départ de l'analyse, soit la racine
{% endhighlight %}

![ncdu](/techlovers/assets/2018-10-14/image1ncdu.png)

Cela va donc lancer l'analyse. Il est possible d'arrêter le scan en appuyant sur *q*.

Le scan terminé, on peut voir les dossiers triés dans l'ordre.

![ncdu2](/techlovers/assets/2018-10-14/image2ncdu.png)

Voici la liste des commandes traduites que vous pouvez utiliser dans ncdu pour ceux qui pourraient avoir du mal avec l'anglais.

> * ? : afficher aide (en anglais) 
> * flèche haute, k : Monter 
> * flèche basse, j : Descendre
> * flèche droite, entrée : Entrer dans le dossier
> * flèche gauche, <, h : Retourner au dossier parent
> * n : lister par nom (alphabétique (inverse))
> * s : lister par taille (croissante, décroissante)
> * C : lister par objets (croissant, décroissant)
> * d : supprimer dossier ou fichier sélectionné
> * t : dossiers listés en premier
> * g : afficher des pourcentages ou des graphiques
> * a : choisir entre taille apparente et taille occupée réellement
> * c : afficher le nombre de fichiers dans chaque dossier
> * e : afficher fichiers cachés
> * i : afficher des info sur l'objet sélectionné
> * r : recalculer la taille du dossier
> * b : ouvrir un terminal 
> * q : quitter ncdu

Je vous invite donc à consulter le [site web](https://dev.yorhel.nl/ncdu) pour l'installation sur votre distribution et le [manuel d'utilisation](https://dev.yorhel.nl/ncdu/man).