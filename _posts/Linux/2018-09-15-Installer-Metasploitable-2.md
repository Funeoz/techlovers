---
title: Installer Metasploitable 2 sur VirtualBox
author: Funeoz
layout: post
permalink: "/linux/metasploitable-2-virtualbox.html"
read_time: true
---
![Metasploitable](/techlovers/assets/metasploitable.jpg)

Installer Metasploitable 2 ne nécessite que quelques minutes.

Pour cela, il faut commencer par installer VirtualBox:

{% highlight bash %}
$ sudo apt-get install virtualbox
{% endhighlight %}

Et téléchargez Metasploitable disponible [ici](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/).

Lancez VirtualBox et appuyez sur "Nouvelle".

Puis nommez la machine "Metasploitable", sélectionnez comme type "Linux" et V
version "Ubuntu (64-bit)".

![image1vb](/techlovers/assets/image1vb.png)

Puis mettez la mémoire vive à 512mo qui est amplement suffisant à Metasploitable:

![image2vb](/techlovers/assets/image2vb.png)

Ensuite, sélectionnez le fichiez metasploitable.vmdk qui se trouve dans le fichier zip: 

![image3vb](/techlovers/assets/image3vb.png)

Appuyez maintenant sur "Créer" et allez dans "Configuration".
Puis dans la sous-partie "Réseau" et sélectionnez la configuration réseau en "Réseau privé hôte". 

*Si la sélection est indisponible, allez dans "Fichier" puis "Host network manager" et cliquez sur "Créer" (Je recommande d'utiliser cette configuration pour des raisons de sécurité car si celle-ci est exposée à Internet, elle serait très vulnérable).*

![image4vb](/techlovers/assets/image4vb.png)

*Retounez donc dans "Configuration -> Réseau puis sélectionnez "Réseau privé hôte".*

Vous pouvez donc lancer Metasploitable. L'identifiant et le mot de passe est "msfadmin".

Le clavier est considéré comme étant en QWERTY. Vous pouvez donc changer la disposition du clavier (a->q, q->a).

{% highlight bash %}
$ sudo loadkeys fr
{% endhighlight %}
