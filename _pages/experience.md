---
layout: page
title: experience
permalink: /experience/
nav: true
nav_order: 2
---

<style>
  .exp-list {
    list-style: none;
    padding-left: 0;
    margin-top: 1.5rem;
  }
  .exp-item {
    margin-bottom: 2.75rem;
    padding-bottom: 1.75rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .exp-item:last-child {
    border-bottom: none;
  }
  .exp-header {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    gap: 0.85rem;
    margin-bottom: 0.35rem;
  }
  .exp-title-group {
    flex: 1 1 auto;
  }
  .exp-role {
    font-size: 1.25rem;
    font-weight: 700;
    margin: 0;
    line-height: 1.3;
    color: var(--global-text-color);
  }
  .exp-company {
    font-weight: 400;
    color: var(--global-theme-color);
  }
  .exp-logo {
    max-height: 32px;
    max-width: 48px;
    width: auto;
    object-fit: contain;
    opacity: 0.95;
  }
  .exp-meta {
    font-size: 0.875rem;
    font-family: monospace;
    font-weight: 600;
    color: var(--global-text-color-light);
    margin-bottom: 0.75rem;
  }
  .exp-highlights {
    margin-top: 0.5rem;
    padding-left: 1.25rem;
    line-height: 1.6;
    color: var(--global-text-color);
  }
  .exp-highlights li {
    margin-bottom: 0.4rem;
  }
</style>

<ul class="exp-list">
  {% for exp in site.data.experience %}
    <li class="exp-item">
      <div class="exp-header">
        {% if exp.logo %}
          <a href="{{ exp.url }}" target="_blank" rel="noopener noreferrer" style="display: inline-flex; align-items: center; flex-shrink: 0;">
            <img src="{{ exp.logo | relative_url }}" alt="{{ exp.company }}" class="exp-logo"{% if exp.logo_style %} style="{{ exp.logo_style }}"{% endif %}>
          </a>
        {% endif %}
        <div class="exp-title-group">
          <h4 class="exp-role">
            {{ exp.role }} — <a href="{{ exp.url }}" target="_blank" rel="noopener noreferrer" class="exp-company">{{ exp.company }}</a>
          </h4>
        </div>
      </div>
      <div class="exp-meta">[{{ exp.date }}] | {{ exp.location }}</div>
      {% if exp.highlights %}
        <ul class="exp-highlights">
          {% for bullet in exp.highlights %}
            <li>{{ bullet }}</li>
          {% endfor %}
        </ul>
      {% endif %}
    </li>
  {% endfor %}
</ul>
