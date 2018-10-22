---
layout: post
author: Funeoz
permalink: /code/utilisation-powershell.html
title: Installation et introduction au PowerShell
---

![Powershell](/techlovers/assets/image1powershell.png)

Le PowerShell est une suite logicielle écrite en C# et basé sur le framework Microsoft .NET . Elle comprend le language et la ligne de commande. Il est le successeur de cmd. Des informations sont disponibles sur le [site de Microsoft](http://www.microsoft.com/powershell) et son dépot est sur [GitHub](https://github.com/PowerShell/PowerShell). Il est disponible sur Mac OS, Windows (de base sur Windows 8, 8.1 et 10) et Linux

## Installation sur Ubuntu

Comme toujours, mon installation va se faire sur Ubuntu car c'est mon OS de travail. Cependant des informations sont disponibles pour chaque système [ici](https://docs.microsoft.com/fr-fr/powershell/scripting/setup/installing-powershell?view=powershell-6).

Passons donc à l'installation sur Ubuntu. Commençons par l'ajout des clés GPG du repository. 

{% highlight bash %}
$ wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
# puis l'enregistrement des clés
$ sudo dpkg -i packages-microsoft-prod.deb
# ensuite on met à jour la liste des repositories
$ sudo apt-get update
# puis on l'installe
$ sudo apt-get install -y powershell
{% endhighlight %}

Un paquet Snap est disponible pour la 18.10, mais je ne vous la recommande pas à cause du stockage pris par le paquet à chaque mise à jour (Snap conserve deux anciennes versions et l'actuelle, prenant un espace considérable).

## Lancement

Pour lancer le powershell, il suffit de lancer le terminal et taper :

{% highlight bash %}
$ pwsh
{% endhighlight %}

## Introduction

Le PowerShell possède des commandes similaires à celles Unix telles que cd, rm,cat, find, wget, mv... . Ce qui rend son utilisation simple et rapide si vous êtes familier à ces commandes. Vous pouvez connaître toutes les commandes sur[Wikipedia](https://fr.wikipedia.org/wiki/Windows_PowerShell#frb-inline).

Il ne faut pas les confondre avec les "verbes" qui permettent d'effectuer des actions bien déterminées.

Voici leur liste :
> * Add : permet d'ajouter une donnée sur une variable qui suit
> * Get : permet d'avoir des informations sur une variable qui suit
> * Clear: permet de réinitialiser une variable
> * Import/Export: permet d'importer/exporter un fichier de commandes ou des alias
> * New : permet de créer une variable ou objet
> * Set : permet de définir des données sur une variable qui suit
> * Write : permet d'écrire une donnée sur une variable ou faire un résumé d'une commande

Pour lancer des scripts PowerShell, celui-ci possède quatre modes d'exécution :

> * Restricted : aucun script est éxécutable. Seul l'interaction avec l'interface est disponible.
> * AllSigned : Les scripts signés sont seulement éxécutables.
> * RemoteSigned : Les scripts provenant d'Internet doivent être signés pour être éxécutés. Ceux qui sont déjà sur l'ordinateur ne doivent pas être forcément signés pour être éxécutés.
> * Unrestricted : Tous les scripts peuvent être éxécutés.

Pour connaître le mode d'éxécution, il suffit de faire: 

{% highlight powershell %}
PS> Get-ExecutionPolicy
Restricted
# puis le changer
PS> Set-ExecutionPolicy Unrestricted
{% endhighlight %}

Vous pouvez donc ensuite lancer tous les scripts que vous voulez, ce qui rendra votre machine plus vulnérable parallèlement.

Il existe aussi des modules qui permettent de profiter de fonctions déjà existantes. Vous pouvez aussi les écrire.

Pour connaître les modules en utilisation :

{% highlight powershell %}
PS> Get-Module
# puis lister ceux déjà existants
PS> Get-Module -ListAvailable
# et en importer un 
PS> Import-Module ActiveDirectory
{% endhighlight %}

Voilà, l'introduction est finie. Je vous invite à consulter le site de Microsoft pour avoir des exemples plus précis sur son utilisation avec des 
[tutoriels](https://docs.microsoft.com/fr-fr/powershell/scripting/getting-started/fundamental/sample-scripts-for-administration?view=powershell-6).




