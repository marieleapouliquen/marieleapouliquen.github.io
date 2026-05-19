---
layout: default
permalink: /
title: ""
description: Marie-Léa Pouliquen — doctorante
---

<header class="home-name">
  <h1><strong>Marie-Léa</strong> Pouliquen</h1>
</header>

<p class="home-tagline">Doctorante-ingénieure CNRS en sciences et humanités environnementales à l'Université de Rennes 2.</p>

<div class="home-hero home-hero-card">
  <div class="home-intro">
    <p>Bonjour ! Je suis doctorante au laboratoire <strong>Géosciences Rennes</strong> (UMR 6118) et au laboratoire <strong>ESO</strong> (Espaces et Sociétés, UMR 6590), sous la direction de <strong>Véronique Van Tilbeurgh</strong> et <strong>Laurent Longuevergne</strong>, avec le co-encadrement de <strong>Gladys Barragan-Jason</strong>.</p>

    <p> Avant la thèse, j'ai étudié la physique de l'atmosphère et du climat (École des Mines de Douai, ENS Ulm), puis j'ai été <strong>enseignante à temps plein en sciences environnementales</strong> pendant trois ans à l'<a href="{{ '/sya/' | relative_url }}">École Américaine de Rennes</a>.</p>

    <p>A présent, j'explore la <strong>relation que les jeunes générations entretiennent au vivant</strong>, à la croisée des sciences sociales, de la psychologie environnementale et de l'écologie sensorielle. À travers ma thèse <a href="{{ '/cap-nature/' | relative_url }}"><strong>Cap Nature</strong></a>, j'étudie comment les capteurs environnementaux participatifs peuvent devenir <strong>médiateurs</strong> d'une expérience sensible de la nature. J'enseigne également la climatologie en licence à l'Université de Rennes, et je conçois des <strong>ressources pédagogiques en libre accès</strong> (<a href="{{ '/terra-klima/' | relative_url }}">Terra Klima</a>, <a href="https://marieleapouliquen.github.io/wiki-cap-nature/">Wiki Cap Nature</a>).</p>

    <p>N'hésitez pas à me contacter pour toute question, collaboration ou intervention.</p>
  </div>
<div class="home-photo-wrap">
  <img src="{{ '/assets/img/profile.jpg' | relative_url }}" alt="Marie-Léa Pouliquen" class="home-photo">

  <div class="home-contact-block">
    <p class="contact-email"><strong>Email</strong><br><a href="mailto:marie-lea.pouliquen@gmail.com">marie-lea.pouliquen@gmail.com</a></p>

    <div class="home-contact">
      <a href="https://www.linkedin.com/in/marieleapouliquen/" class="contact-icon" target="_blank" rel="noopener" aria-label="LinkedIn" title="LinkedIn">
        <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20"><path d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19a.66.66 0 000 .14V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"/></svg>
      </a>
      <a href="https://orcid.org/0000-0002-6147-3683" class="contact-icon" target="_blank" rel="noopener" aria-label="ORCID" title="ORCID">
        <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20"><path d="M12 0C5.372 0 0 5.372 0 12s5.372 12 12 12 12-5.372 12-12S18.628 0 12 0zM7.369 4.378c.525 0 .947.431.947.947 0 .525-.422.947-.947.947-.525 0-.946-.422-.946-.947 0-.516.421-.947.946-.947zm-.722 3.038h1.444v10.041H6.647V7.416zm3.562 0h3.9c3.712 0 5.344 2.653 5.344 5.025 0 2.578-2.016 5.025-5.325 5.025h-3.919V7.416zm1.444 1.303v7.444h2.297c3.272 0 4.022-2.484 4.022-3.722 0-2.016-1.284-3.722-4.097-3.722h-2.222z"/></svg>
      </a>
    </div>
  </div>
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

## Au-delà de la recherche

Au-delà de mes activités académiques, j'aime peindre et photographier ce qui m'entoure. Ces pratiques nourrissent ma sensibilité au vivant et alimentent en retour ma manière d'aborder la médiation scientifique. Mon site artistique : <a href="http://mlykscorner.fr">MLYK's Corner</a>.

