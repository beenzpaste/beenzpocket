---
layout: default
title: Collections
permalink: /collections/
---

<h1>Collections</h1>

<aside class="collections-toc">
  <ul>
    <li><a href="#essays">Essays</a></li>
    <li><a href="#books">Books</a></li>
    <li><a href="#articles">Articles</a></li>
  </ul>
</aside>

<h2 id="essays">Essays</h2>
<ul>
  {% for entry in site.essays %}
    <li>
      <a href="{{ entry.url | relative_url }}">{{ entry.title }}</a>
      {% if entry.date %}
        <small>({{ entry.date | date: "%B %d, %Y" }})</small>
      {% endif %}
    </li>
  {% endfor %}
</ul>

<h2 id="books">Books</h2>
<ul>
  {% assign sorted_books = site.books | sort: "date" | reverse %}
  {% for entry in sorted_books %}
    <li>
      {% if entry.type == "external" and entry.link %}
        <a href="{{ entry.link }}" target="_blank">{{ entry.title }}</a>
      {% else %}
        <a href="{{ entry.url | relative_url }}">{{ entry.title }}</a>
      {% endif %}
      {% if entry.author %}
        <small>by {{ entry.author }}</small>
      {% endif %}
    </li>
  {% endfor %}
</ul>

<h2 id="articles">Articles</h2>
<ul>
  {% assign sorted_articles = site.articles | sort: "date" | reverse %}
  {% for entry in sorted_articles %}
    <li>
      {% if entry.link %}
        <a href="{{ entry.link }}" target="_blank" rel="noopener">{{ entry.title }}</a>
        {% if entry.source %}
          <small>({{ entry.source }})</small>
        {% endif %}
      {% else %}
        {{ entry.title }}
      {% endif %}
    </li>
  {% endfor %}
</ul>