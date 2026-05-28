---
layout: page
title: Personal
permalink: /personal/
nav: true
nav_order: 5
---

## Cabinet of Curiosities

<div class="mt-5">
  {% include gallery.liquid %}
</div>

<br>

## Blogs 
<ul class="post-list">
  {% for blog in site.data.blogs %}
    <li>
      <a href="{{ blog.url }}" target="_blank">{{ blog.name }}</a>
      {% if blog.description != "" %}
        <p>{{ blog.description }}</p>
      {% endif %}
    </li>
  {% endfor %}
</ul>
