---
layout: page
title: Contribuer à Techlovers
show_sidebar: false
---

Pour contribuer pour Techlovers : 

1) Créez-vous ou connectez-vous à votre compte GitHub.

2) Clonez le repository du site:

{% highlight bash %}
$ git clone https://github.com/Funeoz/techlovers.git
{% endhighlight %}

3) **Attention, votre article doit suivre la mise en page Markdown**

a) Le nom du fichier dans être écrit de cette manière : AAAA-MM-JJ-Titre-article.md

b) Ajoutez votre article dans le dossier *_posts*. 

c) Veillez à votre orthographe.

d) Mettez en tête de fichier les lignes suivantes:

{% highlight markdown %}
---
layout: post
author: votre_pseudo
title: votre_titre
subtitle: # sous-titre si voulu
---
{% endhighlight %}

4) Ajoutez si vous le voulez des images à votre article et mettez-les dans le dossier *assets*.

5) Créez une Pull Request.

6) L'équipe décidera de la publication de votre article.