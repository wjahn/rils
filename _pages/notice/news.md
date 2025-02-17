---
title: "News"
layout: single
permalink: /notice/news/
sidebar:
 nav: "notice-nav"
---

{% assign news_posts = site.posts | where: "categories", "news" | sort: "date" | reverse %}

<div class="news-container">
{% for post in news_posts %}
 <article class="news-item">
   <div class="news-image">
     {% if post.thumbnail %}
       <img src="{{ post.thumbnail }}" alt="{{ post.title }}">
     {% endif %}
   </div>
   <div class="news-content">
     <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
     <p class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</p>
     {% if post.excerpt %}
       <p>{{ post.excerpt }}</p>
     {% endif %}
   </div>
 </article>
{% endfor %}
</div>