---
title: "Gallery"
layout: single
permalink: /notice/gallery/
sidebar:
  nav: "notice-nav"
---

{% assign gallery_posts = site.posts | where: "categories", "gallery"  | sort: "date" | reverse %}

<div class="gallery-grid">
{% for post in gallery_posts %}
  <div class="gallery-item">
    <a href="{{ post.url }}">
      {% if post.thumbnail %}
        <img src="{{ post.thumbnail }}" alt="{{ post.title }}">
      {% endif %}
      <h3>{{ post.title }}</h3>
      <p class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</p>
    </a>
  </div>
{% endfor %}
</div>