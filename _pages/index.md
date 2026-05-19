---
layout: default
permalink: /
title: ""
description: Marie-Léa Pouliquen — doctorante
---

<header class="home-name">
  <h1><strong>Marie-Léa</strong> Pouliquen</h1>
</header>

<p class="home-tagline">Doctorante-ingénieure CNRS en sciences et humanités environnementales</p>

## Explorer mon travail

<div class="home-cards">
  <a href="{{ '/recherche/' | relative_url }}" class="home-card">
    <h3>Recherche</h3>
    <span class="home-card-meta">→ Voir mes travaux</span>
  </a>

  <a href="{{ '/enseignement/' | relative_url }}" class="home-card">
    <h3>Enseignement</h3>
    <span class="home-card-meta">→ Voir ma pratique</span>
  </a>

  <a href="{{ '/diffusion/' | relative_url }}" class="home-card">
    <h3>Diffusion</h3>
    <span class="home-card-meta">→ Voir mes interventions</span>
  </a>
  
</div>

## Actualités récentes

<table class="news-table">
{% assign sorted_news = site.news | sort: 'date' | reverse %}
{% for item in sorted_news limit:5 %}
  <tr>
    <td class="news-date">{{ item.date | date: "%d %b %Y" }}</td>
    <td>{{ item.content | markdownify | remove: '<p>' | remove: '</p>' }}</td>
  </tr>
{% endfor %}
</table>

<p style="text-align: right; margin-top: 1rem;"><a href="{{ '/actualites/' | relative_url }}">Voir toutes les actualités →</a></p>
