---
layout: default
permalink: /blog/
title: ""
description: Actualités, conférences, médiation scientifique
---


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
