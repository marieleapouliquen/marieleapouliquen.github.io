---
layout: default
permalink: /actualites/
title: Actualités
description: Conférences, publications, formations et événements
---

Retrouvez ici l'ensemble de mes actualités : conférences, interventions publiques, publications, formations, distinctions et collaborations.

<table class="news-table">
{% assign sorted_news = site.news | sort: 'date' | reverse %}
{% for item in sorted_news %}
  <tr>
    <td class="news-date">{{ item.date | date: "%d %b %Y" }}</td>
    <td>{{ item.content | markdownify | remove: '<p>' | remove: '</p>' }}</td>
  </tr>
{% endfor %}
</table>
