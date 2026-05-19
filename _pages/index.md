---
layout: default
permalink: /
title: Marie-Léa Pouliquen
description: Marie-Léa Pouliquen — Doctorante en sciences et humanités environnementales, Université de Rennes
---

<div class="home-hero">
  <div class="home-intro">
    <p>Comment les 15-25 ans se relient-ils aujourd'hui au vivant, à l'heure où les expériences directes de nature se raréfient et où le numérique s'invite partout ? C'est la question que j'explore à la croisée de la <strong>sociologie</strong>, de la <strong>psychologie environnementale</strong> et de l'<strong>écologie sensorielle</strong>.</p>
    <p>Ma recherche doctorale, <strong>Cap Nature</strong>, articule enquêtes quantitatives, revue systématique et ateliers expérimentaux mobilisant des capteurs participatifs (bioacoustique, applications d'identification d'espèces). L'hypothèse centrale : bien scénarisés, ces outils ne substituent pas la nature à un écran — ils en deviennent un <strong>seuil</strong>.</p>
  </div>
  <img src="{{ '/assets/img/profile.jpg' | relative_url }}" alt="Marie-Léa Pouliquen" class="home-photo">
</div>

<div class="cards">
  <div class="card">
    <h3><a href="{{ '/recherche/' | relative_url }}">Recherche</a></h3>
    <p>Thèse <em>Cap Nature</em> et publications en sciences du climat et de l'atmosphère.</p>
  </div>
  <div class="card">
    <h3><a href="{{ '/enseignement/' | relative_url }}">Enseignement</a></h3>
    <p>Cours universitaires en géosciences, géographie environnementale et sciences de l'environnement.</p>
  </div>
  <div class="card">
    <h3><a href="{{ '/diffusion/' | relative_url }}">Diffusion</a></h3>
    <p>Conférences grand public, ressources pédagogiques, médiation scientifique.</p>
  </div>
</div>

## Actualités

## Actualités

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
