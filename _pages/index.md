---
layout: default
permalink: /
title: ""
description: Marie-Léa Pouliquen — doctorante en sociologie de l'environnement et sciences du climat à l'Université de Rennes
---

<header class="home-name">
  <h1><strong>Marie-Léa</strong> Pouliquen</h1>
</header>

<p class="home-tagline">Doctorante en sociologie de l'environnement et sciences du climat à l'<a href="https://www.univ-rennes.fr/">Université de Rennes</a>.</p>

<div class="home-hero">
  <div class="home-intro">
    <p>Bonjour ! Je suis doctorante au laboratoire <a href="https://geosciences.univ-rennes.fr/">Géosciences Rennes</a> (UMR 6118) et au laboratoire <a href="https://eso.cnrs.fr/">ESO</a> (Espaces et Sociétés, UMR 6590), sous la direction de <strong>Véronique Van Tilbeurgh</strong> et <strong>Laurent Longuevergne</strong>, avec le co-encadrement de <strong>Gladys Barragan-Jason</strong>.</p>

    <p>Mes travaux explorent la <strong>relation que les jeunes générations entretiennent au vivant</strong>, à la croisée des sciences sociales, de la psychologie environnementale et de l'écologie sensorielle. À travers ma thèse <a href="{{ '/cap-nature/' | relative_url }}"><strong>Cap Nature</strong></a>, j'étudie comment les capteurs environnementaux participatifs peuvent devenir un <strong>médiateurs</strong> d'une expérience sensible de la nature</p>

    <p>Avant la thèse, j'ai étudié la physique de l'atmosphère et du climat</strong> (École des Mines de Douai, ENS Ulm), puis <strong>enseignante à temps plein en sciences environnementales</strong> pendant trois ans à l'<a href="{{ '/sya/' | relative_url }}">École Américaine de Rennes</a>. J'enseigne aujourd'hui la climatologie en licence à l'Université de Rennes, et je conçois des <strong>ressources pédagogiques en libre accès</strong> (<a href="{{ '/terra-klima/' | relative_url }}">Terra Klima</a>, <a href="https://marieleapouliquen.github.io/wiki-cap-nature/">Wiki Cap Nature</a>).</p>

    <p>N'hésitez pas à me contacter pour toute question, collaboration ou intervention.</p>
  </div>
  <img src="{{ '/assets/img/profile.jpg' | relative_url }}" alt="Marie-Léa Pouliquen" class="home-photo">
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
