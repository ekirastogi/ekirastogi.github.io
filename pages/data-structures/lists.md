---
layout: page
title: Lists
showInHeader: false
permalink: /data-structures/lists
---

<ol>
  {% for post in site.categories.lists %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ol>