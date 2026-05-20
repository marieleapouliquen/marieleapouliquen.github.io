---
layout: default
permalink: /terra-klima/planetes-boucle-dor/
title: ""
description: "Modèle interactif d'équilibre radiatif planétaire — Terra Klima"
---

<p style="margin-bottom: 1.5rem;"><a href="{{ '/enseignement/' | relative_url }}">← Retour à la page Enseignement</a></p>

<!-- ============ TERRA KLIMA · MODÈLE 1 · PLANÈTES BOUCLE D'OR ============ -->
<style>
  .tk {
    --tk-ink: #111111;
    --tk-muted: #666666;
    --tk-light: #999999;
    --tk-bg: #ffffff;
    --tk-bg-alt: #fafafa;
    --tk-line: #e5e5e5;
    --tk-accent: #2c7da0;
    --tk-serif: 'EB Garamond', Georgia, serif;
    --tk-sans: 'Inter', -apple-system, sans-serif;

    max-width: 820px;
    margin: 0 auto;
    color: var(--tk-ink);
    font-family: var(--tk-sans);
  }
  .tk * { box-sizing: border-box; }

  /* En-tête sobre */
  .tk-head { margin-bottom: 2.5rem; }
  .tk-eyebrow {
    font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.1em;
    color: var(--tk-muted); font-weight: 600; margin: 0 0 0.5rem;
  }
  .tk-head h1 {
    font-family: var(--tk-serif); font-size: 2rem; font-weight: 600;
    line-height: 1.2; margin: 0 0 0.8rem; color: var(--tk-ink);
  }
  .tk-head .tk-lead {
    font-size: 1.05rem; line-height: 1.6; color: var(--tk-muted); margin: 0;
  }

  /* Étapes numérotées */
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

  /* Graphique */
  .tk-chart { margin: 1.2rem 0; border: 1px solid var(--tk-line); border-radius: 6px; padding: 0.5rem; background: var(--tk-bg); }

  /* Contrôles */
  .tk-controls {
    background: var(--tk-bg-alt); border: 1px solid var(--tk-line);
    border-radius: 6px; padding: 1.2rem 1.4rem; margin: 1.2rem 0;
  }
  .tk-control-row { display: grid; grid-template-columns: 200px 1fr 90px; align-items: center; gap: 1rem; margin-bottom: 1rem; }
  .tk-control-row:last-child { margin-bottom: 0; }
  .tk-control-row label { font-size: 0.9rem; font-weight: 500; color: var(--tk-ink); }
  .tk-control-row input[type="range"] { width: 100%; accent-color: var(--tk-accent); }
  .tk-control-row input[type="number"] {
    width: 100%; padding: 0.4rem 0.6rem; border: 1px solid var(--tk-line);
    border-radius: 4px; font-family: var(--tk-sans); font-size: 0.9rem;
  }
  .tk-control-head { display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem; }
  .tk-control-head .tk-planet-pick { display: flex; align-items: center; gap: 0.6rem; }
  .tk-control-head label { font-size: 0.9rem; font-weight: 600; }
  .tk-control-head select {
    padding: 0.4rem 0.7rem; border: 1px solid var(--tk-line); border-radius: 4px;
    font-family: var(--tk-sans); font-size: 0.9rem; font-weight: 500; background: #fff;
  }
  .tk-reset {
    background: none; border: 1px solid var(--tk-line); border-radius: 4px;
    padding: 0.4rem 0.8rem; font-family: var(--tk-sans); font-size: 0.82rem;
    color: var(--tk-muted); cursor: pointer; transition: all 0.15s ease;
  }
  .tk-reset:hover { border-color: var(--tk-ink); color: var(--tk-ink); }

  /* Encadré "à retenir" */
  .tk-takeaway {
    background: var(--tk-bg-alt); border-left: 3px solid var(--tk-accent);
    border-radius: 0 4px 4px 0; padding: 1.1rem 1.3rem; margin: 1.2rem 0;
  }
  .tk-takeaway p { margin: 0; font-size: 0.95rem; line-height: 1.6; color: var(--tk-ink); }
  .tk-takeaway p strong { font-family: var(--tk-serif); }

  .tk-hint { font-size: 0.88rem; font-style: italic; color: var(--tk-light); margin-top: 0.5rem; }
  .tk-energy-readout { font-size: 0.9rem; color: var(--tk-ink); margin: 0.4rem 0 0; }
  .tk-energy-readout strong { font-family: var(--tk-serif); font-size: 1.05rem; color: var(--tk-accent); }
  .tk-energy-note { color: var(--tk-light); font-style: italic; font-size: 0.82rem; }

  /* Légende cases à cocher */
  .tk-checks { display: flex; gap: 1.2rem; flex-wrap: wrap; margin: 0.8rem 0; }
  .tk-checks label { font-size: 0.85rem; color: var(--tk-muted); display: flex; align-items: center; gap: 0.3rem; cursor: pointer; }

  @media (max-width: 700px) {
    .tk-control-row { grid-template-columns: 1fr; gap: 0.4rem; }
    .tk-head h1 { font-size: 1.6rem; }
  }
</style>

<div class="tk">

  <div class="tk-head">
    <p class="tk-eyebrow">Terra Klima · Modèle 1</p>
    <h1>Les planètes Boucle d'Or</h1>
    <p class="tk-lead">Pourquoi la Terre est-elle « juste à la bonne température », quand Vénus brûle et que Mars gèle ? Explorons l'équilibre entre l'énergie reçue du Soleil et la chaleur qu'une planète renvoie vers l'espace.</p>
  </div>

  <!-- ÉTAPE 1 — La question -->
  <div class="tk-step">
    <span class="tk-step-num">1</span>
    <h2>La question de départ</h2>
    <p>Chaque planète reçoit une certaine quantité d'énergie du Soleil, d'autant plus faible qu'elle en est éloignée. On pourrait croire que cette distance suffit à prédire sa température. Mais ce n'est pas si simple : <strong>une partie de l'énergie est immédiatement réfléchie</strong> vers l'espace, sans réchauffer la planète. Cette fraction réfléchie s'appelle l'<strong>albédo</strong>.</p>
    <p>Commençons par observer l'énergie solaire reçue par chaque planète selon sa distance au Soleil.</p>
    <div class="tk-chart"><div id="tk-chart-energy"></div></div>
    <p class="tk-hint">Survolez les points pour voir les valeurs. Mercure reçoit près de 10 000 fois plus d'énergie que Neptune.</p>
  </div>

  <!-- ÉTAPE 2 — Le modèle interactif -->
  <div class="tk-step">
    <span class="tk-step-num">2</span>
    <h2>Calculez la température d'équilibre</h2>
    <p>Imaginons une planète « nue » : sans atmosphère, sans effet de serre. Sa température se stabilise quand <strong>l'énergie qu'elle absorbe égale l'énergie qu'elle réémet</strong>. C'est la <strong>température d'équilibre radiatif</strong>.</p>
    <p>Choisissez une planète, puis faites varier sa <strong>distance au Soleil</strong> et son <strong>albédo</strong>. L'énergie reçue se recalcule automatiquement selon la loi en 1/d² (l'énergie diminue avec le carré de la distance). Observez comment la température calculée se déplace.</p>

    <div class="tk-controls">
      <div class="tk-control-head">
        <div class="tk-planet-pick">
          <label for="tk-sel-planet">Planète :</label>
          <select id="tk-sel-planet">
            <option>Mercure</option><option>Vénus</option><option selected>Terre</option><option>Mars</option>
            <option>Jupiter</option><option>Saturne</option><option>Uranus</option><option>Neptune</option>
          </select>
        </div>
        <button id="tk-btn-reset" class="tk-reset">↺ Réinitialiser</button>
      </div>
      <div class="tk-control-row">
        <label for="tk-range-albedo">Albédo (0 – 0,9)</label>
        <input id="tk-range-albedo" type="range" min="0" max="0.9" step="0.01" />
        <input id="tk-num-albedo" type="number" min="0" max="0.9" step="0.01" />
      </div>
      <div class="tk-control-row">
        <label for="tk-range-dist">Distance au Soleil (Mkm)</label>
        <input id="tk-range-dist" type="range" min="40" max="5000" step="1" />
        <input id="tk-num-dist" type="number" min="40" max="5000" step="1" />
      </div>
      <p class="tk-energy-readout">Énergie reçue (calculée) : <strong id="tk-energy-val">—</strong> W/m² <span class="tk-energy-note">— déduite de la distance par la loi en 1/d²</span></p>
    </div>

    <div class="tk-chart"><div id="tk-chart-model"></div></div>
    <p class="tk-hint">💡 Rapprochez la planète du Soleil : elle reçoit davantage d'énergie et se réchauffe. Augmentez l'albédo : elle renvoie plus de lumière et se refroidit.</p>
  </div>

  <!-- ÉTAPE 3 — La confrontation au réel -->
  <div class="tk-step">
    <span class="tk-step-num">3</span>
    <h2>Comparez au réel</h2>
    <p>Voici le moment intéressant. Superposons la <strong>température calculée</strong> par notre modèle de planète nue avec la <strong>température réellement observée</strong> à la surface de chaque planète.</p>
    <div class="tk-chart"><div id="tk-chart-compare"></div></div>
    <p class="tk-hint">◉ Points pleins : température observée &nbsp;·&nbsp; ○ Points creux : température calculée par le modèle</p>
    <div class="tk-takeaway">
      <p>Pour plusieurs planètes, la température réelle est <strong>bien plus élevée</strong> que celle prédite par le modèle. Notre planète « nue » est donc incomplète : il manque quelque chose.</p>
    </div>
  </div>

  <!-- ÉTAPE 4 — L'explication -->
  <div class="tk-step">
    <span class="tk-step-num">4</span>
    <h2>Que révèle l'écart ?</h2>
    <p>Quand la température observée dépasse la température d'équilibre, c'est que la planète <strong>retient ou produit de la chaleur</strong> au-delà d'un simple corps noir.</p>
    <p>Pour les <strong>planètes telluriques</strong> comme la Terre ou Vénus, cet écart vient surtout des <strong>gaz à effet de serre</strong>, qui piègent une partie du rayonnement réémis. Vénus, avec son atmosphère dense de CO₂, affiche l'écart le plus spectaculaire — c'est l'effet de serre emballé.</p>
    <p>Pour les <strong>planètes géantes</strong> comme Jupiter ou Neptune, c'est plutôt leur <strong>chaleur interne</strong> — héritée de leur formation et de leur compression gravitationnelle — qui les maintient plus chaudes que prévu.</p>
    <div class="tk-takeaway">
      <p><strong>L'idée Boucle d'Or :</strong> la température d'une planète ne dépend pas que de sa distance au Soleil. L'albédo et surtout l'atmosphère décident si une planète est gelée, brûlante, ou « juste comme il faut » pour l'eau liquide — et donc, peut-être, pour la vie.</p>
    </div>
  </div>

  <!-- Référence : températures observées (en bas, comme donnée de fond) -->
  <div class="tk-step">
    <span class="tk-step-num">★</span>
    <h2>Pour mémoire : les températures observées</h2>
    <p>Le graphique de référence des températures de surface réellement mesurées sur chaque planète.</p>
    <div class="tk-chart"><div id="tk-chart-obs"></div></div>
  </div>

</div>

<script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
<script>
(function(){
  const name   = ['Mercure','Vénus','Terre','Mars','Jupiter','Saturne','Uranus','Neptune'];
  const d      = [57.9,108.2,149.2,287.9,778.5,1434,2871,4495];
  const L0     = [12300,3140,1360,600,50,10,3.5,1.5];
  const albedo0= [0.06,0.7,0.3,0.15,0.42,0.45,0.53,0.66];
  const temp_true = [179,462,15,-63,-163,-189,-220,-218];
  // Palette sobre : un seul accent bleu + gris, sauf différenciation nécessaire
  const accent = '#2c7da0';
  const ink = '#111111';
  const color  = ['#999','#c1666b','#2c7da0','#a8581f','#7a7a7a','#9a8c5a','#6a8caf','#4a5a8a'];
  const sigma = 5.67e-8;

  let dist = [...d];          // distance courante (manipulable) par planète
  let albedo = [...albedo0];

  // Loi en 1/d² : l'énergie reçue se déduit de la distance au Soleil.
  // Référence : 1360 W/m² à 149,2 Mkm (orbite terrestre).
  const L_REF = 1360, D_REF = 149.2;
  function energyFromDist(distMkm){ return L_REF * Math.pow(D_REF / distMkm, 2); }

  // Énergie initiale calculée par la loi (cohérente avec le curseur distance)
  let L = d.map(energyFromDist);

  function nakedplanet(alpha, L){ return Math.pow(L*(1-alpha)/(4*sigma), 0.25) - 273.15; }
  function computeTempModel(){ return albedo.map((a,i)=>nakedplanet(a, L[i])); }

  const baseLayout = {
    font: { family: 'Inter, sans-serif', size: 12, color: '#111' },
    paper_bgcolor: 'rgba(0,0,0,0)',
    plot_bgcolor: 'rgba(0,0,0,0)',
    margin: { t: 60, r: 30, b: 60, l: 65 },
    title: { y: 0.97, yanchor: 'top', x: 0.5, xanchor: 'center' },
    xaxis: { gridcolor: '#eee', zerolinecolor: '#ddd' },
    yaxis: { gridcolor: '#eee', zerolinecolor: '#ddd' }
  };
  const cfg = { responsive: true, displayModeBar: false };

  // Positions de labels alternées pour éviter les chevauchements
  const labelPos = ['top center','bottom center','top center','bottom center','top center','bottom center','top center','bottom center'];

  // ÉTAPE 1 — Énergie reçue (échelles log sur les deux axes)
  Plotly.newPlot('tk-chart-energy', [{
    x: d, y: L, text: name, mode: 'markers+text', textposition: labelPos,
    marker: { size: 11, color: accent, line: { color: '#fff', width: 1 } }, type: 'scatter',
    textfont: { family: 'Inter, sans-serif', size: 11, color: '#444' },
    cliponaxis: false,
    hovertemplate: '<b>%{text}</b><br>Distance : %{x:,.0f} Mkm<br>Énergie reçue : %{y:,.1f} W/m²<extra></extra>'
  }], Object.assign({}, baseLayout, {
    title: { text: 'Énergie solaire reçue selon la distance', font: { family: 'EB Garamond, serif', size: 16 } },
    xaxis: Object.assign({}, baseLayout.xaxis, { title: 'Distance au Soleil (millions de km) — échelle log', type: 'log', range:[Math.log10(40), Math.log10(6000)] }),
    yaxis: Object.assign({}, baseLayout.yaxis, { title: 'Énergie [W/m²] — échelle log', type: 'log' })
  }), cfg);

  // ÉTAPE 2 — Modèle interactif
  let temp_model = computeTempModel();
  Plotly.newPlot('tk-chart-model', [{
    x: d, y: temp_model, text: name, mode: 'markers+text', textposition: labelPos,
    marker: { size: 11, color: accent, line: { color: '#fff', width: 1 } }, type: 'scatter',
    textfont: { family: 'Inter, sans-serif', size: 11, color: '#444' },
    cliponaxis: false,
    hovertemplate: '<b>%{text}</b><br>T° calculée : %{y:.0f} °C<extra></extra>'
  }], Object.assign({}, baseLayout, {
    title: { text: "Température d'équilibre radiatif (modèle de planète nue)", font: { family: 'EB Garamond, serif', size: 16 } },
    xaxis: Object.assign({}, baseLayout.xaxis, { title: 'Distance au Soleil (millions de km) — échelle log', type: 'log', range:[Math.log10(40), Math.log10(6000)] }),
    yaxis: Object.assign({}, baseLayout.yaxis, { title: 'Température [°C]' }),
    shapes: [{
      type: 'rect', xref: 'paper', yref: 'y', x0: 0, x1: 1, y0: 0, y1: 100,
      fillcolor: accent, opacity: 0.06, line: { width: 0 }, layer: 'below'
    }],
    annotations: [{
      xref: 'paper', x: 0.99, y: 50, xanchor: 'right', text: 'eau liquide (0–100 °C)',
      showarrow: false, font: { family: 'Inter, sans-serif', size: 10, color: accent }
    }]
  }), cfg);

  // ÉTAPE 3 — Comparaison (échelle log X + annotations effet de serre + barres d'écart)
  // Barres verticales reliant T calculée → T observée pour visualiser l'écart
  const gapShapes = d.map((dist,i)=>({
    type:'line', xref:'x', yref:'y',
    x0: dist, x1: dist, y0: temp_model[i], y1: temp_true[i],
    line:{ color:'#ccc', width:1.5 }, layer:'below'
  }));
  const traceReal = { name:'Observée', x:d, y:temp_true, text:name, mode:'markers', marker:{ size:11, color: ink }, type:'scatter',
    hovertemplate: '<b>%{text}</b><br>T° observée : %{y:.0f} °C<extra></extra>' };
  const traceModel = { name:'Calculée (modèle)', x:d, y:temp_model, text:name, mode:'markers', marker:{ size:13, color: '#fff', line:{color: accent, width:2}, symbol:'circle' }, type:'scatter',
    hovertemplate: '<b>%{text}</b><br>T° calculée : %{y:.0f} °C<extra></extra>' };
  Plotly.newPlot('tk-chart-compare', [traceReal, traceModel], Object.assign({}, baseLayout, {
    title: { text: 'Température observée vs calculée : l\'écart révèle l\'atmosphère', font: { family: 'EB Garamond, serif', size: 16 }, y: 0.97, yanchor: 'top', x: 0.5, xanchor: 'center' },
    margin: { t: 60, r: 30, b: 90, l: 65 },
    xaxis: Object.assign({}, baseLayout.xaxis, { title: 'Distance au Soleil (millions de km) — échelle log', type: 'log', range:[Math.log10(40), Math.log10(6000)] }),
    yaxis: Object.assign({}, baseLayout.yaxis, { title: 'Température [°C]', range:[-280, 540] }),
    legend: { orientation:'h', x:0.5, xanchor:'center', y:-0.22, yanchor:'top', font:{ size:11 } },
    shapes: gapShapes,
    annotations: [
      {
        x: Math.log10(108.2), y: 462, ax: 35, ay: -10, xanchor:'left',
        text: 'Vénus : +481 °C<br>effet de serre emballé',
        showarrow: true, arrowhead: 2, arrowsize: 1, arrowwidth: 1.2, arrowcolor: '#c1666b',
        font: { family: 'Inter, sans-serif', size: 10, color: '#c1666b' },
        bgcolor: 'rgba(255,255,255,0.85)', bordercolor: '#c1666b', borderwidth: 1, borderpad: 4
      },
      {
        x: Math.log10(149.2), y: 15, ax: 60, ay: -75, xanchor:'left',
        text: 'Terre : +34 °C<br>effet de serre vital',
        showarrow: true, arrowhead: 2, arrowsize: 1, arrowwidth: 1.2, arrowcolor: accent,
        font: { family: 'Inter, sans-serif', size: 10, color: accent },
        bgcolor: 'rgba(255,255,255,0.9)', bordercolor: accent, borderwidth: 1, borderpad: 4
      }
    ]
  }), cfg);

  // RÉFÉRENCE — Températures observées
  Plotly.newPlot('tk-chart-obs', [{
    x: d, y: temp_true, text: name, mode: 'markers+text', textposition: labelPos,
    marker: { size: 11, color: ink, line: { color: '#fff', width: 1 } }, type: 'scatter',
    textfont: { family: 'Inter, sans-serif', size: 11, color: '#444' },
    cliponaxis: false,
    hovertemplate: '<b>%{text}</b><br>T° observée : %{y:.0f} °C<extra></extra>'
  }], Object.assign({}, baseLayout, {
    title: { text: 'Températures de surface observées', font: { family: 'EB Garamond, serif', size: 16 } },
    xaxis: Object.assign({}, baseLayout.xaxis, { title: 'Distance au Soleil (millions de km) — échelle log', type: 'log', range:[Math.log10(40), Math.log10(6000)] }),
    yaxis: Object.assign({}, baseLayout.yaxis, { title: 'Température [°C]' })
  }), cfg);

  // Contrôles interactifs
  const sel = document.getElementById('tk-sel-planet');
  const rA = document.getElementById('tk-range-albedo');
  const nA = document.getElementById('tk-num-albedo');
  const rD = document.getElementById('tk-range-dist');
  const nD = document.getElementById('tk-num-dist');
  const energyVal = document.getElementById('tk-energy-val');
  const btnReset = document.getElementById('tk-btn-reset');

  function fmt(n){ return n >= 100 ? Math.round(n).toLocaleString('fr-FR') : n.toFixed(1); }

  function syncInputs(){
    const i = sel.selectedIndex;
    rA.value = albedo[i]; nA.value = albedo[i];
    rD.value = Math.round(dist[i]); nD.value = Math.round(dist[i]);
    energyVal.textContent = fmt(L[i]);
  }
  function refreshCharts(){
    temp_model = computeTempModel();
    // Les points se déplacent aussi en X (distance) → on met à jour x ET y
    Plotly.restyle('tk-chart-energy', { x:[dist], y:[L] });
    Plotly.restyle('tk-chart-model', { x:[dist], y:[temp_model] });
    Plotly.restyle('tk-chart-compare', { x:[dist, dist], y:[temp_true, temp_model] }, [0,1]);
    const newGaps = dist.map((dd,k)=>({
      type:'line', xref:'x', yref:'y',
      x0: dd, x1: dd, y0: temp_model[k], y1: temp_true[k],
      line:{ color:'#ccc', width:1.5 }, layer:'below'
    }));
    Plotly.relayout('tk-chart-compare', { shapes: newGaps });
  }
  function applyChange(){
    const i = sel.selectedIndex;
    albedo[i] = Math.max(0, Math.min(0.9, parseFloat(nA.value)));
    dist[i] = Math.max(40, Math.min(5000, parseFloat(nD.value)));
    L[i] = energyFromDist(dist[i]);   // recalcul automatique par la loi en 1/d²
    energyVal.textContent = fmt(L[i]);
    refreshCharts();
  }
  rA.addEventListener('input', ()=>{ nA.value = rA.value; applyChange(); });
  nA.addEventListener('input', ()=>{ rA.value = nA.value; applyChange(); });
  rD.addEventListener('input', ()=>{ nD.value = rD.value; applyChange(); });
  nD.addEventListener('input', ()=>{ rD.value = nD.value; applyChange(); });
  sel.addEventListener('change', syncInputs);
  btnReset.addEventListener('click', ()=>{
    const i = sel.selectedIndex;
    albedo[i] = albedo0[i]; dist[i] = d[i]; L[i] = energyFromDist(d[i]);
    syncInputs(); refreshCharts();
  });

  syncInputs();
})();
</script>
