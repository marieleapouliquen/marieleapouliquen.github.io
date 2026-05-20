---
layout: default
permalink: /terra-klima/co2-rechauffement/
title: ""
description: "Projection du climat jusqu'en 2100 selon différents scénarios — Terra Klima"
---

<p style="margin-bottom: 1.5rem;"><a href="{{ '/enseignement/' | relative_url }}">← Retour à la page Enseignement</a></p>

<!-- ============ TERRA KLIMA · MODÈLE 2 · CO₂ ET RÉCHAUFFEMENT ============ -->
<style>
  .tk {
    --tk-ink: #111111;
    --tk-muted: #666666;
    --tk-light: #999999;
    --tk-bg: #ffffff;
    --tk-bg-alt: #fafafa;
    --tk-line: #e5e5e5;
    --tk-accent: #2c7da0;
    --tk-warn: #c1666b;
    --tk-serif: 'EB Garamond', Georgia, serif;
    --tk-sans: 'Inter', -apple-system, sans-serif;

    max-width: 820px;
    margin: 0 auto;
    color: var(--tk-ink);
    font-family: var(--tk-sans);
  }
  .tk * { box-sizing: border-box; }

  .tk-head { margin-bottom: 2.5rem; }
  .tk-eyebrow {
    font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.1em;
    color: var(--tk-muted); font-weight: 600; margin: 0 0 0.5rem;
  }
  .tk-head h1 {
    font-family: var(--tk-serif); font-size: 2rem; font-weight: 600;
    line-height: 1.2; margin: 0 0 0.8rem; color: var(--tk-ink);
  }
  .tk-head .tk-lead { font-size: 1.05rem; line-height: 1.6; color: var(--tk-muted); margin: 0; }

  .tk-step { margin: 2.5rem 0; padding-top: 2.5rem; border-top: 1px solid var(--tk-line); }
  .tk-step:first-of-type { border-top: none; padding-top: 0; }
  .tk-step-num {
    display: inline-flex; align-items: center; justify-content: center;
    width: 1.8rem; height: 1.8rem; border-radius: 50%;
    background: var(--tk-ink); color: #fff; font-size: 0.85rem; font-weight: 600;
    font-family: var(--tk-sans); margin-bottom: 0.8rem;
  }
  .tk-step h2 {
    font-family: var(--tk-serif); font-size: 1.4rem; font-weight: 600;
    margin: 0 0 0.6rem; color: var(--tk-ink); line-height: 1.3;
  }
  .tk-step p { font-size: 0.97rem; line-height: 1.65; color: var(--tk-muted); margin: 0 0 1rem; }
  .tk-step p strong { color: var(--tk-ink); }

  .tk-chart { margin: 1.2rem 0; border: 1px solid var(--tk-line); border-radius: 6px; padding: 0.5rem; background: var(--tk-bg); }

  .tk-controls {
    background: var(--tk-bg-alt); border: 1px solid var(--tk-line);
    border-radius: 6px; padding: 1.2rem 1.4rem; margin: 1.2rem 0;
    display: flex; align-items: center; gap: 0.8rem; flex-wrap: wrap;
  }
  .tk-controls label { font-size: 0.9rem; font-weight: 600; color: var(--tk-ink); }
  .tk-controls select {
    padding: 0.45rem 0.8rem; border: 1px solid var(--tk-line); border-radius: 4px;
    font-family: var(--tk-sans); font-size: 0.95rem; font-weight: 500; background: #fff; color: var(--tk-ink);
  }
  .tk-result {
    margin-left: auto; font-size: 0.9rem; color: var(--tk-ink);
  }
  .tk-result strong { font-family: var(--tk-serif); font-size: 1.15rem; color: var(--tk-accent); }

  .tk-takeaway {
    background: var(--tk-bg-alt); border-left: 3px solid var(--tk-accent);
    border-radius: 0 4px 4px 0; padding: 1.1rem 1.3rem; margin: 1.2rem 0;
  }
  .tk-takeaway p { margin: 0; font-size: 0.95rem; line-height: 1.6; color: var(--tk-ink); }
  .tk-takeaway p strong { font-family: var(--tk-serif); }

  .tk-hint { font-size: 0.88rem; font-style: italic; color: var(--tk-light); margin-top: 0.5rem; }

  .tk-legend { display: flex; gap: 1.5rem; flex-wrap: wrap; font-size: 0.85rem; color: var(--tk-muted); margin: 0.6rem 0 0; }
  .tk-legend span { display: inline-flex; align-items: center; gap: 0.4rem; }
  .tk-swatch { width: 22px; height: 0; border-top-width: 3px; border-top-style: solid; display: inline-block; }

  .tk-cols { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin: 1.2rem 0; }
  .tk-cols h3 { font-family: var(--tk-serif); font-size: 1.05rem; font-weight: 600; margin: 0 0 0.5rem; color: var(--tk-ink); }
  .tk-cols ul { margin: 0; padding-left: 1.1rem; }
  .tk-cols li { font-size: 0.9rem; line-height: 1.55; color: var(--tk-muted); margin-bottom: 0.4rem; }
  @media (max-width: 700px) {
    .tk-cols { grid-template-columns: 1fr; }
    .tk-head h1 { font-size: 1.6rem; }
    .tk-result { margin-left: 0; width: 100%; }
  }

  .tk-eq {
    background: var(--tk-bg-alt); border: 1px solid var(--tk-line); border-radius: 6px;
    padding: 1rem 1.2rem; margin: 1rem 0; font-size: 0.9rem; line-height: 1.7; color: var(--tk-muted);
  }
  .tk-eq strong { color: var(--tk-ink); font-family: var(--tk-serif); }
  .tk-subhead { font-family: var(--tk-serif); font-size: 1.1rem; font-weight: 600; color: var(--tk-ink); margin: 1.8rem 0 0.5rem; }
  .tk-subhead:first-of-type { margin-top: 0.5rem; }

  /* Calculateur CO₂ → Forçage → Température */
  .tk-calc {
    background: var(--tk-bg-alt); border: 1px solid var(--tk-line);
    border-radius: 6px; padding: 1.4rem; margin: 1.2rem 0;
  }
  .tk-calc-control { display: flex; align-items: center; gap: 1rem; flex-wrap: wrap; margin-bottom: 1.5rem; }
  .tk-calc-baseline {
    font-size: 0.85rem; color: var(--tk-muted); margin-bottom: 1rem;
    padding-bottom: 0.8rem; border-bottom: 1px dashed var(--tk-line);
  }
  .tk-calc-baseline strong { font-family: var(--tk-serif); color: var(--tk-ink); }
  .tk-calc-control label { font-size: 0.9rem; font-weight: 600; color: var(--tk-ink); white-space: nowrap; }
  .tk-calc-control input[type="range"] { flex: 1; min-width: 180px; accent-color: var(--tk-accent); }
  .tk-calc-control output {
    font-family: var(--tk-serif); font-size: 1.1rem; font-weight: 600; color: var(--tk-accent);
    min-width: 90px; text-align: right;
  }
  .tk-calc-chain { display: flex; align-items: stretch; gap: 0.6rem; flex-wrap: wrap; }
  .tk-calc-box {
    flex: 1; min-width: 130px; background: var(--tk-bg); border: 1px solid var(--tk-line);
    border-radius: 6px; padding: 0.9rem 1rem; display: flex; flex-direction: column; gap: 0.2rem;
  }
  .tk-calc-label { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 0.06em; color: var(--tk-muted); font-weight: 600; }
  .tk-calc-value { font-family: var(--tk-serif); font-size: 1.4rem; font-weight: 600; color: var(--tk-ink); }
  .tk-calc-formula { font-size: 0.72rem; color: var(--tk-light); font-style: italic; margin-top: 0.2rem; }
  .tk-calc-arrow { display: flex; align-items: center; color: var(--tk-light); font-size: 1.3rem; }

  /* Grille 3 graphes côte à côte */
  .tk-row-plots { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0.8rem; margin: 1.2rem 0; }
  .tk-row-plots .tk-chart { margin: 0; }
  @media (max-width: 900px) { .tk-row-plots { grid-template-columns: 1fr; } }
  @media (max-width: 700px) {
    .tk-calc-chain { flex-direction: column; }
    .tk-calc-arrow { transform: rotate(90deg); justify-content: center; }
  }
</style>

<div class="tk">

  <div class="tk-head">
    <p class="tk-eyebrow">Terra Klima · Modèle 2</p>
    <h1>Émissions de CO₂ et réchauffement</h1>
    <p class="tk-lead">Comment la concentration de CO₂ détermine-t-elle la température de la planète, et pourquoi la date à laquelle nous cessons d'émettre est-elle décisive ?</p>
  </div>

  <!-- ÉTAPE 1 — Ce que montre (et ne montre pas) ce modèle -->
  <div class="tk-step">
    <span class="tk-step-num">1</span>
    <h2>À propos du modèle</h2>
    <p>Ce simulateur isole <strong>une seule question</strong> : si l'on ne fait varier que le CO₂, comment la température moyenne de la planète y répond-elle ? Il suit de 1900 à 2100 une chaîne en trois maillons — <strong>les émissions déterminent la concentration de CO₂, le CO₂ détermine l'énergie piégée, cette énergie détermine la température</strong>.</p>
    <p>C'est un modèle <strong>volontairement simplifié</strong>, conçu pour faire ressortir des ordres de grandeur et une dynamique, pas pour prédire le climat avec précision. Il <strong>néglige délibérément</strong> : les autres gaz à effet de serre (méthane, protoxyde d'azote…), les interactions avec les nuages, et les nombreuses boucles de rétroaction du système climatique réel (fonte des glaces, circulation océanique profonde, dégazage des sols…). La réponse réelle du climat est donc plus complexe — mais le mécanisme central, lui, est bien là.</p>
  </div>

  <!-- ÉTAPE 2 — Le calculateur (mécanisme statique) -->
  <div class="tk-step">
    <span class="tk-step-num">2</span>
    <h2>Le mécanisme : du CO₂ à la température</h2>
    <p>Avant de regarder l'évolution dans le temps, comprenons le mécanisme à l'instant présent. Le point essentiel : <strong>le forçage radiatif n'est pas créé par le CO₂ en valeur absolue, mais par son augmentation par rapport à une référence</strong> — ici, la concentration préindustrielle de 280 ppm. C'est l'écart à cette référence qui déséquilibre le bilan énergétique de la planète.</p>
    <p>Déplacez le curseur et observez la chaîne : un <strong>écart de CO₂</strong> par rapport à 280 ppm engendre un <strong>forçage radiatif</strong>, qui engendre un <strong>réchauffement</strong>.</p>

    <div class="tk-calc">
      <div class="tk-calc-control">
        <label for="tk-calc-co2">Concentration de CO₂</label>
        <input id="tk-calc-co2" type="range" min="280" max="1000" step="5" value="420" />
        <output id="tk-calc-co2-val">420 ppm</output>
      </div>

      <div class="tk-calc-chain">
        <div class="tk-calc-box">
          <span class="tk-calc-label">Écart de CO₂</span>
          <span class="tk-calc-value" id="tk-calc-co2-box">—</span>
          <span class="tk-calc-formula">par rapport à 280 ppm</span>
        </div>
        <span class="tk-calc-arrow">→</span>
        <div class="tk-calc-box">
          <span class="tk-calc-label">Forçage radiatif</span>
          <span class="tk-calc-value" id="tk-calc-rf-box">—</span>
          <span class="tk-calc-formula">F = 4 · ln(CO₂/280) / ln 2</span>
        </div>
        <span class="tk-calc-arrow">→</span>
        <div class="tk-calc-box">
          <span class="tk-calc-label">Réchauffement à l'équilibre</span>
          <span class="tk-calc-value" id="tk-calc-temp-box">—</span>
          <span class="tk-calc-formula">T = F × 0,75 °C/(W/m²)</span>
        </div>
      </div>
    </div>
    <p class="tk-hint">Ramenez le curseur à 280 ppm : tout retombe à zéro. C'est ce qui montre que le forçage mesure une <em>perturbation</em> par rapport à la référence, et non une propriété absolue du CO₂. La température d'équilibre est celle atteinte une fois tout le système réchauffé — le climat réel y tend avec des décennies de retard.</p>
  </div>

  <!-- ÉTAPE 3 — Le levier + 3 courbes -->
  <div class="tk-step">
    <span class="tk-step-num">3</span>
    <h2>Le levier : la date du zéro émissions nettes</h2>
    <p>Passons maintenant à l'évolution dans le temps. Tant que nous émettons du CO₂, sa concentration augmente. Le <strong>zéro émissions nettes</strong> est le moment où l'on cesse d'ajouter du CO₂ net.</p>
    <p>Choisissez l'année où ce zéro est atteint. Les trois graphiques ci-dessous — un par maillon de la chaîne — se mettent à jour ensemble. La courbe rouge pointillée est le scénario <em>business-as-usual</em> (émissions continues, sans politique climatique) ; la courbe bleue, votre scénario.</p>

    <div class="tk-controls">
      <label for="tk-sel-year">Zéro émissions nettes en :</label>
      <select id="tk-sel-year">
        <option>2020</option><option>2030</option><option selected>2050</option>
        <option>2060</option><option>2070</option><option>2080</option><option>2090</option>
      </select>
      <span class="tk-result">Réchauffement en 2100 : <strong id="tk-temp-final">—</strong></span>
    </div>
    <div class="tk-legend">
      <span><span class="tk-swatch" style="border-top-color: var(--tk-warn); border-top-style: dashed;"></span> Sans action (business-as-usual)</span>
      <span><span class="tk-swatch" style="border-top-color: var(--tk-accent);"></span> Scénario choisi</span>
    </div>

    <div class="tk-row-plots">
      <div class="tk-chart"><div id="tk-plot-co2"></div></div>
      <div class="tk-chart"><div id="tk-plot-rf"></div></div>
      <div class="tk-chart"><div id="tk-plot-temp"></div></div>
    </div>

    <p>Deux phénomènes expliquent ce que vous voyez. D'abord, le <strong>temps de résidence du CO₂</strong> : après le zéro émissions, la courbe de CO₂ ne chute pas, elle forme un <strong>plateau</strong> — l'essentiel du CO₂ déjà émis reste dans l'atmosphère pendant des siècles. Ensuite, l'<strong>inertie océanique</strong> : la température met des décennies à rattraper le forçage, et continue donc de grimper même après l'arrêt des émissions.</p>

    <div class="tk-takeaway">
      <p><strong>Chaque décennie compte.</strong> Parce que le CO₂ persiste et qu'il continue de forcer le climat, le réchauffement se fige au niveau atteint au moment du zéro émissions — il ne « s'efface » pas. Atteindre ce zéro en 2030 plutôt qu'en 2050 ou 2070 ne change pas seulement la vitesse du réchauffement, mais le <strong>niveau définitif</strong> auquel il se stabilise. Testez plusieurs dates et regardez où passe la courbe de température par rapport aux seuils de +1,5 °C et +2 °C de l'Accord de Paris.</p>
    </div>
  </div>

  <!-- ÉTAPE ★ — Détails techniques -->
  <div class="tk-step">
    <span class="tk-step-num">★</span>
    <h2>Pour aller plus loin</h2>

    <h3 class="tk-subhead">Les équations du modèle</h3>
    <p>Le modèle enchaîne trois relations, par pas de 5 ans de 1900 à 2100 :</p>
    <div class="tk-eq">
      <strong>1. Forçage radiatif :</strong> F = 4 × ln(CO₂ / 280) / ln 2 &nbsp;—&nbsp; +4 W/m² pour un doublement du CO₂.<br>
      <strong>2. Température d'équilibre :</strong> T_eq = F × 0,75 &nbsp;—&nbsp; environ +3 °C pour un doublement.<br>
      <strong>3. Inertie thermique :</strong> la température réelle rejoint cet équilibre avec un retard d'environ 20 ans, dû à la lenteur avec laquelle les océans se réchauffent.
    </div>

    <h3 class="tk-subhead">Ce que le modèle simplifie</h3>
    <p>Ce modèle ne retient que le mécanisme central. Plusieurs phénomènes réels en sont absents, et il faut les garder en tête pour interpréter les courbes :</p>
    <p>D'abord, il traite le <strong>CO₂ comme seul gaz à effet de serre</strong> et résume l'effet refroidissant des aérosols à un terme simplifié — le méthane, le protoxyde d'azote et les nuages ne sont pas représentés. Il utilise une <strong>sensibilité climatique moyenne</strong> (3 °C par doublement) et ne modélise pas les <strong>rétroactions complexes</strong> du système réel : fonte des glaces, circulation océanique profonde, dégazage des sols. Enfin, c'est une <strong>moyenne planétaire</strong> sans résolution régionale, et les trajectoires d'émissions sont idéalisées — ce ne sont pas des prévisions.</p>

    <h3 class="tk-subhead">Les puits de carbone</h3>
    <p>Une simplification mérite une mention à part. Dans la réalité, environ la <strong>moitié du CO₂ que nous émettons est captée</strong> par la biosphère (forêts, sols) et surtout par l'<strong>océan</strong>. Ces puits de carbone ralentissent l'accumulation de CO₂ dans l'atmosphère, et donc le réchauffement — c'est un répit considérable. Mais ce service a une contrepartie : en absorbant le CO₂, l'océan s'<strong>acidifie</strong>, ce qui menace les organismes à coquille ou à squelette calcaire (coraux, mollusques, plancton) et, à terme, des chaînes alimentaires entières. Le modèle intègre implicitement ce captage dans le rythme d'accumulation du CO₂, mais n'en montre pas le coût pour les océans.</p>
  </div>

</div>

<script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
<script>
(function(){
  const timeStep=5, eqCO2=280, initCO2=290, CO2_exp=0.0225;
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
    for(let i=0;i<=iyrfc;i++){
      rampCO2.push(bauCO2[i]); rfTotRamp.push(rfTot[i]); TTransRamp.push(TTrans[i]);
    }
    // Après le zéro émissions : le CO₂ NE redescend PAS vite.
    // L'essentiel de l'excès persiste des siècles. On modélise une décroissance
    // très lente (temps caractéristique ~150 ans) vers un plancher où 70 % de
    // l'excès au moment du zéro émissions reste dans l'atmosphère.
    const TAU_RESORPTION = 150, PERSIST_FRAC = 0.7;
    const co2AtCut = bauCO2[iyrfc];
    const persistFloor = eqCO2 + (co2AtCut - eqCO2) * PERSIST_FRAC;
    for(let i=iyrfc+1;i<years.length;i++){
      const prev=rampCO2[i-1];
      const next = prev + (persistFloor - prev) * (timeStep / TAU_RESORPTION);
      rampCO2.push(next);
      const rfCO2i=watts_m2_2x*Math.log(next/eqCO2)/Math.log(2);
      const rfToti=rfCO2i; rfTotRamp.push(rfToti);
      const Teqi=rfToti*climateSensitivityWm2;
      TTransRamp.push(TTransRamp[i-1]+(Teqi-TTransRamp[i-1])*(timeStep/TResponseTime));
    }
    return {rampCO2, rfTotRamp, TTransRamp};
  }

  const YEARS_CUT=[2020,2030,2050,2060,2070,2080,2090], RAMPS={};
  YEARS_CUT.forEach(y=>RAMPS[y]=scenarioRamp(y));

  const ink = '#111111', accent = '#2c7da0', warn = '#c1666b';

  const baseLayout = {
    paper_bgcolor: 'rgba(0,0,0,0)',
    plot_bgcolor: 'rgba(0,0,0,0)',
    font: { family: 'Inter, sans-serif', size: 11, color: '#111' },
    margin: { t: 50, r: 12, b: 40, l: 48 },
    height: 300,
    showlegend: false,
    xaxis: { gridcolor: '#eee', zerolinecolor: '#ddd', range:[1900,2100], tickfont:{size:10}, dtick:50 },
    yaxis: { gridcolor: '#eee', zerolinecolor: '#ddd', tickfont:{size:10} }
  };
  const cfg = { displayModeBar:false, responsive:true };

  function layout(title, yLabel, yRange, shapes, annotations){
    return Object.assign({}, baseLayout, {
      title: { text: title, font: { family:'EB Garamond, serif', size: 13 }, x:0.5, xanchor:'center', y:0.97, yanchor:'top' },
      yaxis: Object.assign({}, baseLayout.yaxis, { title:{ text:yLabel, font:{size:11} }, range: yRange }),
      shapes: shapes || [],
      annotations: annotations || []
    });
  }

  // CO₂
  Plotly.newPlot('tk-plot-co2', [
    { x:years, y:bauCO2, mode:'lines', line:{width:2, dash:'dash', color:warn}, hovertemplate:'%{x} : %{y:.0f} ppm<extra>Sans action</extra>' },
    { x:years, y:RAMPS[2050].rampCO2, mode:'lines', line:{width:2.5, color:accent}, hovertemplate:'%{x} : %{y:.0f} ppm<extra>Scénario choisi</extra>' }
  ], layout('① CO₂ atmosphérique','ppm',[250,1000]), cfg);

  // Forçage radiatif
  Plotly.newPlot('tk-plot-rf', [
    { x:years, y:rfTot, mode:'lines', line:{width:2, dash:'dash', color:warn}, hovertemplate:'%{x} : %{y:.1f} W/m²<extra>Sans action</extra>' },
    { x:years, y:RAMPS[2050].rfTotRamp, mode:'lines', line:{width:2.5, color:accent}, hovertemplate:'%{x} : %{y:.1f} W/m²<extra>Scénario choisi</extra>' }
  ], layout('② Forçage radiatif','W/m²',[0,8]), cfg);

  // Température, avec lignes repère Paris
  const parisShapes = [
    { type:'line', xref:'paper', yref:'y', x0:0, x1:1, y0:1.5, y1:1.5, line:{color:'#888', width:1, dash:'dot'} },
    { type:'line', xref:'paper', yref:'y', x0:0, x1:1, y0:2.0, y1:2.0, line:{color:'#888', width:1, dash:'dot'} }
  ];
  const parisAnnot = [
    { xref:'paper', x:0.04, y:1.5, yanchor:'bottom', xanchor:'left', text:'+1,5 °C', showarrow:false, font:{size:9, color:'#666'} },
    { xref:'paper', x:0.04, y:2.0, yanchor:'bottom', xanchor:'left', text:'+2 °C', showarrow:false, font:{size:9, color:'#666'} }
  ];
  Plotly.newPlot('tk-plot-temp', [
    { x:years, y:TTrans, mode:'lines', line:{width:2, dash:'dash', color:warn}, hovertemplate:'%{x} : +%{y:.2f} °C<extra>Sans action</extra>' },
    { x:years, y:RAMPS[2050].TTransRamp, mode:'lines', line:{width:2.5, color:accent}, hovertemplate:'%{x} : +%{y:.2f} °C<extra>Scénario choisi</extra>' }
  ], layout('③ Réchauffement','°C',[0,4.2], parisShapes, parisAnnot), cfg);

  // Affichage température finale
  const tempFinalEl = document.getElementById('tk-temp-final');
  function updateResult(R){
    const tf = R.TTransRamp[R.TTransRamp.length-1];
    tempFinalEl.textContent = '+' + tf.toFixed(1).replace('.', ',') + ' °C';
    tempFinalEl.style.color = tf <= 1.5 ? '#3a7a52' : (tf <= 2.0 ? '#c98a1f' : '#c1666b');
  }
  updateResult(RAMPS[2050]);

  document.getElementById('tk-sel-year').addEventListener('change', e=>{
    const y=parseInt(e.target.value,10), R=RAMPS[y];
    Plotly.restyle('tk-plot-co2', {y:[R.rampCO2]}, [1]);
    Plotly.restyle('tk-plot-rf', {y:[R.rfTotRamp]}, [1]);
    Plotly.restyle('tk-plot-temp', {y:[R.TTransRamp]}, [1]);
    updateResult(R);
  });

  // CALCULATEUR statique : écart de CO₂ → Forçage → Température
  (function(){
    const slider = document.getElementById('tk-calc-co2');
    const valOut = document.getElementById('tk-calc-co2-val');
    const co2Box = document.getElementById('tk-calc-co2-box');
    const rfBox  = document.getElementById('tk-calc-rf-box');
    const tBox   = document.getElementById('tk-calc-temp-box');
    function compute(){
      const co2 = parseFloat(slider.value);
      const ecart = co2 - eqCO2;
      const F = watts_m2_2x * Math.log(co2/eqCO2) / Math.log(2);
      const T = F * climateSensitivityWm2;
      valOut.textContent = co2 + ' ppm';
      co2Box.textContent = (ecart === 0 ? '0' : '+' + ecart) + ' ppm';
      rfBox.textContent  = (F < 0.05 ? '0' : '+' + F.toFixed(1).replace('.', ',')) + ' W/m²';
      tBox.textContent   = (T < 0.05 ? '0' : '+' + T.toFixed(1).replace('.', ',')) + ' °C';
      tBox.style.color = T < 0.05 ? '#666' : (T <= 1.5 ? '#3a7a52' : (T <= 2.0 ? '#c98a1f' : '#c1666b'));
    }
    slider.addEventListener('input', compute);
    compute();
  })();

  window.addEventListener('resize', ()=>['tk-plot-co2','tk-plot-rf','tk-plot-temp'].forEach(id=>{
    const el=document.getElementById(id); if(el) Plotly.Plots.resize(el);
  }));
})();
</script>
