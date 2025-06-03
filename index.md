---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home
---


<div style="height: 2rem;"></div>

<div class="about-wrapper">
  <div class="about-image">
    <img src="assets/images/beenz_logo.png" alt="beenz logo" />
  </div>
  <div class="about-text">
    <h2 style="font-style: italic; line-height: 1.2;">Love,</h2>
    <h1 style="font-style: italic; line-height: 0.2;">Sheena</h1>
    <br>
    <p stule="line-height: 2;">Welcome to Beenz’ Pocket, an amalgamation of works done, experimentation, and interesting tidbits that evolves with me. <br>
    <br>
    Note: This website is still a work in progress. </p>
  </div>
</div>


<hr>
<div style="height: 2rem;"></div>

<h2>My Work</h2>
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
