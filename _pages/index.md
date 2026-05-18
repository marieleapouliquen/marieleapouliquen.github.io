---
layout: default
permalink: /
title: Accueil
description: Marie-Léa Pouliquen — Doctorante en sciences et humanités environnementales, Université de Rennes
---

## Bienvenue

Comment les 15-25 ans se relient-ils aujourd'hui au vivant, à l'heure où les expériences directes de nature se raréfient et où le numérique s'invite partout&nbsp;? C'est la question que j'explore à la croisée de la **sociologie**, de la **psychologie environnementale** et de l'**écologie sensorielle**.

Ma recherche doctorale, **Cap Nature**, articule enquêtes quantitatives, revue systématique et ateliers expérimentaux mobilisant des capteurs participatifs (bioacoustique, applications d'identification d'espèces). L'hypothèse centrale : bien scénarisés, ces outils ne substituent pas la nature à un écran — ils en deviennent un **seuil**.

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

<table class="news-table">
  {% for news_item in site.news reversed %}
    <tr>
      <td class="news-date">{{ news_item.date | date: "%d %b %Y" }}</td>
      <td>{{ news_item.content | markdownify }}</td>
    </tr>
  {% endfor %}
</table>
