---
layout: page
title: Works
permalink: /works/
---

<h1>My Projects</h1>

<div class="works-grid">
  {% for work in site.works %}
    <a href="{{ work.url | relative_url }}" class="work-link">
      <div class="work-card">
        <img src="{{ work.image | relative_url }}" alt="{{ work.title }}">
        <div class="card-overlay">
          <h2>{{ work.title }}</h2>
          <h3>{{ work.subtitle }}</h3>
        </div>
      </div>
    </a>
  {% endfor %}
</div>