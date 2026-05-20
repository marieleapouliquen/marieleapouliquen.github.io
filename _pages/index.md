---
layout: default
permalink: /
title: ""
description: Marie-Léa Pouliquen — doctorante
---

<a href="{{ '/about/' | relative_url }}" class="home-identity" title="À propos" aria-label="Aller à la page À propos">
  <header class="home-name">
    <h1>Marie-Léa Pouliquen</h1>
  </header>

  <p class="home-tagline">Doctorante-ingénieure CNRS en sciences et humanités environnementales à l'Université de Rennes 2.</p>

<div class="home-banner" role="img" aria-label="Paysage forestier"></div>

## Explorer mon travail

<div class="home-cards">
  <a href="{{ '/recherche/' | relative_url }}" class="home-card">
    <h3>Recherche</h3>
    <span class="home-card-meta">→ Voir mes travaux</span>
  </a>

  <a href="{{ '/enseignement/' | relative_url }}" class="home-card">
    <h3>Enseignement</h3>
    <span class="home-card-meta">→ Cours de climatologie et ressources pédagogiques</span>
  </a>

  <a href="{{ '/blog/' | relative_url }}" class="home-card">
    <h3>Blog</h3>
    <span class="home-card-meta">→ Projets récents et conférences grand public</span>
  </a>

</div>

## Actualités récentes

<table class="news-table">
{% assign sorted_news = site.news | sort: 'date' | reverse %}
{% for item in sorted_news limit:5 %}
  <tr>
    <td class="news-date">{{ item.date | date: "%d %b %Y" }}</td>
    <td class="news-content">
      {% if item.title %}
        <a href="{{ '/blog/' | relative_url }}#{{ item.date | date: '%Y-%m-%d' }}" class="news-title">{{ item.title }}</a>
      {% endif %}
      {% if item.venue %}<span class="news-venue">{{ item.venue }}</span>{% endif %}
    </td>
  </tr>
{% endfor %}
</table>
