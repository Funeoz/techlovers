---
layout: post
author: Funeoz
title: Coder sur Visual Studio Code avec n'importe quel appareil
permalink: /code/coder_partout.html
category: linux
---

![Logo](/techlovers/assets/2019-03-26/image1codercom.png)

Le site [Coder.com](https://coder.com/) permet de coder sur n'importe quel appareil avec VS Code. Il peut être installé avec Docker, ou des fichiers binaires disponibles pour Mac OS et Linux (version Windows bientôt disponible). Ou alors, il existe une version alpha et gratuite nommé "code-server" permettant directement de coder sur leur site. Son code source se trouve sur [GitHub](https://github.com/codercom/code-server). 

# Installation sous Ubuntu

Il faut d'abord installer la dépendance net-tools:

{% highlight bash %}
$ sudo apt install net-tools
{% endhighlight %}

Puis télécharger le fichier binaire pour Linux disponible [ici](https://github.com/codercom/code-server/releases).

Décompressez le fichier. Si vous n'avez pas de logiciel d'archivage, je vous recommande ark.

Ensuite, exécutez les commandes suivantes :

{% highlight bash %}
# allez au dossier
$ cd code-server-X.XX.X-XXX-linux-x64
# donnez les droits d'exécution au fichier
$ chmod +x code-server-X.XX.X-XXX-linux-x64
# exécutez-le
$ ./code-server-X.XX.X-XXX-linux-x64
{% endhighlight %}

Le serveur va se lancer à l'adresse "https://localhost:8443". Un mot de passe va vous être demandé qui vous sera donné lors de l'exécution du fichier binaire. 

### Change l'adresse de connexion

Par défaut, l'adresse 0.0.0.0 est utilisée. Il suffit de taper:

{% highlight bash %}
$ code-server -h 127.0.0.2
{% endhighlight %}

Pour changer l'adresse de connexion à "127.0.0.2".

### Changer le port de connexion 

Pour cela, une commande suffit (exemple: port 9000):

{% highlight bash %}
$ code-server -p 9000
{% endhighlight %}

# Coder sur Android ou IOS

Pour cela, il suffit de créer un compte sur leur [site](https://coder.com).
Un numéro de téléphone vous sera demandé pour éviter les abus.

L'éditeur se lancera par la suite.

**Note**: Code-server peut aussi être installé sur Google Cloud, Amazon Web Services ou Digital Ocean.