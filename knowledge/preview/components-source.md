```html
<!doctype html>
<!-- @dsCard group="Components" name="Components" subtitle="Buttons, badges, inputs, stat cards, icons" -->
<html lang="en">
<head>
<meta charset="utf-8">
<title>Gauss — Components</title>
<link rel="stylesheet" href="../colors_and_type.css">
<style>
  body { margin: 0; padding: 56px; background: var(--bg-paper); }
  .frame { max-width: 1200px; margin: 0 auto; }
  .header { padding-bottom: 32px; border-bottom: 1px solid var(--border-hairline); margin-bottom: 48px; }
  .header h1 { margin: 0 0 8px; font-size: 56px; font-weight: 800; letter-spacing: -0.03em; }
  .header p { margin: 0; max-width: 540px; }
  .row-label { font-family: var(--font-display); font-size: 11px; font-weight: 600; letter-spacing: 0.16em; text-transform: uppercase; color: var(--fg-3); margin: 32px 0 16px; display: flex; align-items: center; gap: 12px; }
  .row-label::after { content: ""; flex: 1; height: 1px; background: var(--border-hairline); }
  .pad { background: white; border: 1px solid var(--border-hairline); border-radius: 12px; padding: 28px; }
  .pad.dark { background: var(--ink-1000); border-color: transparent; }
  .row { display: flex; flex-wrap: wrap; gap: 12px; align-items: center; }

  /* Buttons */
  .btn { display: inline-flex; align-items: center; gap: 8px; font-family: var(--font-display); font-weight: 600; font-size: 15px; padding: 12px 20px; border-radius: 4px; border: 1px solid transparent; cursor: pointer; transition: all .15s ease; text-decoration: none; letter-spacing: -0.005em; }
  .btn-primary { background: var(--gauss-green); color: var(--ink-1000); box-shadow: var(--shadow-sm); }
  .btn-primary:hover { background: var(--gauss-green-700); color: white; }
  .btn-secondary { background: var(--ink-1000); color: white; }
  .btn-secondary:hover { background: var(--ink-900); }
  .btn-outline { background: transparent; color: var(--ink-900); border-color: var(--ink-300); }
  .btn-outline:hover { border-color: var(--ink-900); }
  .btn-ghost { background: transparent; color: var(--ink-900); }
  .btn-ghost:hover { background: var(--ink-100); }
  .btn-lg { font-size: 16px; padding: 16px 28px; }
  .btn .arrow { font-size: 18px; transition: transform .15s; }
  .btn:hover .arrow { transform: translateX(2px); }

  /* Badges */
  .badge { display: inline-flex; align-items: center; gap: 6px; font-family: var(--font-display); font-weight: 600; font-size: 11px; letter-spacing: 0.06em; text-transform: uppercase; padding: 4px 10px; border-radius: 999px; border: 1px solid transparent; }
  .badge-green { background: var(--gauss-green-100); color: var(--gauss-green-900); border-color: var(--gauss-green); }
  .badge-ink { background: var(--ink-100); color: var(--ink-700); }
  .badge-warn { background: #FEF3E1; color: #946100; }
  .badge-grid { background: rgba(43,108,255,0.12); color: #1a4dc7; }
  .badge .dot { width: 6px; height: 6px; border-radius: 999px; background: currentColor; }

  /* Inputs */
  .field { display: flex; flex-direction: column; gap: 6px; }
  .field label { font-family: var(--font-display); font-size: 12px; font-weight: 600; letter-spacing: 0.04em; color: var(--fg-2); }
  .input { font-family: var(--font-body); font-size: 15px; padding: 12px 14px; border-radius: 6px; border: 1px solid var(--ink-300); background: white; transition: all .15s; }
  .input:focus { outline: none; border-color: var(--gauss-green); box-shadow: 0 0 0 3px rgba(57,181,74,0.18); }
  .input::placeholder { color: var(--fg-3); }

  /* Stat card */
  .stat-card { background: white; border: 1px solid var(--border-hairline); border-radius: 12px; padding: 24px; min-width: 220px; box-shadow: var(--shadow-sm); }
  .stat-card .eyebrow { color: var(--fg-3); margin-bottom: 10px; }
  .stat-card .value { font-family: var(--font-display); font-weight: 800; font-size: 40px; line-height: 1; letter-spacing: -0.02em; font-variant-numeric: tabular-nums; }
  .stat-card .value.green { color: var(--gauss-green-700); }
  .stat-card .note { color: var(--fg-3); font-size: 13px; margin-top: 8px; }
  .stat-card.dark { background: var(--ink-1000); border-color: transparent; color: white; }
  .stat-card.dark .value.green { color: var(--gauss-green); }
  .stat-card.dark .note { color: rgba(255,255,255,0.6); }

  /* Spec table */
  .spec-table { width: 100%; border-collapse: collapse; }
  .spec-table th, .spec-table td { padding: 14px 16px; text-align: left; border-bottom: 1px solid var(--border-hairline); font-size: 14px; }
  .spec-table th { font-family: var(--font-display); font-size: 11px; font-weight: 600; letter-spacing: 0.14em; text-transform: uppercase; color: var(--fg-3); background: var(--ink-50); }
  .spec-table td:last-child { font-family: var(--font-mono); font-variant-numeric: tabular-nums; color: var(--ink-900); }

  /* Icons */
  .icons { display: grid; grid-template-columns: repeat(7, 1fr); gap: 16px; }
  .ic { background: white; border: 1px solid var(--border-hairline); border-radius: 12px; padding: 20px; display: flex; flex-direction: column; align-items: center; gap: 12px; }
  .ic svg { width: 40px; height: 40px; stroke: var(--ink-900); fill: none; stroke-width: 1.75; stroke-linecap: round; stroke-linejoin: round; }
  .ic .nm { font-family: var(--font-mono); font-size: 11px; color: var(--fg-3); }

  /* Notice */
  .notice { display: flex; gap: 16px; padding: 20px; background: var(--gauss-green-100); border-left: 3px solid var(--gauss-green); border-radius: 0 8px 8px 0; }
  .notice .nicon { width: 24px; height: 24px; flex: 0 0 24px; }
  .notice .nicon svg { width: 100%; height: 100%; stroke: var(--gauss-green-900); fill: none; stroke-width: 2; }
  .notice .nbody { color: var(--ink-900); font-size: 14px; line-height: 1.5; }
  .notice .nbody b { font-family: var(--font-display); font-weight: 700; }
</style>
</head>
<body>
<div class="frame">
  <header class="header">
    <div class="eyebrow" style="margin-bottom: 12px;">COMPONENTS · 04</div>
    <h1>Components</h1>
    <p>Building blocks of every Gauss artifact. Each one is copy‑pasteable into a new HTML file as long as <code>colors_and_type.css</code> is linked.</p>
  </header>

  <!-- Buttons -->
  <div class="row-label">Buttons</div>
  <div class="pad">
    <div class="row" style="margin-bottom: 16px;">
      <button class="btn btn-primary btn-lg">Solicitar proposta <span class="arrow">→</span></button>
      <button class="btn btn-primary">Solicitar proposta <span class="arrow">→</span></button>
      <button class="btn btn-secondary">Falar com engenheiro</button>
      <button class="btn btn-outline">Ver detalhes técnicos</button>
      <button class="btn btn-ghost">Cancelar</button>
    </div>
    <div class="row">
      <span class="eyebrow" style="margin-right: 12px;">DISABLED · LOADING · DESTRUCTIVE</span>
      <button class="btn btn-primary" disabled style="opacity: 0.4; cursor: not-allowed;">Solicitar proposta</button>
      <button class="btn btn-secondary"><span class="arrow" style="animation: spin 1s linear infinite; display: inline-block;">◐</span> Gerando…</button>
      <button class="btn" style="background: white; color: #B7322E; border: 1px solid #B7322E;">Cancelar contrato</button>
    </div>
  </div>
  <style>@keyframes spin { to { transform: rotate(360deg); } }</style>

  <!-- Badges -->
  <div class="row-label">Badges & status pills</div>
  <div class="pad">
    <div class="row">
      <span class="badge badge-green"><span class="dot"></span>Em operação</span>
      <span class="badge badge-ink">Aguardando aprovação</span>
      <span class="badge badge-warn">Vistoria pendente</span>
      <span class="badge badge-grid">Conectado à rede</span>
      <span class="badge badge-green">ABNT NBR 5410</span>
      <span class="badge badge-ink">12 kWp</span>
      <span class="badge badge-ink">21 módulos</span>
      <span class="badge badge-ink">CCS2</span>
    </div>
  </div>

  <!-- Inputs -->
  <div class="row-label">Form fields</div>
  <div class="pad">
    <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px;">
      <div class="field">
        <label>Nome completo</label>
        <input class="input" placeholder="Como aparece no RG" value="Bento Bentolo">
      </div>
      <div class="field">
        <label>Consumo médio mensal</label>
        <input class="input" type="text" placeholder="kWh" value="1.500 kWh">
      </div>
      <div class="field">
        <label>CEP</label>
        <input class="input" placeholder="00000-000">
      </div>
    </div>
  </div>

  <!-- Stat cards -->
  <div class="row-label">Stat cards · the workhorse of proposals</div>
  <div class="row" style="gap: 16px;">
    <div class="stat-card">
      <div class="eyebrow">ECONOMIA MENSAL</div>
      <div class="value green">R$&nbsp;1.532</div>
      <div class="note">vs. conta atual de R$ 1.875</div>
    </div>
    <div class="stat-card">
      <div class="eyebrow">PAYBACK</div>
      <div class="value">4,3 <span style="font-size: 18px; color: var(--fg-3);">anos</span></div>
      <div class="note">retorno integral do investimento</div>
    </div>
    <div class="stat-card dark">
      <div class="eyebrow" style="color: var(--gauss-green);">GERAÇÃO ESTIMADA</div>
      <div class="value green">1.448 <span style="font-size: 18px; color: rgba(255,255,255,0.6);">kWh/mês</span></div>
      <div class="note">21 módulos OSDA 575 W</div>
    </div>
    <div class="stat-card">
      <div class="eyebrow">CO₂ EVITADO · 25 ANOS</div>
      <div class="value">9,2 <span style="font-size: 18px; color: var(--fg-3);">t</span></div>
      <div class="note">cálculo conservador</div>
    </div>
  </div>

  <!-- Spec table -->
  <div class="row-label">Spec table · for equipamentos ofertados</div>
  <div class="pad" style="padding: 0; overflow: hidden;">
    <table class="spec-table">
      <thead>
        <tr><th>Item</th><th>Especificação</th></tr>
      </thead>
      <tbody>
        <tr><td>Fabricante</td><td>Canadian Solar</td></tr>
        <tr><td>Módulo</td><td>OSDA 575 W</td></tr>
        <tr><td>Potência instalada</td><td>12,075 kWp</td></tr>
        <tr><td>Inversor</td><td>9 kW</td></tr>
        <tr><td>Garantia · módulos</td><td>10 anos</td></tr>
        <tr><td>Garantia · inversor</td><td>10 anos</td></tr>
        <tr><td>Garantia · instalação</td><td>1 ano</td></tr>
      </tbody>
    </table>
  </div>

  <!-- Icons -->
  <div class="row-label">Iconography · 24 px frame, 1.75 px stroke, no fills, no clichés</div>
  <div class="icons">
    <div class="ic">
      <svg viewBox="0 0 24 24"><rect x="4" y="5" width="16" height="14"/><line x1="9" y1="5" x2="9" y2="19"/><line x1="14" y1="5" x2="14" y2="19"/><line x1="4" y1="9" x2="20" y2="9"/><line x1="4" y1="14" x2="20" y2="14"/></svg>
      <span class="nm">module</span>
    </div>
    <div class="ic">
      <svg viewBox="0 0 24 24"><rect x="5" y="7" width="14" height="10" rx="1"/><line x1="2" y1="12" x2="5" y2="12"/><line x1="19" y1="12" x2="22" y2="12"/><circle cx="16" cy="10" r="0.8" fill="currentColor"/></svg>
      <span class="nm">inverter</span>
    </div>
    <div class="ic">
      <svg viewBox="0 0 24 24"><rect x="4" y="6" width="16" height="5" rx="1"/><rect x="4" y="13" width="16" height="5" rx="1"/><line x1="10" y1="3.5" x2="14" y2="3.5"/></svg>
      <span class="nm">battery</span>
    </div>
    <div class="ic">
      <svg viewBox="0 0 24 24"><rect x="6" y="3" width="9" height="15" rx="1"/><path d="M15 8 C 19 8, 19 12, 19 14 C 19 16, 17 16, 17 14"/><line x1="9" y1="20" x2="12" y2="20"/></svg>
      <span class="nm">charger</span>
    </div>
    <div class="ic">
      <svg viewBox="0 0 24 24"><line x1="12" y1="3" x2="12" y2="21"/><line x1="6" y1="7" x2="18" y2="7"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
      <span class="nm">grid</span>
    </div>
    <div class="ic">
      <svg viewBox="0 0 24 24"><line x1="4" y1="9" x2="20" y2="9"/><polyline points="4 13 9 17 14 12 20 18"/><polyline points="20 14 20 18 16 18"/></svg>
      <span class="nm">savings</span>
    </div>
    <div class="ic">
      <svg viewBox="0 0 24 24"><line x1="4" y1="17" x2="20" y2="17"/><polyline points="4 13 9 9 14 14 20 6"/><polyline points="20 10 20 6 16 6"/></svg>
      <span class="nm">generation</span>
    </div>
  </div>

  <!-- Notice -->
  <div class="row-label">Notice / callout</div>
  <div class="notice">
    <div class="nicon">
      <svg viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"/><line x1="12" y1="8" x2="12" y2="13"/><circle cx="12" cy="16" r="0.6" fill="currentColor"/></svg>
    </div>
    <div class="nbody">
      <b>Premissa de instalação.</b> O quadro de distribuição existente deverá dispor de capacidade e espaço disponíveis para o novo circuito. As instalações seguirão as normas ABNT NBR 5410, NBR 17790 e NR‑10.
    </div>
  </div>
</div>
</body>
</html>
```