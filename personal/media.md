---
layout: default
title: Media
permalink: /personal/media/
subtitle:   # optional: one line shown under the title, e.g. subtitle: Things I find interesting.
---

<!-- The items come from _data/media.yml: edit that file, not this one.
     Below: jump links to each section, then each section as a masonry gallery.
     Each item shows image, title, creator/year and one line; "more" folds open longer notes. -->
{% if site.data.media %}
{% assign sections = site.data.media | group_by: "section" %}
<p class="links">
  {% for s in sections %}<a href="#{{ s.name | slugify }}">{{ s.name }}</a>{% endfor %}
</p>

{% for s in sections %}
<h2 id="{{ s.name | slugify }}">{{ s.name }}</h2>
<div class="gallery">
  {% for item in s.items %}
  <figure>
    {% if item.image %}<a href="/assets/img/media/{{ item.image }}"><img src="/assets/img/media/{{ item.image }}" alt="{{ item.title | escape }}" loading="lazy"></a>{% endif %}
    <figcaption>
      <strong>{{ item.title }}{% if item.favourite %}<span class="star">★</span>{% endif %}</strong>
      {% if item.by or item.year %}<span class="meta">{{ item.by }}{% if item.by and item.year %} · {% endif %}{{ item.year }}</span>{% endif %}
      {{ item.short | markdownify }}
      {% if item.more %}<details><summary>more</summary>{{ item.more | markdownify }}</details>{% endif %}
    </figcaption>
  </figure>
  {% endfor %}
</div>
{% endfor %}
{% else %}
<p><em>Nothing here yet.</em></p>
{% endif %}
