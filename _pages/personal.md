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

## Trips

<style>
  /* 1. Animated Drawer Styling */
  details.trip-drawer {
    background: #ffffff;
    border: 1px solid #eaeaea;
    border-radius: 8px;
    margin-bottom: 1rem;
    box-shadow: 0 2px 4px rgba(0,0,0,0.02);
    transition: box-shadow 0.2s ease;
  }
  details.trip-drawer:hover {
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  }
  details.trip-drawer summary {
    padding: 1rem 1.25rem;
    font-size: 1.1rem;
    font-weight: 600;
    cursor: pointer;
    list-style: none;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  details.trip-drawer summary::-webkit-details-marker {
    display: none; /* Hides default ugly arrow */
  }
  details.trip-drawer summary::after {
    content: '+'; /* Clean plus icon */
    font-size: 1.5rem;
    font-weight: 300;
    color: #6c757d;
  }
  details.trip-drawer[open] summary::after {
    content: '−'; /* Turns to minus when open */
  }
  .trip-drawer-content {
    padding: 0 1.25rem 1.25rem;
    border-top: 1px solid #f0f0f0;
    margin-top: 0.5rem;
    padding-top: 1rem;
  }
  
  /* 2. Masonry Gallery Styling */
  .masonry-gallery {
    column-count: 3;
    column-gap: 1rem;
  }
  .masonry-item {
    break-inside: avoid;
    margin-bottom: 1rem;
    border-radius: 6px;
    overflow: hidden;
  }
  .masonry-item img {
    width: 100%;
    height: auto;
    display: block;
    transition: transform 0.3s ease;
  }
  .masonry-item:hover img {
    transform: scale(1.03);
  }
  
  /* Responsive Breakpoints */
  @media (max-width: 768px) { .masonry-gallery { column-count: 2; } }
  @media (max-width: 576px) { .masonry-gallery { column-count: 1; } }
</style>

<div class="mt-4 mb-5">
  {% for trip in site.data.trips %}
    <details class="trip-drawer">

<summary>
    <span>{{ trip.title }} <span class="text-muted" style="font-size: 0.85em; font-weight: normal;">— {{ trip.location }}</span></span>
  </summary>

<div class="trip-drawer-content">
    <div class="masonry-gallery">
      {% for file in site.static_files %}
        {% assign image_path = "/assets/images/trips/" | append: trip.folder %}

    {% if file.path contains image_path %}
      <div class="masonry-item">
        <img src="{{ file.path | relative_url }}" alt="Photo from {{ trip.title }}">
      </div>
    {% endif %}
  {% endfor %}
</div>
</div>

</details>
{% endfor %}

</div>
