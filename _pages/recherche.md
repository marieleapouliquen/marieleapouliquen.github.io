---
layout: default
permalink: /recherche/
title: ""
description: Travaux de recherche, projet doctoral Cap Nature et publications
body_class: page-cv
---

<div class="cv-layout">

<aside class="cv-toc">
  <ul class="cv-toc-list">
    <li><a href="#these">Thèse en cours</a></li>
    <li><a href="#cadre">Cadre institutionnel</a></li>
    <li><a href="#methodes">Approche méthodologique</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#anterieur">Rapports de stage</a></li>
  </ul>
</aside>

<div class="cv-main">

<div class="cv-header">
  <div class="cv-header-text">
    <h1>Recherche</h1>
    <p style="color: var(--color-muted); margin: 0;">Travaux doctoraux, publications et projets de recherche.</p>
  </div>
</div>

<p><strong>Comment les 15-25 ans se relient-ils aujourd'hui au vivant</strong>, à l'heure où les expériences directes de nature se raréfient et où le numérique s'invite partout ? C'est la question qui structure mon travail doctoral, à la <strong>croisée de la sociologie de l'environnement, de la psychologie environnementale et de l'écologie sensorielle</strong>.</p>

<section class="cv-section" id="these">
<h2>Thèse en cours · Cap Nature</h2>

<div class="research-feature">
  <div class="research-feature-content">
    <p class="research-feature-meta">Doctorat en cours · 2024 — 2027</p>
    <h3>Cap Nature : des capteurs pour renouer avec le vivant</h3>
    <p>Comment les technologies participatives (capteurs environnementaux, applications d'identification d'espèces) peuvent-elles servir de <strong>seuil</strong> vers une expérience sensible du vivant chez les 15-25 ans, plutôt que de s'y substituer&nbsp;?</p>
    <p>Mon doctorat articule <strong>trois études complémentaires</strong>&nbsp;:</p>
    <ul>
      <li><strong>Étude 1</strong> — Enquête quantitative sur les facteurs sociaux, culturels et expérientiels qui façonnent le rapport au vivant des 15-25 ans.</li>
      <li><strong>Étude 2</strong> — Revue systématique (méthodologie PRISMA) des pédagogies de reconnexion à la nature inspirées des sciences participatives.</li>
      <li><strong>Étude 3</strong> — Protocole expérimental mobilisant des capteurs environnementaux participatifs (bioacoustique, identification d'espèces) avec des lycéen·ne·s et étudiant·e·s.</li>
    </ul>
    <p style="margin-top: 1rem;"><a href="{{ '/cap-nature/' | relative_url }}" class="external-link">→ Voir le projet et le wiki des ateliers</a></p>
  </div>
</div>
</section>

<section class="cv-section" id="publications">
<h2>Publications</h2>

<h3 style="margin-top: 0;">Articles publiés</h3>

<div class="publication">
  <p class="pub-title">Aerosols on the Tropical Island of La Réunion : Assessment of Climatology, Origin of Variability and Trend</p>
  <p class="pub-authors">Duflot, V., Bègue, N., <strong>Pouliquen, M.-L.</strong>, Goloub, P., &amp; Metzger, J.-M.</p>
  <p class="pub-venue"><em>Remote Sensing</em>, 14(19), 4945 — 2022</p>
  <p><a href="https://doi.org/10.3390/rs14194945" class="external-link">DOI : 10.3390/rs14194945 ↗</a></p>
</div>

</section>

<section class="cv-section" id="anterieur">
<h2>Recherches antérieures</h2>

<div class="publication">
  <p class="pub-title">Paramétrisation de la diffusivité verticale turbulente dans l'Anticyclone de Mousson Asiatique</p>
  <p class="pub-authors"><strong>Pouliquen, M.-L.</strong> (mémoire de Master 2 Recherche)</p>
  <p class="pub-venue">Laboratoire de Météorologie Dynamique, ENS Ulm — 2019</p>
  <p>Sous la direction du Pr. Bernard Legras. Modélisation lagrangienne (Traczilla-Flexpart).</p>
</div>

<div class="publication">
  <p class="pub-title">Coupling Sea Surface Temperature with Atmospheric Convection in the Tropical Atlantic</p>
  <p class="pub-authors"><strong>Pouliquen, M.-L.</strong> (mémoire de Master 1)</p>
  <p class="pub-venue">Max Planck Institut für Meteorologie, Hambourg — 2018</p>
  <p>Sous la direction du Pr. Björn Stevens et du Dr. James Ruppert. Modélisation couplée océan-atmosphère (PyOM, ICON).</p>
</div>

<div class="publication">
  <p class="pub-title">Climatologie des propriétés optiques des aérosols troposphériques mesurés à La Réunion</p>
  <p class="pub-authors"><strong>Pouliquen, M.-L.</strong> (mémoire d'ingénieur)</p>
  <p class="pub-venue">Laboratoire de l'Atmosphère et des Cyclones, La Réunion — 2017</p>
  <p>Sous la direction du Dr. Valentin Duflot. Inversion lidar/satellite des aérosols troposphériques.</p>
</div>

</section>

</div>
</div>

<script>
// Sommaire qui surligne la section active au scroll
document.addEventListener('DOMContentLoaded', function() {
  const sections = document.querySelectorAll('.cv-section');
  const tocLinks = document.querySelectorAll('.cv-toc-list a');

  function setActive() {
    let current = '';
    sections.forEach(section => {
      const rect = section.getBoundingClientRect();
      if (rect.top <= 100) current = section.id;
    });
    tocLinks.forEach(link => {
      link.classList.toggle('active', link.getAttribute('href') === '#' + current);
    });
  }

  window.addEventListener('scroll', setActive);
  setActive();

  // Smooth scroll
  tocLinks.forEach(link => {
    link.addEventListener('click', function(e) {
      e.preventDefault();
      const target = document.querySelector(this.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });
  });
});
</script>
