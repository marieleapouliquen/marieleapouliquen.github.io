---
layout: default
permalink: /
title: Marie-Léa Pouliquen
description: Marie-Léa Pouliquen — Doctorante en sciences et humanités environnementales, Université de Rennes
---

<div class="home-hero">
  <div class="home-intro">
    <p>Bonjour ! Je suis <strong>Marie-Léa Pouliquen</strong>, doctorante en sciences et sociologie de l'environnement à l'<strong>Université de Rennes</strong>.</p>
    <p>Mon travail explore la <strong>relation que les jeunes générations entretiennent au vivant</strong>, à la croisée des sciences sociales, des sciences naturelles et de la pédagogie. J'ai aussi enseigné trois ans en lycée, et je conçois des ressources pédagogiques en libre accès.</p>
    <p>Bonne visite — n'hésitez pas à me contacter pour toute question, collaboration ou intervention.</p>
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

## Projets

<div class="home-projects">

  <a href="{{ '/cap-nature/' | relative_url }}" class="project-card">
    <div class="project-card-image" style="background-image: url('{{ '/assets/img/projet-cap-nature.jpg' | relative_url }}');"></div>
    <div class="project-card-content">
      <span class="project-card-tag">Recherche · Ateliers</span>
      <h3>Cap Nature</h3>
      <p>Des capteurs participatifs pour renouer la relation au vivant des jeunes générations. Ma thèse en cours et un wiki collaboratif pour les enseignants.</p>
      <span class="project-card-link">Découvrir →</span>
    </div>
  </a>

  <a href="{{ '/terra-klima/' | relative_url }}" class="project-card">
    <div class="project-card-image" style="background-image: url('{{ '/assets/img/projet-terra-klima.jpg' | relative_url }}');"></div>
    <div class="project-card-content">
      <span class="project-card-tag">Pédagogie · Climat</span>
      <h3>Terra Klima</h3>
      <p>Plateforme de simulateurs interactifs pour enseigner la climatologie : équilibre radiatif, trajectoires d'émissions, dynamique atmosphérique. En libre accès.</p>
      <span class="project-card-link">Explorer →</span>
    </div>
  </a>

</div>

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
