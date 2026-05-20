---
layout: default
permalink: /blog/
title: ""
description: Actualités, conférences, médiation scientifique
---

<div class="blog-header">
  <div class="blog-header-text">
    <h1>Blog</h1>
    <p>Actualités, conférences et médiation scientifique au fil de l'eau.</p>
  </div>
  <div class="blog-header-banner" role="img" aria-label="Conférence à l'Institut Franco-Américain de Rennes, décembre 2024"></div>
</div>

<div class="blog-list">
{% assign sorted_posts = site.news | sort: 'date' | reverse %}
{% for item in sorted_posts %}
  <article class="blog-entry" id="{{ item.date | date: '%Y-%m-%d' }}">  
    <p class="blog-date">{{ item.date | date: "%-d %B %Y" }}</p>
    {% if item.title %}<h2 class="blog-title">{{ item.title }}</h2>{% endif %}
    {% if item.venue %}<p class="blog-venue">{{ item.venue }}</p>{% endif %}
    <div class="blog-content">
      {{ item.content | markdownify }}
    </div>
  </article>
{% endfor %}
</div>
