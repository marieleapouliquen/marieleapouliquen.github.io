---
layout: default
permalink: /terra-klima/planetes-boucle-dor/
title: ""
description: "Modèle interactif d'équilibre radiatif planétaire — Terra Klima"
---

<p style="margin-bottom: 1.5rem;"><a href="{{ '/terra-klima/' | relative_url }}">← Retour à Terra Klima</a></p>

<!-- ============ TERRA KLIMA · MODÈLE 1 · PLANÈTES BOUCLE D'OR ============ -->
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
  }

  .terra-klima-wrap * { box-sizing: border-box; }

  .terra-klima-wrap .tk-hero {
    background:
      radial-gradient(800px 400px at -10% -20%, rgba(255,215,64,.85) 0%, rgba(255,215,64,0) 60%),
      linear-gradient(105deg, #ffb703 0%, #fd7e14 22%, #7b2cbf 60%, #0a2540 100%);
    border: 0;
    border-radius: 20px;
    padding: clamp(22px, 3vw, 36px);
    margin-bottom: var(--tk-gap);
  }
  .terra-klima-wrap .tk-hero h1 {
    margin: 0 0 6px;
    font-size: clamp(28px, 4vw, 32px);
    line-height: 1.15;
    color: #fff;
    font-family: inherit;
  }
  .terra-klima-wrap .tk-hero p {
    margin: 0;
    font-size: clamp(15px, 2.1vw, 17px);
    color: #fff;
    text-shadow: 0 2px 4px rgba(0,0,0,.4);
  }
  .terra-klima-wrap .tk-cta { display: flex; gap: 12px; flex-wrap: wrap; margin-top: 14px; }
  .terra-klima-wrap .tk-btn {
    display: inline-block;
    padding: 10px 14px;
    border-radius: 12px;
    text-decoration: none;
    font-weight: 700;
    border: 1px solid var(--tk-line);
  }
  .terra-klima-wrap .tk-btn.primary { background: #2D2868; color: #fff; border-color: transparent; }
  .terra-klima-wrap .tk-btn.ghost { color: #2D2868; background: #F6F0FE; border-color: transparent; }

  .terra-klima-wrap section { margin: clamp(28px, 4vw, 48px) 0; }
  .terra-klima-wrap .tk-module {
    background: var(--tk-card);
    border: 1px solid var(--tk-line);
    border-radius: 16px;
    padding: clamp(14px, 2vw, 20px);
  }
  .terra-klima-wrap .tk-module h2 { margin: 0 0 6px; font-family: inherit; }
  .terra-klima-wrap .tk-caption { font-size: 14px; color: var(--tk-muted); margin: 6px 0 12px; }

  .terra-klima-wrap .tk-cols {
    display: grid;
    gap: var(--tk-gap);
    grid-template-columns: 2fr 1fr;
  }
  @media (max-width: 1000px) {
    .terra-klima-wrap .tk-cols { grid-template-columns: 1fr; }
  }
  .terra-klima-wrap .tk-card {
    background: var(--tk-card);
    border: 1px solid var(--tk-line);
    border-radius: 14px;
    padding: 18px;
  }
  .terra-klima-wrap .tk-card h3 { margin: 0 0 8px; font-family: inherit; }
  .terra-klima-wrap .tk-muted { color: var(--tk-muted); }
  .terra-klima-wrap .tk-sep { height: 1px; background: var(--tk-line); margin: 18px 0; }
  .terra-klima-wrap .tk-list { list-style: disc; padding-left: 20px; margin: 8px 0 0; }
  .terra-klima-wrap .tk-note { font-style: italic; margin-top: 6px; color: var(--tk-muted); }

  /* Jeu : onglets et contrôles */
  .terra-klima-wrap .tk-game { max-width: 1100px; margin: 0 auto; }
  .terra-klima-wrap .tk-tabs { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 12px; }
  .terra-klima-wrap .tk-tabbtn {
    cursor: pointer;
    border: 1px solid var(--tk-line);
    padding: 8px 12px;
    border-radius: 10px;
    background: #f7f7f7;
    font-family: inherit;
  }
  .terra-klima-wrap .tk-tabbtn.active { background: #111; color: #fff; border-color: #111; }
  .terra-klima-wrap .tk-panel { display: none; }
  .terra-klima-wrap .tk-panel.active { display: block; }
  .terra-klima-wrap .tk-controls {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    align-items: center;
    margin-bottom: 10px;
  }
  .terra-klima-wrap .tk-controls .tk-row {
    display: grid;
    grid-template-columns: 180px 1fr 120px;
    align-items: center;
    gap: 10px;
  }
  .terra-klima-wrap .tk-controls .tk-row input[type="number"] {
    width: 100%;
    padding: 8px 10px;
    border: 1px solid #cbd5e1;
    border-radius: 10px;
  }
  .terra-klima-wrap .tk-controls .tk-row input[type="range"] { width: 100%; }
  .terra-klima-wrap .tk-controls .tk-row label { font-weight: 600; }
  .terra-klima-wrap .tk-bar { height: 1px; background: #e6e6e6; margin: 12px 0; }
  .terra-klima-wrap .tk-right { text-align: right; }
  .terra-klima-wrap .tk-btn.small { padding: 6px 10px; border-radius: 10px; }
  .terra-klima-wrap select#tk-sel-planet {
    padding: 8px 12px;
    font-size: 16px;
    min-width: 300px;
    border: 1px solid #cbd5e1;
    border-radius: 10px;
    font-weight: 600;
  }
  @media (max-width: 760px) {
    .terra-klima-wrap .tk-controls { grid-template-columns: 1fr; }
  }
</style>

<div class="terra-klima-wrap">

  <div class="tk-hero">
    <h1>🌎🟠 Les Planètes Boucle d'Or</h1>
    <p>Pourquoi certaines planètes sont-elles glacées, d'autres brûlantes tandis que la Terre est juste à la bonne température pour permettre la coexistence des trois états de l'eau&nbsp;? Ce mini-jeu vous invite à explorer la relation entre l'énergie reçue du Soleil et la température de surface des planètes.</p>
    <div class="tk-cta">
      <a href="#tk-jeu" class="tk-btn primary">Lancer le jeu</a>
      <a href="#tk-explications" class="tk-btn ghost">Lire les explications</a>
    </div>
  </div>

  <section id="tk-jeu">
    <div class="tk-module">
      <h2>Simulateur interactif</h2>
      <p class="tk-caption">Ce mini-jeu explore comment la <strong>distance au Soleil</strong> et l'<strong>albédo</strong> (part de lumière réfléchie) influencent la température d'une planète. En ajustant ces paramètres, vous calculez la <strong>température d'équilibre radiatif</strong> — celle d'une planète « nue », sans atmosphère ni effet de serre.</p>
      <p class="tk-caption">Le modèle reste volontairement simple : il n'englobe pas toute la complexité des climats planétaires, mais il met en lumière un mécanisme fondamental — l'équilibre entre l'énergie reçue du Soleil et l'énergie réémise vers l'espace. Comparez ensuite les valeurs calculées aux <strong>températures observées</strong> pour comprendre pourquoi certaines planètes (comme <em>Vénus</em> ou <em>la Terre</em>) sont plus chaudes qu'un corps noir idéal.</p>
      <p class="tk-caption">💡 Indice : plus l'albédo est élevé, plus la planète renvoie la lumière — et plus elle reste froide.</p>

      <div class="tk-game">
        <div class="tk-tabs">
          <button class="tk-tabbtn active" data-target="#tk-p-obs">Température réelle de surface</button>
          <button class="tk-tabbtn" data-target="#tk-p-energy">Énergie solaire reçue</button>
          <button class="tk-tabbtn" data-target="#tk-p-model">Équilibre interactif</button>
          <button class="tk-tabbtn" data-target="#tk-p-compare">Réel vs modélisé</button>
        </div>

        <div class="tk-panel active" id="tk-p-obs"><div id="tk-chart-obs"></div></div>
        <div class="tk-panel" id="tk-p-energy"><div id="tk-chart-energy"></div></div>

        <div class="tk-panel" id="tk-p-model">
          <div class="tk-controls">
            <div class="tk-row" style="grid-column: 1 / -1;">
              <label for="tk-sel-planet">Planète</label>
              <select id="tk-sel-planet">
                <option>Mercure</option><option>Vénus</option><option>Terre</option><option>Mars</option>
                <option>Jupiter</option><option>Saturne</option><option>Uranus</option><option>Neptune</option>
              </select>
              <div class="tk-right">
                <button id="tk-btn-reset" class="tk-btn small">↺ Réinitialiser</button>
              </div>
            </div>
            <div class="tk-row">
              <label for="tk-range-albedo">Albédo (0–0,9)</label>
              <input id="tk-range-albedo" type="range" min="0" max="0.9" step="0.01" />
              <input id="tk-num-albedo" type="number" min="0" max="0.9" step="0.01" />
            </div>
            <div class="tk-row">
              <label for="tk-range-L">Irradiance L (W/m²)</label>
              <input id="tk-range-L" type="range" min="0.5" max="20000" step="0.1" />
              <input id="tk-num-L" type="number" min="0.5" max="20000" step="0.1" />
            </div>
          </div>

          <div id="tk-chart-model"></div>
          <div class="tk-bar"></div>
          <div class="tk-note">Évolution temporelle (relaxation vers l'équilibre) — synchronisée avec la planète et les paramètres ci-dessus.</div>
          <div style="display:flex;gap:16px;flex-wrap:wrap;margin:8px 0 12px;">
            <label><input type="checkbox" id="tk-chk-v" checked> Vénus</label>
            <label><input type="checkbox" id="tk-chk-e" checked> Terre</label>
            <label><input type="checkbox" id="tk-chk-m" checked> Mars</label>
          </div>
          <div id="tk-chart-time-embed"></div>
        </div>

        <div class="tk-panel" id="tk-p-compare">
          <div id="tk-chart-compare"></div>
          <div class="tk-note">◉ Ronds pleins : T_observée &nbsp;&nbsp; ○ Ronds clairs : T_calculée (modèle)</div>
        </div>
      </div>
    </div>
  </section>

  <section id="tk-explications">
    <div class="tk-cols">
      <div class="tk-card">
        <h3>Le modèle de l'équilibre radiatif</h3>
        <p class="tk-muted">Pour illustrer la relation entre l'énergie solaire reçue par une planète et sa température de surface, nous avons construit un modèle de <strong>température d'équilibre radiatif</strong>, fondé sur l'hypothèse du <em>corps noir</em> : chaque planète est supposée absorber et ré-émettre l'énergie solaire sans atmosphère ni transfert interne de chaleur. Ce modèle calcule la température d'une planète « nue », déterminée par l'énergie reçue et son <strong>albédo</strong> (fraction de lumière réfléchie).</p>
        <div class="tk-sep"></div>
        <h3>Visualisation</h3>
        <ul class="tk-list">
          <li><strong>(1) Température réelle de surface</strong> : température moyenne de surface observée pour chaque planète.</li>
          <li><strong>(2) Énergie solaire reçue</strong> : puissance du rayonnement en fonction de la distance au Soleil.</li>
          <li><strong>(3) Équilibre interactif</strong> : jouez sur l'albédo et l'irradiance pour ajuster la température d'équilibre.</li>
          <li><strong>(4) Réel vs modélisé</strong> : comparez la température calculée par le modèle avec la température réelle.</li>
        </ul>
        <div class="tk-sep"></div>
        <h3>Pourquoi la température d'équilibre est-elle plus basse que la température réelle&nbsp;?</h3>
        <p class="tk-muted">Lorsque la température observée dépasse la température d'équilibre radiatif, cela signifie que la planète conserve ou génère davantage de chaleur qu'un simple <em>corps noir</em>. Chez les <strong>planètes telluriques</strong> (comme la Terre ou Vénus), cette différence provient principalement des <strong>gaz à effet de serre</strong>. Pour les <strong>planètes géantes</strong> (Jupiter, Saturne, Neptune), c'est surtout la <strong>chaleur interne</strong> — résidu de leur formation et compression gravitationnelle — qui explique leur température plus élevée.</p>
      </div>

      <aside class="tk-card">
        <h3>À expérimenter</h3>
        <ul class="tk-list">
          <li>Faites varier la <strong>distance au Soleil</strong> (irradiance L) et observez comment la température réagit.</li>
          <li>Augmentez l'<strong>albédo</strong> pour voir comment la planète se refroidit en réfléchissant davantage de lumière.</li>
          <li>Comparez l'écart entre la <strong>température réelle</strong> et la <strong>température modélisée</strong> pour Vénus (fort effet de serre) et Mars (atmosphère très fine).</li>
        </ul>
      </aside>
    </div>
  </section>

</div>

<script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
<script>
(function(){
  const name   = ['Mercure','Vénus','Terre','Mars','Jupiter','Saturne','Uranus','Neptune'];
  const d      = [57.9,108.2,149.2,287.9,778.5,1434,2871,4495];
  const L0     = [12300,3140,1360,600,50,10,3.5,1.5];
  const albedo0= [0.06,0.7,0.3,0.15,0.42,0.45,0.53,0.66];
  const temp_true = [179,462,15,-63,-163,-189,-220,-218];
  const color  = ['gold','fuchsia','lightblue','red','peru','burlywood','turquoise','mediumpurple'];

  let L = [...L0];
  let albedo = [...albedo0];
  const sigma = 5.67e-8;

  function nakedplanet(alpha, L){ return Math.pow(L*(1-alpha)/(4*sigma), 0.25) - 273.15; }
  function computeTempModel(){ return albedo.map((a,i)=>nakedplanet(a, L[i])); }

  function integrateTemps(alpha, Lin){
    const dt_year = 1, depth = 4000, Cp = depth * 4.2e6, steps = 2000;
    const heatIn = Lin * (1 - alpha) / 4;
    let T = 0, HC = Cp * T;
    const time = new Array(steps), tempC = new Array(steps);
    for (let i=0;i<steps;i++){
      const heatOut = sigma * Math.pow(T,4);
      HC += (heatIn - heatOut) * dt_year * 3.14e7;
      T = HC / Cp;
      time[i] = i * dt_year;
      tempC[i] = T - 273.15;
    }
    return {time, tempC};
  }

  Plotly.newPlot('tk-chart-obs', [{
    x: d, y: temp_true, text: name, mode: 'markers+text', textposition: 'top center',
    marker: { size: 10, color }, type: 'scatter',
    hovertemplate: '<b>%{text}</b><br>Distance: %{x:.1f} Mkm<br>T° observée: %{y:.0f} °C<extra></extra>'
  }], {
    title: 'Températures de surface (observées)',
    xaxis: { title: 'Distance au Soleil (millions de km)', range:[0,5000] },
    yaxis:{ title:'Température [°C]' }, margin:{ t:50, r:20, b:60, l:60 }
  }, {responsive:true, displayModeBar:false});

  Plotly.newPlot('tk-chart-energy', [{
    x: d, y: L, text: name, mode: 'markers+text', textposition: 'top center',
    marker: { size: 10, color }, type: 'scatter',
    hovertemplate: '<b>%{text}</b><br>Distance: %{x:.1f} Mkm<br>Énergie: %{y:.0f} W/m²<extra></extra>'
  }], {
    title: 'Énergie solaire reçue',
    xaxis: { title: 'Distance au Soleil (millions de km)', range:[0,5000] },
    yaxis:{ title:'Énergie [W/m²]' }, margin:{ t:50, r:20, b:60, l:60 }
  }, {responsive:true, displayModeBar:false});

  let temp_model = computeTempModel();
  Plotly.newPlot('tk-chart-model', [{
    x: d, y: temp_model, text: name, mode: 'markers+text', textposition: 'top center',
    marker: { size: 10, color }, type: 'scatter',
    hovertemplate: '<b>%{text}</b><br>Distance: %{x:.1f} Mkm<br>T° calculée: %{y:.0f} °C<extra></extra>'
  }], {
    title: 'Températures d\'équilibre radiatif',
    xaxis: { title: 'Distance au Soleil (millions de km)', range:[0,5000] },
    yaxis:{ title:'Température [°C]' }, margin:{ t:50, r:20, b:60, l:60 }
  }, {responsive:true, displayModeBar:false});

  const traceReal = { name:'Observée', x:d, y:temp_true, text:name, mode:'markers+text', textposition:'top center', marker:{ size:10, color }, type:'scatter' };
  const traceModel = { name:'Calculée', x:d, y:temp_model, text:name, mode:'markers', marker:{ size:12, color, line:{color, width:2}, symbol:'circle-open' }, type:'scatter' };
  Plotly.newPlot('tk-chart-compare', [traceReal, traceModel], {
    title:'Réel vs Modèle',
    xaxis:{ title:'Distance au Soleil (millions de km)', range:[0,5000] },
    yaxis:{ title:'Température [°C]' },
    margin:{ t:50, r:20, b:60, l:60 }, legend:{ orientation:'h', x:0, y:1.12 }
  }, {responsive:true, displayModeBar:false});

  const sel = document.getElementById('tk-sel-planet');
  const rA = document.getElementById('tk-range-albedo');
  const nA = document.getElementById('tk-num-albedo');
  const rL = document.getElementById('tk-range-L');
  const nL = document.getElementById('tk-num-L');
  const btnReset = document.getElementById('tk-btn-reset');

  function syncInputs(){
    const i = sel.selectedIndex;
    rA.value = albedo[i]; nA.value = albedo[i];
    rL.value = L[i]; nL.value = L[i];
    const S = integrateTemps(albedo[i], L[i]);
    Plotly.restyle('tk-chart-time-embed', { x:[S.time], y:[S.tempC], line:[{color: color[i], width:3}] }, [3]);
  }
  function applyChange(){
    const i = sel.selectedIndex;
    albedo[i] = Math.max(0, Math.min(0.9, parseFloat(nA.value)));
    L[i] = Math.max(0.5, Math.min(20000, parseFloat(nL.value)));
    temp_model = computeTempModel();
    Plotly.restyle('tk-chart-energy', { y:[L] });
    Plotly.restyle('tk-chart-model', { y:[temp_model] });
    Plotly.restyle('tk-chart-compare', { y:[temp_true, temp_model] });
    const S = integrateTemps(albedo[i], L[i]);
    Plotly.restyle('tk-chart-time-embed', { x:[S.time], y:[S.tempC], line:[{color: color[i], width:3}] }, [3]);
  }
  rA.addEventListener('input', ()=>{ nA.value = rA.value; applyChange(); });
  nA.addEventListener('input', ()=>{ rA.value = nA.value; applyChange(); });
  rL.addEventListener('input', ()=>{ nL.value = rL.value; applyChange(); });
  nL.addEventListener('input', ()=>{ rL.value = nL.value; applyChange(); });
  sel.addEventListener('change', syncInputs);
  btnReset.addEventListener('click', ()=>{
    const i = sel.selectedIndex;
    albedo[i] = albedo0[i]; L[i] = L0[i];
    syncInputs(); applyChange();
  });

  const Sel0 = integrateTemps(albedo[0], L[0]);
  const Merc0 = integrateTemps(albedo0[0], L0[0]);
  const Venus0 = integrateTemps(albedo0[1], L0[1]);
  const Earth0 = integrateTemps(albedo0[2], L0[2]);
  const Mars0 = integrateTemps(albedo0[3], L0[3]);
  const Jup0 = integrateTemps(albedo0[4], L0[4]);
  const Sat0 = integrateTemps(albedo0[5], L0[5]);
  const Ura0 = integrateTemps(albedo0[6], L0[6]);
  const Nep0 = integrateTemps(albedo0[7], L0[7]);

  Plotly.newPlot('tk-chart-time-embed', [
    { name:'Vénus', x:Venus0.time, y:Venus0.tempC, mode:'lines', line:{width:2, color: color[1]} },
    { name:'Terre', x:Earth0.time, y:Earth0.tempC, mode:'lines', line:{width:2, color: color[2]} },
    { name:'Mars', x:Mars0.time, y:Mars0.tempC, mode:'lines', line:{width:2, color: color[3]} },
    { name:'Planète sélectionnée', x:Sel0.time, y:Sel0.tempC, mode:'lines', line:{width:3, color: color[0]} },
    { name:'Mercure', x:Merc0.time, y:Merc0.tempC, mode:'lines', line:{width:2, color: color[0]} },
    { name:'Jupiter', x:Jup0.time, y:Jup0.tempC, mode:'lines', line:{width:2, color: color[4]} },
    { name:'Saturne', x:Sat0.time, y:Sat0.tempC, mode:'lines', line:{width:2, color: color[5]} },
    { name:'Uranus', x:Ura0.time, y:Ura0.tempC, mode:'lines', line:{width:2, color: color[6]} },
    { name:'Neptune', x:Nep0.time, y:Nep0.tempC, mode:'lines', line:{width:2, color: color[7]} }
  ], {
    title:"Convergence vers T_rad",
    xaxis:{ title:'Temps [années]' }, yaxis:{ title:'Température [°C]' },
    margin:{ t:50, r:20, b:60, l:60 }, legend:{orientation:'v'}
  }, {responsive:true, displayModeBar:false});

  syncInputs();

  const chkV = document.getElementById('tk-chk-v');
  const chkE = document.getElementById('tk-chk-e');
  const chkM = document.getElementById('tk-chk-m');
  function updateRefVisibility(){
    Plotly.restyle('tk-chart-time-embed', { visible: [chkV.checked ? true : 'legendonly'] }, [0]);
    Plotly.restyle('tk-chart-time-embed', { visible: [chkE.checked ? true : 'legendonly'] }, [1]);
    Plotly.restyle('tk-chart-time-embed', { visible: [chkM.checked ? true : 'legendonly'] }, [2]);
  }
  [chkV, chkE, chkM].forEach(el => el.addEventListener('change', updateRefVisibility));
  updateRefVisibility();

  document.querySelectorAll('.terra-klima-wrap .tk-tabbtn').forEach(btn => btn.addEventListener('click', () => {
    document.querySelectorAll('.terra-klima-wrap .tk-tabbtn').forEach(b=>b.classList.remove('active'));
    document.querySelectorAll('.terra-klima-wrap .tk-panel').forEach(p=>p.classList.remove('active'));
    btn.classList.add('active');
    document.querySelector(btn.dataset.target).classList.add('active');
    setTimeout(()=>{
      ['tk-chart-obs','tk-chart-energy','tk-chart-model','tk-chart-compare','tk-chart-time-embed']
        .forEach(id=>{ const el=document.getElementById(id); if(el){ Plotly.Plots.resize(el); }});
    }, 0);
  }));
})();
</script>
