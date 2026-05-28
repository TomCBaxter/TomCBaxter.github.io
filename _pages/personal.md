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
<div class="row">
  {% for blog in site.data.blogs %}
    <div class="col-sm-6 mb-3">
      <div class="card h-100">
        <div class="card-body">
          <h5 class="card-title">
            <a href="{{ blog.url }}" target="_blank">{{ blog.name }}</a>
          </h5>
          {% if blog.description != "" %}
            <p class="card-text">{{ blog.description }}</p>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
