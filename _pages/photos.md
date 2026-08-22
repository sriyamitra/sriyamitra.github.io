---
layout: page
title: photos
permalink: /photos/
nav: true
nav_order: 3
---

<style>
  .photo-collage {
    column-count: 2;
    column-gap: 1.5rem;
    margin-top: 2rem;
  }

  @media (max-width: 768px) {
    .photo-collage {
      column-count: 1;
    }
  }

  .photo-card {
    break-inside: avoid;
    margin-bottom: 1.5rem;
    display: inline-block;
    width: 100%;
    transition: transform 0.25s ease;
  }

  .photo-card img {
    width: 100%;
    height: auto;
    display: block;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
    transition: box-shadow 0.25s ease, transform 0.25s ease;
  }

  .photo-card:hover img {
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
  }

  .photo-caption {
    margin-top: 0.5rem;
    font-size: 0.85rem;
    color: var(--global-text-color-light);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 4px;
  }

  .photo-title {
    font-weight: 500;
    color: var(--global-text-color);
  }

  .photo-location {
    font-family: monospace;
    font-size: 0.75rem;
  }
</style>

<div class="photo-collage">
  {% for item in site.data.photos %}
    <div class="photo-card">
      <img src="{{ item.image | relative_url }}" alt="{{ item.title }}" data-zoomable loading="lazy">
      {% if item.title or item.location %}
        <div class="photo-caption">
          {% if item.title %}<span class="photo-title">{{ item.title }}</span>{% endif %}
          {% if item.location %}<span class="photo-location">{{ item.location }}</span>{% endif %}
        </div>
      {% endif %}
    </div>
  {% endfor %}
</div>
