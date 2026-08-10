---
layout: default
permalink: /blog/
title: ""
description: Conférences et médiation scientifique
---

# Blog

<div class="blog-list">
{% assign all_items = site.news | concat: site.syntheses | sort: 'date' | reverse %}
{% for item in all_items %}
  <article class="blog-entry{% if item.collection == 'syntheses' %} blog-entry--synthese{% endif %}" id="{{ item.date | date: '%Y-%m-%d' }}">
    <p class="blog-date">{{ item.date | date: "%-d %B %Y" }}</p>

    {% if item.collection == 'syntheses' %}
      <h2 class="blog-title"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></h2>
      {% if item.venue %}<p class="blog-venue">{{ item.venue }}</p>{% endif %}
      {% if item.summary %}
      <div class="blog-content">
        <p>{{ item.summary }}</p>
      </div>
      {% endif %}
      <a class="blog-readmore" href="{{ item.url | relative_url }}">Lire la synthèse</a>
    {% else %}
      {% if item.title %}<h2 class="blog-title">{{ item.title }}</h2>{% endif %}
      {% if item.venue %}<p class="blog-venue">{{ item.venue }}</p>{% endif %}
      <div class="blog-content">
        {{ item.content | markdownify }}
      </div>
    {% endif %}
  </article>
{% endfor %}
</div>
