---
author: Funeoz
title: Télécharger de la musique depuis Deezer avec Deezloader
permalink: /linux/deezloader-musique-depuis-deezer-linux.html
category: linux
image: /techlovers/assets/2020-05-06/image1deezloader.webp
---

**ATTENTION, EN ANCUN CAS LES DÉVELOPPEURS ET MOI NE SONT RESPONSABLES DES DOMMAGES QUI POURRAIENT ÊTRE COMMIS PAR L'UTILISATION DE CET OUTIL. CELUI-CI PEUT ÊTRE ILLÉGAL DANS VOTRE PAYS. VOUS ÊTES PRÉVENUS. CE TUTORIEL EST A TITRE ÉDUCATIF.**

Deezloader permet de télécharger des musiques en format MP3 128kbps ou 320 kbps et en FLAC 1411kbps depuis Deezer. Cet outil permet donc de télécharger en haute qualité de la musique sans prise de tête. Il est disponible sur Windows, Mac OS, Linux et Android. Le code source est disponible [ici](https://notabug.org/RemixDevs/DeezloaderRemix).

## Installation sous Linux

Le format employé par les développeurs est AppImage. Il est donc supporté par la plupart des distributions.

Rendez-vous tout d'abord sur cette page : [https://notabug.org/RemixDevs/DeezloaderRemix/wiki/Downloads](https://notabug.org/RemixDevs/DeezloaderRemix/wiki/Downloads)

Vous trouverez tous les liens de téléchargement pour votre Linux 64bit ou 32bit puis téléchargez le fichier.

Ouvrez votre terminal et donnez les droits d'exécution au fichier :

{% highlight bash %}
$ cd Téléchargements
$ sudo chmod +x Deezloader_Remix_4.4.0-x86_64.AppImage # adaptez à votre version
{% endhighlight %}

Vous pourrez ensuite lancer le lancer depuis le terminal :

{% highlight bash %}
$ ./Deezloader_Remix_4.4.0-x86_64.AppImage
{% endhighlight %}

Ou depuis le gestionnaire de fichiers où le système pourra ensuite vous proposer de créer un raccourci bureau vers le fichier.
