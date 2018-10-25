---
layout: page
title: Trees
showInHeader: false
permalink: /data-structures/trees
---
{% if jekyll.environment == "production" %}
<ol>
  {% for post in site.categories.trees %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ol>
{% endif %}