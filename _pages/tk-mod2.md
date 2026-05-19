---
layout: default
permalink: /terra-klima/co2-rechauffement/
title: ""
description: "Projection du climat jusqu'en 2100 selon différents scénarios — Terra Klima"
---

<p style="margin-bottom: 1.5rem;"><a href="{{ '/enseignement/' | relative_url }}">← Retour à la page Enseignement</a></p>

<!-- ============ TERRA KLIMA · MODÈLE 2 · CO₂ ET RÉCHAUFFEMENT ============ -->
<style>
  .terra-klima-wrap {
    --tk-bg: #ffffff;
    --tk-ink: #111827;
    --tk-muted: #374151;
    --tk-card: #c0f0e0;
    --tk-line: #c0f0e0;
    --tk-accent: #0ea5e9;
    --tk-accent-ink: #fff;
    --tk-wrap: 1100px;
    --tk-gap: 22px;

    max-width: var(--tk-wrap);
    margin: 0 auto;
    color: var(--tk-ink);
    font-size: 15px;
    line-height: 1.6;
  }

  .terra-klima-wrap * { box-sizing: border-box; }

  .terra-klima-wrap .tk-hero {
    background: #fff;
    border: 1px solid var(--tk-line);
    border-radius: 16px;
    padding: clamp(22px, 3vw, 36px);
    box-shadow: 0 1px 2px rgba(0,0,0,.04);
    margin-bottom: var(--tk-gap);
  }
  .terra-klima-wrap .tk-hero h1 {
    margin: 0 0 10px;
    font-size: clamp(28px, 4vw, 32px);
    color: var(--tk-ink);
    font-family: inherit;
  }
  .terra-klima-wrap .tk-hero p {
    margin: 0;
    color: var(--tk-muted);
    font-size: clamp(16px, 2.2vw, 18px);
  }
  .terra-klima-wrap .tk-cta { display: flex; gap: 12px; flex-wrap: wrap; margin-top: 14px; }
  .terra-klima-wrap .tk-btn {
    display: inline-block;
    padding: 10px 14px;
    border-radius: 10px;
    text-decoration: none;
    font-weight: 700;
    border: 1px solid var(--tk-line);
  }
  .terra-klima-wrap .tk-btn.primary { background: var(--tk-accent); color: var(--tk-accent-ink); border-color: transparent; }
  .terra-klima-wrap .tk-btn.ghost { color: var(--tk-ink); background: #fff; }

  .terra-klima-wrap section { margin: clamp(28px, 4vw, 48px) 0; }

  .terra-klima-wrap .tk-grid-3 {
    display: grid;
    gap: var(--tk-gap);
    grid-template-columns: 2fr 1fr;
  }
  @media (max-width: 980px) {
    .terra-klima-wrap .tk-grid-3 { grid-template-columns: 1fr; }
  }
  .terra-klima-wrap .tk-card {
    background: #fff;
    border: 1px solid var(--tk-line);
    border-radius: 12px;
    padding: 18px;
    box-shadow: 0 1px 2px rgba(0,0,0,.04);
  }
  .terra-klima-wrap .tk-card h2,
  .terra-klima-wrap .tk-card h3 { margin: 0 0 10px; color: var(--tk-ink); font-family: inherit; }
  .terra-klima-wrap .tk-muted { color: var(--tk-muted); }
  .terra-klima-wrap .tk-sep { height: 1px; background: var(--tk-line); margin: 18px 0; }
  .terra-klima-wrap .tk-list { list-style: none; padding: 0; margin: 0; display: grid; gap: 10px; }
  .terra-klima-wrap .tk-list li {
    padding: 10px 12px;
    border: 1px solid var(--tk-line);
    border-radius: 10px;
    background: #fff;
  }

  .terra-klima-wrap .tk-module {
    background: #fff;
    border: 1px solid var(--tk-line);
    border-radius: 14px;
    padding: clamp(14px, 2vw, 20px);
    box-shadow: 0 1px 3px rgba(0,0,0,.05);
  }
  .terra-klima-wrap .tk-module h2 { margin: 0 0 6px; color: var(--tk-ink); font-family: inherit; }
  .terra-klima-wrap .tk-caption { font-size: 15px; color: var(--tk-muted); margin: 6px 0 12px; }

  .terra-klima-wrap .tk-row-plots {
    display: grid;
    gap: 14px;
    grid-template-columns: repeat(3, 1fr);
  }
  @media (max-width: 980px) {
    .terra-klima-wrap .tk-row-plots { grid-template-columns: repeat(2, 1fr); }
  }
  @media (max-width: 700px) {
    .terra-klima-wrap .tk-row-plots { grid-template-columns: 1fr; }
  }

  .terra-klima-wrap #tk-sel-year {
    padding: 6px 12px;
    border: 1px solid var(--tk-line);
    border-radius: 10px;
    min-width: 190px;
    font-weight: 600;
    background: #fff;
    color: var(--tk-ink);
  }
  .terra-klima-wrap label { color: var(--tk-ink); font-weight: 600; }
</style>

<div class="terra-klima-wrap">

  <div class="tk-hero">
    <h1>Projection du climat jusqu'en 2100</h1>
    <p>Explorez l'impact du calendrier de <strong>zéro émissions nettes</strong> sur le CO₂ atmosphérique, le <strong>forçage radiatif</strong> et la <strong>température moyenne</strong> avec ce simulateur.</p>
    <div class="tk-cta">
      <a href="#tk-simulateur" class="tk-btn primary">Lancer le simulateur</a>
      <a href="#tk-explications" class="tk-btn ghost">Comprendre le modèle</a>
    </div>
  </div>

  <section id="tk-simulateur">
    <div class="tk-module">
      <h2>Simulateur interactif</h2>
      <p class="tk-caption">Choisissez l'année de <em>zéro émissions nettes</em> et comparez au scénario « Business-as-usual ».</p>

      <div style="display:flex;gap:12px;align-items:center;flex-wrap:wrap;margin-bottom:8px;">
        <label for="tk-sel-year">Zéro émissions nettes en :</label>
        <select id="tk-sel-year">
          <option>2020</option><option>2030</option><option>2040</option><option>2050</option>
          <option>2060</option><option>2070</option><option>2080</option><option>2090</option>
        </select>
      </div>

      <div class="tk-row-plots">
        <div id="tk-plot-co2"></div>
        <div id="tk-plot-rf"></div>
        <div id="tk-plot-temp"></div>
      </div>

      <div style="font-style:italic;margin-top:8px;color:#6b7280;">
        Les courbes rouges représentent le scénario <b>Business-as-usual</b>. Les courbes pleines correspondent au scénario sélectionné.
      </div>
    </div>
  </section>

  <section id="tk-explications">
    <div class="tk-grid-3">
      <div class="tk-card">
        <h2>Comment fonctionne le modèle ?</h2>

        <h3>Le principe</h3>
        <p class="tk-muted">Le modèle suit de 1900 à 2100 l'évolution du <strong>CO₂</strong>, du <strong>forçage radiatif</strong> (énergie piégée) et de la <strong>température moyenne</strong>, avec un pas de temps de 5 ans. Deux trajectoires : <em>Business-as-usual</em> (croissance continue des émissions) et <em>Zéro émissions nettes</em> à une date choisie.</p>

        <div class="tk-sep"></div>

        <h3>Les équations (simplifiées)</h3>
        <ul class="tk-list">
          <li><b>CO₂ (Business-as-usual)</b> : croissance proportionnelle, à partir d'un état d'équilibre préindustriel (280 ppm).</li>
          <li><b>Forçage CO₂</b> : \(F = 4 \cdot \ln(CO₂/280)/\ln 2\) — soit +4 W/m² pour un doublement du CO₂.</li>
          <li><b>Effet « masque »</b> : les aérosols refroidissent ≈ −0,75 W/m² et disparaissent vite après l'arrêt des émissions.</li>
          <li><b>T° d'équilibre</b> : \(T_{eq} = F_{total} \times 0{,}75\) °C/(W/m²) (≈ 3 °C pour +4 W/m²).</li>
          <li><b>T° transitoire</b> : réponse lente \(\tau \approx 20\) ans (inertie océanique) : \(T_{t+1}=T_t+(T_{eq}-T_t)\,\Delta t/\tau\).</li>
        </ul>

        <div class="tk-sep"></div>

        <h3>À retenir</h3>
        <ul class="tk-list">
          <li><b>Chaque décennie compte</b> : 2030 ≠ 2070 pour la trajectoire du climat.</li>
          <li><b>Le CO₂ agit longtemps</b> : l'atmosphère et les océans mettent des décennies à s'ajuster.</li>
          <li><b>Modèle pédagogique</b> : il montre les ordres de grandeur, sans prétendre à la précision régionale.</li>
        </ul>
      </div>

      <aside class="tk-card">
        <h3>Hypothèses et limites</h3>
        <ul class="tk-list">
          <li>CO₂ traité comme gaz dominant (CH₄/N₂O non explicités).</li>
          <li>Sensibilité climatique moyenne (3 °C pour ×2 CO₂).</li>
          <li>Aérosols agrégés (effet masque simplifié).</li>
          <li>Pas de rétroactions complexes (glace/albédo, circulation océanique profonde, nuages).</li>
        </ul>
        <div class="tk-sep"></div>
        <h3>Conseils de lecture</h3>
        <ul class="tk-list">
          <li>Comparez la pente Business-as-usual vs Net-Zero.</li>
          <li>Regardez le délai entre Net-Zero et stabilisation de T°.</li>
          <li>Testez plusieurs dates et notez l'amplitude finale.</li>
        </ul>
      </aside>
    </div>
  </section>

</div>

<script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
<script>
(function(){
  const timeStep=5, eqCO2=280, initCO2=290, CO2_exp=0.0225, CO2RampExp=0.01;
  const aerosol_Wm2_now=-0.75, watts_m2_2x=4, climateSensitivity2x=3;
  const climateSensitivityWm2=climateSensitivity2x/watts_m2_2x, TResponseTime=20;

  const years=[]; for(let y=1900;y<=2100;y+=timeStep) years.push(y);

  const bauCO2=[initCO2], inoCO2=[0], rfCO2=[0], rfMask=[0], rfTot=[0], Teq=[0], TTrans=[0];
  for(let i=1;i<years.length;i++){
    const next=eqCO2 + (bauCO2[i-1]-eqCO2)*(1+CO2_exp*timeStep);
    bauCO2.push(next);
    inoCO2.push((bauCO2[i]-bauCO2[i-1])/timeStep);
    rfCO2.push(watts_m2_2x*Math.log(bauCO2[i]/eqCO2)/Math.log(2));
  }
  function makeAerosolCoeff(idx){
    const growth=(bauCO2[idx]-bauCO2[idx-1])/timeStep;
    return aerosol_Wm2_now/growth;
  }
  (function(){
    const idx2020=years.indexOf(2020), aerosolCoeff=makeAerosolCoeff(idx2020);
    for(let i=1;i<years.length;i++){
      rfMask.push(Math.max(inoCO2[i]*aerosolCoeff, aerosol_Wm2_now));
      rfTot.push(rfCO2[i]+rfMask[i]);
      Teq.push(rfTot[i]*climateSensitivityWm2);
      TTrans.push(TTrans[i-1]+(Teq[i]-TTrans[i-1])*(timeStep/TResponseTime));
    }
  })();

  function scenarioRamp(yearForChange){
    const iyrfc=years.indexOf(yearForChange);
    const rampCO2=[], rfTotRamp=[], TTransRamp=[];
    const rfCO2Ramp=[], rfMaskRamp=[], TeqRamp=[];
    for(let i=0;i<=iyrfc;i++){
      rampCO2.push(bauCO2[i]); rfTotRamp.push(rfTot[i]); TTransRamp.push(TTrans[i]);
      rfCO2Ramp.push(rfCO2[i]); rfMaskRamp.push(rfMask[i]); TeqRamp.push(Teq[i]);
    }
    for(let i=iyrfc+1;i<years.length;i++){
      const prev=rampCO2[i-1], next=prev+(eqCO2*1.2-prev)*(CO2RampExp*timeStep);
      rampCO2.push(next);
      const rfCO2i=watts_m2_2x*Math.log(next/eqCO2)/Math.log(2);
      rfCO2Ramp.push(rfCO2i); rfMaskRamp.push(0);
      const rfToti=rfCO2i; rfTotRamp.push(rfToti);
      const Teqi=rfToti*climateSensitivityWm2; TeqRamp.push(Teqi);
      TTransRamp.push(TTransRamp[i-1]+(Teqi-TTransRamp[i-1])*(timeStep/TResponseTime));
    }
    return {rampCO2, rfTotRamp, TTransRamp};
  }

  const YEARS_CUT=[2020,2030,2040,2050,2060,2070,2080,2090], RAMPS={};
  YEARS_CUT.forEach(y=>RAMPS[y]=scenarioRamp(y));

  const baseLayout = {
    paper_bgcolor: '#ffffff',
    plot_bgcolor:  '#ffffff',
    font: { family: 'system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif', size: 14, color: '#111827' },
    xaxis: {
      color:'#111827',
      gridcolor:'#e5e7eb',
      zerolinecolor:'#e5e7eb',
      tickfont: { size: 12 },
      title: { text: 'Année', font:{ size: 13 } }
    },
    yaxis: {
      color:'#111827',
      gridcolor:'#e5e7eb',
      zerolinecolor:'#e5e7eb',
      tickfont: { size: 12 },
      title: { text: '', font:{ size: 13 } }
    }
  };

  const layout = (titleText, yLabel, yRange=null) => ({
    ...baseLayout,
    title: { text: titleText, font: { size: 14 } },
    margin:{ t: 42, r: 10, b: 42, l: 52 },
    height: 300,
    xaxis: { ...baseLayout.xaxis, range:[1900,2100] },
    yaxis: {
      ...baseLayout.yaxis,
      title: { text: yLabel, font: { size: 13 } },
      ...(yRange ? { range: yRange } : {})
    },
    showlegend: false
  });

  Plotly.newPlot('tk-plot-co2', [
    { x:years, y:bauCO2, mode:'lines', line:{width:3, dash:'dash', color:'firebrick'} },
    { x:years, y:RAMPS[2020].rampCO2, mode:'lines', line:{width:4, color:'darkslategray'} }
  ], layout('Teneur atmosphérique en CO₂','CO₂ [ppm]',[250,1000]), {displayModeBar:false, responsive:true});

  Plotly.newPlot('tk-plot-rf', [
    { x:years, y:rfTot, mode:'lines', line:{width:3, dash:'dash', color:'firebrick'} },
    { x:years, y:RAMPS[2020].rfTotRamp, mode:'lines', line:{width:4, color:'seagreen'} }
  ], layout('Forçage radiatif total','W/m²',[0,8]), {displayModeBar:false, responsive:true});

  Plotly.newPlot('tk-plot-temp', [
    { x:years, y:TTrans, mode:'lines', line:{width:3, dash:'dash', color:'firebrick'} },
    { x:years, y:RAMPS[2020].TTransRamp, mode:'lines', line:{width:4, color:'goldenrod'} }
  ], layout('Réchauffement global','Température [°C]',[0,4]), {displayModeBar:false, responsive:true});

  document.getElementById('tk-sel-year').addEventListener('change', e=>{
    const y=parseInt(e.target.value,10), R=RAMPS[y];
    Plotly.restyle('tk-plot-co2', {y:[R.rampCO2]}, [1]);
    Plotly.restyle('tk-plot-rf', {y:[R.rfTotRamp]}, [1]);
    Plotly.restyle('tk-plot-temp', {y:[R.TTransRamp]}, [1]);
  });

  window.addEventListener('resize', ()=>['tk-plot-co2','tk-plot-rf','tk-plot-temp'].forEach(id=>{
    const el=document.getElementById(id); if(el) Plotly.Plots.resize(el);
  }));
})();
</script>

<script>
  window.MathJax = { tex: { inlineMath: [['\\(','\\)'], ['$', '$']] }, svg: { fontCache: 'global' } };
</script>
<script defer src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"></script>
