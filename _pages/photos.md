---
layout: page
title: '<i class="fa-regular fa-camera"></i>'
permalink: /photos/
nav: true
nav_order: 3
---

<script>
  document.title = "photos | " + (document.title.includes("|") ? document.title.split("|").slice(1).join("|").trim() : "{{ site.title }}");
</script>

<style>
  .photo-collage {
    width: 100vw;
    position: relative;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
    padding: 0 6rem;
    box-sizing: border-box;
    column-count: 4;
    column-gap: 1rem;
    margin-top: 1rem;
  }

  @media (min-width: 1500px) {
    .photo-collage {
      column-count: 5;
      padding: 0 8.5rem;
      column-gap: 1.25rem;
    }
  }

  @media (max-width: 1100px) {
    .photo-collage {
      column-count: 3;
      padding: 0 3.75rem;
      column-gap: 0.85rem;
    }
  }

  @media (max-width: 768px) {
    .photo-collage {
      column-count: 2;
      padding: 0 2rem;
      column-gap: 0.75rem;
    }
  }

  @media (max-width: 480px) {
    .photo-collage {
      column-count: 1;
      padding: 0 1.5rem;
    }
  }

  .photo-card {
    break-inside: avoid;
    margin-bottom: 1rem;
    display: inline-block;
    width: 100%;
    transition: transform 0.25s ease;
  }

  .photo-card img,
  .photo-card video {
    width: 100%;
    height: auto;
    display: block;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.25s ease, transform 0.25s ease;
  }

  .photo-card:hover img,
  .photo-card:hover video {
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
      {% if item.video %}
        <video src="{{ item.video | relative_url }}"{% if item.poster %} poster="{{ item.poster | relative_url }}"{% endif %} autoplay loop muted playsinline controls preload="auto"></video>
      {% else %}
        <img src="{{ item.image | relative_url }}" alt="{{ item.title }}" data-zoomable loading="lazy">
      {% endif %}
      {% comment %}
      {% if item.title or item.location %}
        <div class="photo-caption">
          {% if item.title %}<span class="photo-title">{{ item.title }}</span>{% endif %}
          {% if item.location %}<span class="photo-location">{{ item.location }}</span>{% endif %}
        </div>
      {% endif %}
      {% endcomment %}
    </div>
  {% endfor %}
</div>
