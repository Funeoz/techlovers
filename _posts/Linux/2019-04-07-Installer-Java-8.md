---
layout: post
author: Funeoz
permalink: /linux/installer_java_8_9_ubuntu.html
title: Installer Java 8 ou 9 sur Ubuntu (JRE) (Abandonné)
category: linux
---

![Logo](/techlovers/assets/image1java.png)

Java Runtime Environment ou JRE permet d'exécuter des fichiers .jar sur votre ordinateur. Ne pas confondre avec le JDK qui est un jeu de bibliothèques destiné au développement en langage Java.

## Installation à l'aide du PPA de Webupd8 (Abandonné)

**ATTENTION: Le PPA pour JRE 8 ou 9 a été abandonné par WebUpd8. En effet, la license d'utilisation du JDK a été modifié par Oracle. Plus d'informations ici : [https://launchpad.net/~webupd8team/+archive/ubuntu/java](https://launchpad.net/~webupd8team/+archive/ubuntu/java). Le tutoriel est conservé comme une archive et ne peux plus être réalisé.**

Le PPA permet d'installer automatiquement chaque nouvelle version de Java 8 ou 9. Il télécharge automatiquement les archives depuis le site d'Oracle et les configurent directement.

Pour cela, ajoutez le PPA:

{% highlight bash %}
$ sudo add-apt-repository ppa:webupd8team/java
{% endhighlight %}

Puis mettez à jour l'index des paquets et installez le paquet java 8 ou 9:

{% highlight bash %}
$ sudo apt update && sudo apt install oracle-java8-installer
# ou pour Java 9
$ sudo apt update && sudo apt install oracle-java9-installer
{% endhighlight %}

Il va vous être demandé d'accepter la license de Java pour télécharger les fichiers binaires de Java.

![java](/techlovers/assets/image2java.jpg)

## Vérifier la version de Java 

Pour cela, exécutez la commande :

{% highlight bash %}
$ javac -version
{% endhighlight %}

Cela devrait vous retourner "1.8.0_XXX" pour Java 8 ou "1.9.0_XXX" pour Java 9.

