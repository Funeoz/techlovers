---
layout: default
title: Linux
---

<div class="posts">
    {% for post in site.posts %}
    {% if post.category == 'linux' %}
        {% include pagination.html %}
        {% include post-card.html %}
        {% include pagination.html %}
    {% endif %}
    {% endfor %}
  </div>