---
layout: default
title: Linux
---

<div class="posts">
    {% include pagination.html %}
    {% for post in site.posts %}
    {% if post.category == 'linux' %}
        {% include post-card.html %}
    {% endif %}
    {% endfor %}
  </div>