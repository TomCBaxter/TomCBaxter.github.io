---
layout: default
title: Cabinet of Curiosities
permalink: /personal/cabinet/
subtitle:   # optional: one line shown under the title, e.g. subtitle: Things I find interesting.
---

<!-- The items come from _data/gallery.yml: edit that file to add, remove or reorder them.
     This loop shows each one as: image (click for full size), title, caption. -->
<div class="gallery">
{% for item in site.data.gallery %}
  <figure>
    <a href="/assets/img/gallery/{{ item.image }}"><img src="/assets/img/gallery/{{ item.image }}" alt="{{ item.title | escape }}" loading="lazy"></a>
    <figcaption><strong>{{ item.title }}</strong>{{ item.caption | markdownify }}</figcaption>
  </figure>
{% endfor %}
</div>
