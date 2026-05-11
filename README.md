
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SpotClean India — Operations Playbook</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Instrument+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1a1a18;
    --paper: #f5f2eb;
    --paper2: #ede9df;
    --accent: #2d5a27;
    --accent2: #c8521a;
    --muted: #6b6860;
    --border: #d4cfc4;
    --white: #fdfcf8;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--paper);
    color: var(--ink);
    font-family: 'Instrument Sans', sans-serif;
    font-size: 16px;
    line-height: 1.7;
  }

  /* HERO */
  .hero {
    background: var(--ink);
    color: var(--paper);
    padding: 5rem 2rem 4rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 39px,
      rgba(255,255,255,0.04) 39px,
      rgba(255,255,255,0.04) 40px
    );
  }

  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: #8a9e7a;
    margin-bottom: 1.5rem;
    position: relative;
  }

  .hero h1 {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(3rem, 8vw, 6rem);
    line-height: 1.0;
    position: relative;
    margin-bottom: 0.5rem;
  }

  .hero h1 em {
    font-style: italic;
    color: #8a9e7a;
  }

  .hero-sub {
    font-size: 1.1rem;
    color: rgba(245, 242, 235, 0.6);
    max-width: 560px;
    margin: 1.5rem auto 0;
    position: relative;
    line-height: 1.6;
  }

  .hero-tagline {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.15em;
    color: var(--accent2);
    margin-top: 2rem;
    position: relative;
    text-transform: uppercase;
  }

  /* NAV */
  .module-nav {
    background: var(--white);
    border-bottom: 1px solid var(--border);
    padding: 0 2rem;
    display: flex;
    overflow-x: auto;
    gap: 0;
    position: sticky;
    top: 0;
    z-index: 100;
    scrollbar-width: none;
  }

  .module-nav::-webkit-scrollbar { display: none; }

  .nav-item {
    flex-shrink: 0;
    padding: 1rem 1.25rem;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    cursor: pointer;
    border-bottom: 2px solid transparent;
    transition: all 0.2s;
    white-space: nowrap;
    background: none;
    border-left: none;
    border-right: none;
    border-top: none;
  }

  .nav-item:hover { color: var(--ink); }
  .nav-item.active {
    color: var(--accent);
    border-bottom-color: var(--accent);
    font-weight: 500;
  }

  /* MAIN */
  .container {
    max-width: 820px;
    margin: 0 auto;
    padding: 3rem 2rem 6rem;
  }

  /* SECTION */
  .module { display: none; }
  .module.active { display: block; animation: fadeIn 0.3s ease; }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(8px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .module-header {
    display: flex;
    align-items: flex-start;
    gap: 1.5rem;
    margin-bottom: 2.5rem;
    padding-bottom: 2rem;
    border-bottom: 1px solid var(--border);
  }

  .module-number {
    font-family: 'DM Serif Display', serif;
    font-size: 5rem;
    line-height: 1;
    color: var(--border);
    flex-shrink: 0;
    margin-top: -0.5rem;
  }

  .module-title-block {}

  .module-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.4rem;
  }

  .module-title {
    font-family: 'DM Serif Display', serif;
    font-size: 2.2rem;
    line-height: 1.15;
    color: var(--ink);
  }

  .module-intro {
    font-size: 1.05rem;
    color: var(--muted);
    margin-top: 0.6rem;
    line-height: 1.65;
  }

  /* CARDS */
  .card {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.5rem;
    margin-bottom: 1rem;
  }

  .card-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--accent2);
    margin-bottom: 0.75rem;
  }

  .card h3 {
    font-family: 'DM Serif Display', serif;
    font-size: 1.2rem;
    margin-bottom: 0.75rem;
    color: var(--ink);
  }

  .card p, .card li {
    font-size: 0.95rem;
    color: #3a3830;
    line-height: 1.7;
  }

  /* STEPS */
  .steps { margin: 1rem 0; }

  .step {
    display: flex;
    gap: 1rem;
    margin-bottom: 1.25rem;
    align-items: flex-start;
  }

  .step-n {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    border: 1px solid var(--border);
    background: var(--paper2);
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    color: var(--muted);
    margin-top: 2px;
  }

  .step-text { font-size: 0.95rem; color: #3a3830; line-height: 1.65; }
  .step-text strong { color: var(--ink); font-weight: 600; }

  /* GRID */
  .grid2 {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1rem;
    margin-bottom: 1rem;
  }

  .stat-box {
    background: var(--paper2);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.25rem;
  }

  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.4rem;
  }

  .stat-value {
    font-family: 'DM Serif Display', serif;
    font-size: 1.8rem;
    color: var(--ink);
    line-height: 1.1;
  }

  .stat-sub {
    font-size: 0.8rem;
    color: var(--muted);
    margin-top: 0.25rem;
  }

  /* TAGS */
  .tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 0.75rem; }

  .tag {
    font-size: 12px;
    padding: 5px 12px;
    border: 1px solid var(--border);
    border-radius: 2px;
    color: var(--muted);
    background: var(--paper2);
    font-family: 'DM Mono', monospace;
  }

  .tag.no {
    border-color: #e8c4b0;
    color: #8b3a15;
    background: #fdf0e8;
  }

  .tag.yes {
    border-color: #b8d4b0;
    color: #2d5a27;
    background: #eef5ec;
  }

  /* DIVIDER */
  hr.section-divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 1.5rem 0;
  }

  /* CALLOUT */
  .callout {
    border-left: 3px solid var(--accent);
    padding: 1rem 1.25rem;
    background: #eef5ec;
    margin: 1.25rem 0;
    border-radius: 0 4px 4px 0;
  }

  .callout p {
    font-size: 0.95rem;
    color: #2a4a24;
    line-height: 1.65;
  }

  .callout.warning {
    border-left-color: var(--accent2);
    background: #fdf0e8;
  }

  .callout.warning p { color: #6b2e0e; }

  /* QUOTE */
  .big-quote {
    font-family: 'DM Serif Display', serif;
    font-size: 1.4rem;
    font-style: italic;
    color: var(--ink);
    line-height: 1.5;
    padding: 1.5rem;
    background: var(--paper2);
    border-radius: 4px;
    margin: 1.25rem 0;
    text-align: center;
  }

  /* TABLE */
  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.9rem;
    margin: 1rem 0;
  }

  th {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    padding: 0.6rem 0.75rem;
    text-align: left;
    border-bottom: 1px solid var(--border);
  }

  td {
    padding: 0.75rem;
    border-bottom: 1px solid var(--border);
    color: #3a3830;
    vertical-align: top;
  }

  tr:last-child td { border-bottom: none; }
  tr:nth-child(even) td { background: var(--paper2); }

  /* STATUS BADGES */
  .status {
    display: inline-block;
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 3px 10px;
    border-radius: 2px;
    font-weight: 500;
  }

  .status.nominated { background: #e8f0e8; color: #2d5a27; }
  .status.funded { background: #fdf0e8; color: #8b3a15; }
  .status.cleaned { background: #e6f0f8; color: #1a4870; }
  .status.maintained { background: #f0f0e8; color: #4a4a20; }
  .status.attention { background: #fce8e8; color: #8b1a1a; }

  /* FOOTER */
  .page-footer {
    background: var(--ink);
    color: rgba(245,242,235,0.5);
    text-align: center;
    padding: 3rem 2rem;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
  }

  .page-footer a {
    color: #8a9e7a;
    text-decoration: none;
  }

  .page-footer strong {
    color: var(--paper);
    display: block;
    font-size: 1.5rem;
    font-family: 'DM Serif Display', serif;
    letter-spacing: 0;
    margin-bottom: 0.5rem;
    font-weight: 400;
  }

  @media (max-width: 600px) {
    .module-header { flex-direction: column; gap: 0.5rem; }
    .module-number { font-size: 3rem; }
    .hero { padding: 3rem 1.5rem; }
    .container { padding: 2rem 1.25rem 4rem; }
  }
</style>
</head>
<body>

<div class="hero">
  <div class="hero-eyebrow">A citizen-led movement</div>
  <h1>Spot<em>Clean</em><br>India</h1>
  <p class="hero-sub">A complete, open-source playbook for cleaning and maintaining public spaces — one spot at a time. No organisation required. No permission needed.</p>
  <div class="hero-tagline">Kaam chalu. Mooh bandh. — Start working. Stop talking.</div>
</div>

<nav class="module-nav" id="nav">
  <button class="nav-item active" onclick="show(0)">01 · Choose a spot</button>
  <button class="nav-item" onclick="show(1)">02 · Team size</button>
  <button class="nav-item" onclick="show(2)">03 · Equipment</button>
  <button class="nav-item" onclick="show(3)">04 · Disposal</button>
  <button class="nav-item" onclick="show(4)">05 · Funding</button>
  <button class="nav-item" onclick="show(5)">06 · Municipality</button>
  <button class="nav-item" onclick="show(6)">07 · Corporations</button>
  <button class="nav-item" onclick="show(7)">08 · Messaging</button>
  <button class="nav-item" onclick="show(8)">09 · Governance</button>
  <button class="nav-item" onclick="show(9)">10 · Digital platform</button>
</nav>

<div class="container">

  <!-- MODULE 1 -->
  <div class="module active" id="m0">
    <div class="module-header">
      <div class="module-number">01</div>
      <div class="module-title-block">
        <div class="module-tag">Selection criteria</div>
        <div class="module-title">How to choose a spot</div>
        <div class="module-intro">Not every dirty spot is the right spot to clean. Picking strategically makes the difference between a lasting transformation and wasted effort.</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">The scoring system</div>
      <h3>Score every candidate spot before committing</h3>
      <p>Rate each spot 1–5 on four criteria. A total score below 12 means skip it for now — find a better candidate.</p>
    </div>

    <div class="grid2">
      <div class="stat-box">
        <div class="stat-label">Criterion 1</div>
        <div class="stat-value">Visibility</div>
        <div class="stat-sub">Seen by 50+ people per day? High-footfall spots create the most behaviour change.</div>
      </div>
      <div class="stat-box">
        <div class="stat-label">Criterion 2</div>
        <div class="stat-value">Access</div>
        <div class="stat-sub">Can volunteers reach it safely on foot? Is there space to work?</div>
      </div>
      <div class="stat-box">
        <div class="stat-label">Criterion 3</div>
        <div class="stat-value">Recurrence</div>
        <div class="stat-sub">Can future dumping be physically blocked or made harder through design?</div>
      </div>
      <div class="stat-box">
        <div class="stat-label">Criterion 4</div>
        <div class="stat-value">Ownership</div>
        <div class="stat-sub">Is there someone nearby — a shopkeeper, RWA, school — willing to maintain it after?</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Priority spot types</div>
      <h3>Where to look first</h3>
      <div class="steps">
        <div class="step"><div class="step-n">1</div><div class="step-text"><strong>Temple, mosque, church entrances</strong> — high footfall, community pride attached, easier to mobilise locals who feel ownership</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>School gates and surroundings</strong> — children are the future maintainers; the school can formally own ongoing upkeep</div></div>
        <div class="step"><div class="step-n">3</div><div class="step-text"><strong>Market corners and nala edges</strong> — chronic chronic dump spots that create visible, dramatic transformations</div></div>
        <div class="step"><div class="step-n">4</div><div class="step-text"><strong>Bus stop surrounds</strong> — captive audience witnesses the before and after; high symbolic value in a public commuter space</div></div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Avoid these (for now)</div>
      <div class="tags">
        <span class="tag no">Active construction zones</span>
        <span class="tag no">Private land without consent</span>
        <span class="tag no">Industrial or chemical waste</span>
        <span class="tag no">No local owner available post-clean</span>
        <span class="tag no">Politically contested locations</span>
      </div>
    </div>
  </div>

  <!-- MODULE 2 -->
  <div class="module" id="m1">
    <div class="module-header">
      <div class="module-number">02</div>
      <div class="module-title-block">
        <div class="module-tag">People & roles</div>
        <div class="module-title">Team size</div>
        <div class="module-intro">A spot fix is not a rally. Smaller, focused teams finish things. Larger groups diffuse accountability and slow everything down.</div>
      </div>
    </div>

    <div class="grid2">
      <div class="stat-box"><div class="stat-label">Minimum team</div><div class="stat-value">6</div><div class="stat-sub">Absolute floor for a safe, complete fix</div></div>
      <div class="stat-box"><div class="stat-label">Ideal team</div><div class="stat-value">12–15</div><div class="stat-sub">Enough for all roles without crowding</div></div>
      <div class="stat-box"><div class="stat-label">Maximum useful</div><div class="stat-value">25</div><div class="stat-sub">Beyond this, people become spectators</div></div>
      <div class="stat-box"><div class="stat-label">Time per spot</div><div class="stat-value">3–4 hrs</div><div class="stat-sub">7am–10 or 11am is the ideal window</div></div>
    </div>

    <div class="card">
      <div class="card-label">Role breakdown — 12 person team</div>
      <h3>Everyone has a job</h3>
      <p style="margin-bottom:1rem; font-size:0.9rem; color:var(--muted);">There are no leaders — only coordinators for the day. Rotate roles across events.</p>
      <div class="steps">
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>Day coordinators</strong> — logistics, safety briefing, single point of contact for the municipal officer. Not "bosses."</div></div>
        <div class="step"><div class="step-n">4</div><div class="step-text"><strong>Sweepers & collectors</strong> — primary clearing, bagging, sorting wet from dry waste throughout the event</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>Surface team</strong> — scrubbing walls and ground, applying anti-litter texture coat, minor pothole filling if applicable</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>Greening crew</strong> — potted plants, small murals, planters. The most visible transformation signal to passersby</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>Documenters</strong> — GPS-timestamped before and after photos from identical angles, uploaded to the platform during the event</div></div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Day timeline</div>
      <h3>A single spot fix, minute by minute</h3>
      <div class="steps">
        <div class="step"><div class="step-n">7:00</div><div class="step-text"><strong>Arrive and brief</strong> — 10 minutes, cover roles, safety, and photograph the before-state from fixed reference points</div></div>
        <div class="step"><div class="step-n">7:15</div><div class="step-text"><strong>Clear and bag</strong> — all waste removed, sorted wet/dry/hazardous. This is the hardest and most important phase</div></div>
        <div class="step"><div class="step-n">9:00</div><div class="step-text"><strong>Surface & green</strong> — scrub, paint, plant. The spot starts becoming something people can be proud of</div></div>
        <div class="step"><div class="step-n">10:30</div><div class="step-text"><strong>Install messaging</strong> — the neighbourhood tile, the bin, the QR plate (see Module 8)</div></div>
        <div class="step"><div class="step-n">11:00</div><div class="step-text"><strong>After photos & upload</strong> — from identical reference angles. Submit to platform. You're done.</div></div>
      </div>
    </div>
  </div>

  <!-- MODULE 3 -->
  <div class="module" id="m2">
    <div class="module-header">
      <div class="module-number">03</div>
      <div class="module-title-block">
        <div class="module-tag">What to bring</div>
        <div class="module-title">Equipment</div>
        <div class="module-intro">Everything your team needs, broken down by phase. Buy locally, keep it simple.</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Cleaning — per 12-person team</div>
      <div class="tags" style="margin-top:0.5rem;">
        <span class="tag">Heavy-duty brooms ×6</span>
        <span class="tag">Stiff scrub brushes ×4</span>
        <span class="tag">Large garbage bags ×50</span>
        <span class="tag">Rubber gloves ×15 pairs</span>
        <span class="tag">Face masks ×15</span>
        <span class="tag">Shovels ×3</span>
        <span class="tag">Buckets ×4</span>
        <span class="tag">Tongs for hazardous items ×2</span>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Surface treatment</div>
      <div class="tags" style="margin-top:0.5rem;">
        <span class="tag">Phenyl or disinfectant concentrate</span>
        <span class="tag">Anti-litter texture paint (rough coat)</span>
        <span class="tag">Paint rollers and trays ×4</span>
        <span class="tag">Wire brush for wall prep</span>
        <span class="tag">Masking tape</span>
        <span class="tag">Drop sheets ×2</span>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Greening</div>
      <div class="tags" style="margin-top:0.5rem;">
        <span class="tag">Hardy potted plants ×4–6 (local species)</span>
        <span class="tag">Quick-set cement for pot anchoring</span>
        <span class="tag">Small planter boxes if wall available</span>
        <span class="tag">Watering can ×1</span>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Documentation</div>
      <div class="tags" style="margin-top:0.5rem;">
        <span class="tag">Smartphone with GPS ×2 minimum</span>
        <span class="tag">Measuring tape (reference shot framing)</span>
        <span class="tag">Small marker stakes for fixed photo points</span>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Cost estimates</div>
      <table>
        <thead><tr><th>Fix type</th><th>Estimated cost</th></tr></thead>
        <tbody>
          <tr><td>Basic clean, no paint</td><td>₹2,000–4,000</td></tr>
          <tr><td>Full clean + surface treatment + greening</td><td>₹8,000–15,000</td></tr>
          <tr><td>With mural or custom signage</td><td>₹15,000–25,000</td></tr>
          <tr><td>Monthly upkeep (ongoing)</td><td>₹500–1,000</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- MODULE 4 -->
  <div class="module" id="m3">
    <div class="module-header">
      <div class="module-number">04</div>
      <div class="module-title-block">
        <div class="module-tag">Critical logistics</div>
        <div class="module-title">Disposal</div>
        <div class="module-intro">The biggest operational failure of cleanup drives is generating bags of garbage with nowhere to go. Solve this before the event, never on the day.</div>
      </div>
    </div>

    <div class="callout warning">
      <p><strong>Non-negotiable rule:</strong> Disposal must be arranged at least 5 days before the event. A spotfix that leaves garbage bags piled on the street has made things worse, not better.</p>
    </div>

    <div class="card">
      <div class="card-label">Pre-event checklist</div>
      <div class="steps">
        <div class="step"><div class="step-n">1</div><div class="step-text"><strong>Contact the ward sanitation inspector</strong> — not the municipal office generally, the ward-level inspector directly. Request a dedicated pickup vehicle at the end of the event. Get a named person's number.</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>Pre-sort on-site</strong> — wet and organic waste in green bags, dry recyclables in blue or white bags. Many cities have segregated collection and a truck may refuse unsegregated waste.</div></div>
        <div class="step"><div class="step-n">3</div><div class="step-text"><strong>Locate the nearest kabadiwala</strong> in advance. Plastic, metal, cardboard and paper can be collected by them — often for free or for a small payment. This meaningfully reduces total waste volume.</div></div>
        <div class="step"><div class="step-n">4</div><div class="step-text"><strong>Identify a composting facility</strong> for organic waste — vermicompost units, municipal compost sites, or a nearby community garden willing to take it.</div></div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Hazardous material protocol</div>
      <h3>Do not touch these items</h3>
      <p>Syringes, medical waste, chemicals, unknown liquids, asbestos — flag with tape, photograph with GPS, and submit a separate report to the municipality's hazardous waste cell. Never bag with general waste. Never attempt removal without proper equipment.</p>
    </div>

    <div class="card">
      <div class="card-label">Where recovered materials go</div>
      <table>
        <thead><tr><th>Material</th><th>Goes to</th></tr></thead>
        <tbody>
          <tr><td>Scrap metal, cardboard, paper, plastic</td><td>Kabadiwala</td></tr>
          <tr><td>Glass</td><td>Municipality recycler</td></tr>
          <tr><td>Organic / food waste</td><td>Nearest composting facility</td></tr>
          <tr><td>Construction debris</td><td>Municipality debris yard only</td></tr>
          <tr><td>Hazardous waste</td><td>Municipality hazardous cell — separate report</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- MODULE 5 -->
  <div class="module" id="m4">
    <div class="module-header">
      <div class="module-number">05</div>
      <div class="module-title-block">
        <div class="module-tag">Money</div>
        <div class="module-title">Funding a spot</div>
        <div class="module-intro">Money must never concentrate at the centre. Each spot is funded independently. This prevents corruption, capture, and the NGO disease of funding-seeking replacing mission.</div>
      </div>
    </div>

    <div class="big-quote">"Fund the spot, not the organisation."</div>

    <div class="card">
      <div class="card-label">Funding tiers — simplest first</div>
      <div class="steps">
        <div class="step"><div class="step-n">1</div><div class="step-text"><strong>Self-funded team</strong> — 12 volunteers contributing ₹200–350 each covers a basic clean. No external dependencies, maximum speed, zero bureaucracy.</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>Local business contribution</strong> — ask nearby shops to donate materials, not cash. A hardware store donating brooms and bags is simpler and corruption-proof. Easiest ask: the shop whose entrance you're cleaning.</div></div>
        <div class="step"><div class="step-n">3</div><div class="step-text"><strong>RWA or housing society funds</strong> — formally request ₹5,000–10,000 from the society's discretionary maintenance budget. Many RWAs have this capacity and respond well to a specific, bounded ask.</div></div>
        <div class="step"><div class="step-n">4</div><div class="step-text"><strong>Platform micro-crowdfunding</strong> — any nominated spot on the digital platform can receive public donations, capped at ₹25,000. Funds released against receipts only. The spot team lead is named and accountable publicly.</div></div>
        <div class="step"><div class="step-n">5</div><div class="step-text"><strong>Corporate CSR top-up</strong> — for complex or large spots only. Subject to strict no-branding rules (see Module 7). Never approached before Tiers 1–4 are exhausted.</div></div>
      </div>
    </div>

    <div class="callout">
      <p>All spot-level spending is photographed, receipted, and posted publicly on the platform within 7 days. There are no exceptions. Transparency is the accountability mechanism.</p>
    </div>
  </div>

  <!-- MODULE 6 -->
  <div class="module" id="m5">
    <div class="module-header">
      <div class="module-number">06</div>
      <div class="module-title-block">
        <div class="module-tag">Official partnership</div>
        <div class="module-title">Working with municipalities</div>
        <div class="module-intro">Don't ask for money or permission. Ask for three specific, low-cost commitments that make the clean durable.</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">The Spot Adoption Agreement</div>
      <h3>A one-page social contract</h3>
      <p style="margin-bottom:1rem;">Not a legal document. Signed by a named ward sanitation inspector and the spot's local owner. It has exactly three commitments:</p>
      <div class="steps">
        <div class="step"><div class="step-n">M</div><div class="step-text"><strong>Municipality commits</strong> to garbage pickup from this spot minimum 3× per week, and to installing one waste bin within 30 days of the clean date</div></div>
        <div class="step"><div class="step-n">O</div><div class="step-text"><strong>Local owner commits</strong> to a monthly walk-through and to reporting any deterioration via the platform app within 48 hours of noticing it</div></div>
        <div class="step"><div class="step-n">S</div><div class="step-text"><strong>SpotClean commits</strong> to a 90-day follow-up visit with a public condition report posted online — visible to the municipality, the community, and anyone who donated</div></div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">How to get a yes</div>
      <div class="steps">
        <div class="step"><div class="step-n">1</div><div class="step-text"><strong>Don't approach the top.</strong> Go to the ward sanitation inspector — the person who actually controls trucks and daily schedules. They have more operational authority than they're credited for, and fewer political pressures.</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>Frame it as free labour for them.</strong> You are cleaning a spot they would otherwise have to budget for. The ask is minimal — one truck visit on one day, and one bin within 30 days.</div></div>
        <div class="step"><div class="step-n">3</div><div class="step-text"><strong>Show them the platform score.</strong> Ward cleanliness scores are increasingly tied to state rankings and commissioner evaluations. A clean, maintained, publicly documented spot improves their metrics directly.</div></div>
        <div class="step"><div class="step-n">4</div><div class="step-text"><strong>Name them on the platform.</strong> The inspector who signed the agreement is named publicly on the spot's page — credit for the municipality when things go well, and gentle accountability when they don't.</div></div>
      </div>
    </div>
  </div>

  <!-- MODULE 7 -->
  <div class="module" id="m6">
    <div class="module-header">
      <div class="module-number">07</div>
      <div class="module-title-block">
        <div class="module-tag">Corporate participation</div>
        <div class="module-title">How corporations can help</div>
        <div class="module-intro">Corporations are fuel, not drivers. Funders never determine which spots get cleaned, how they are cleaned, or what is written on the walls.</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">What corporations can do</div>
      <div class="tags" style="margin-top:0.5rem;">
        <span class="tag yes">Fund materials for platform-nominated spots</span>
        <span class="tag yes">Provide employees as volunteers</span>
        <span class="tag yes">Fund platform operating costs (disclosed publicly)</span>
        <span class="tag yes">Receive internal ESG and CSR recognition</span>
        <span class="tag yes">Count volunteer hours toward CSR requirements</span>
      </div>
    </div>

    <div class="card">
      <div class="card-label">What corporations cannot do</div>
      <div class="tags" style="margin-top:0.5rem;">
        <span class="tag no">No logo on cleaned walls or surfaces</span>
        <span class="tag no">No company name on any installed signage</span>
        <span class="tag no">No selecting which spots receive funding</span>
        <span class="tag no">No press releases naming specific spots</span>
        <span class="tag no">No employees-only events — must mix with community</span>
        <span class="tag no">No naming rights of any kind</span>
      </div>
    </div>

    <div class="callout warning">
      <p>Any corporate that cannot accept these terms is not the right partner. There are plenty who will accept them. The no-branding rule is the single most important safeguard against the model becoming an advertising platform.</p>
    </div>

    <div class="card">
      <div class="card-label">How the conversation goes</div>
      <h3>The pitch to a corporate CSR team</h3>
      <p>Your employees spend one Saturday morning cleaning a real spot in the community they work in. They work alongside local residents, not as a separate corporate group. No speeches, no banners, no photographers except our platform documenters. You get: ESG documentation, employee satisfaction and team-building value, and the knowledge that something real was done. We get: materials funded and capable volunteers. That's the whole deal.</p>
    </div>
  </div>

  <!-- MODULE 8 -->
  <div class="module" id="m7">
    <div class="module-header">
      <div class="module-number">08</div>
      <div class="module-title-block">
        <div class="module-tag">Behaviour change</div>
        <div class="module-title">Messaging after a clean</div>
        <div class="module-intro">Shame-based messaging doesn't work. Signs saying "do not litter — fine ₹500" are ignored everywhere. What works is signalling that the space is cared for and belongs to someone.</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Physical interventions that change behaviour</div>
      <div class="steps">
        <div class="step"><div class="step-n">1</div><div class="step-text"><strong>Anti-litter texture coat on walls</strong> — rough-textured paint actively discourages urination and poster-plastering. People treat a textured, painted wall differently from a bare one. This is the single most proven physical intervention.</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>A mural or geometric pattern</strong> — even a simple painted design signals intentionality and human care. People do not litter painted walls as readily as blank ones. The art does not need to be professional.</div></div>
        <div class="step"><div class="step-n">3</div><div class="step-text"><strong>A living plant, visibly tended</strong> — nothing signals ongoing human care more powerfully than a living thing. Even one well-placed pot plant changes the psychology of a corner.</div></div>
        <div class="step"><div class="step-n">4</div><div class="step-text"><strong>A cemented, named bin</strong> — not a flimsy can. An anchored, clearly marked, regularly-emptied bin. Its presence alone changes disposal behaviour. An empty-looking space with no bin makes littering feel inevitable.</div></div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">The one message to leave behind</div>
      <h3>In the local language, on a durable tile or painted text</h3>
      <div class="big-quote" style="font-size:1.2rem;">"This space is loved by the people of [neighbourhood name]. Help us keep it this way."</div>
      <p>No organisation name. No website. No QR code on the wall. The QR code goes on a small weatherproof steel plate bolted nearby — linking to the spot's public page for those who want to get involved. The wall belongs to the neighbourhood, not to any movement.</p>
    </div>

    <div class="card">
      <div class="card-label">What not to write</div>
      <div class="tags">
        <span class="tag no">Do not litter — fine ₹500</span>
        <span class="tag no">CCTV surveillance in progress</span>
        <span class="tag no">Keep India clean</span>
        <span class="tag no">Any organisation name or logo</span>
        <span class="tag no">Government scheme branding</span>
      </div>
    </div>
  </div>

  <!-- MODULE 9 -->
  <div class="module" id="m8">
    <div class="module-header">
      <div class="module-number">09</div>
      <div class="module-title-block">
        <div class="module-tag">Structure</div>
        <div class="module-title">Keeping it lean</div>
        <div class="module-intro">Every Indian civic organisation eventually gets captured — by a politician, a funder, a charismatic leader, or its own growing bureaucracy. This structure is designed to make capture structurally difficult.</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Organisational structure</div>
      <div class="steps">
        <div class="step"><div class="step-n">1</div><div class="step-text"><strong>No national president, no national office.</strong> The methodology is the organisation. Anyone following this playbook is SpotClean. No one can be expelled or installed.</div></div>
        <div class="step"><div class="step-n">2</div><div class="step-text"><strong>A 5-person platform trust</strong> — the only formal entity. Manages the digital platform, domain, and any pooled operational funds. Rotating 2-year terms, publicly named, financials open in real time. One term only — no renewals.</div></div>
        <div class="step"><div class="step-n">3</div><div class="step-text"><strong>City nodes, not chapters.</strong> Each city has a loose WhatsApp or Signal group of active spot owners. No elections, no hierarchy. The most active people naturally coordinate. One node cannot make decisions for another.</div></div>
        <div class="step"><div class="step-n">4</div><div class="step-text"><strong>All money is spot-level.</strong> Central fund maximum: ₹10 lakh at any time — enough for platform operations, nothing more. Any donation above ₹1 lakh is disclosed publicly within 48 hours of receipt.</div></div>
        <div class="step"><div class="step-n">5</div><div class="step-text"><strong>One paid contractor.</strong> A platform manager on an annual contract, renewable by majority trust vote, replaceable at any time. Not an employee. No other paid staff — all coordination is voluntary.</div></div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Anti-capture rules — baked into the structure</div>
      <div class="tags">
        <span class="tag no">No politician can be a trust member</span>
        <span class="tag no">No funder can sit on the trust</span>
        <span class="tag yes">Methodology is Creative Commons licensed — can never be owned</span>
        <span class="tag yes">Any group can use the SpotClean name without permission</span>
        <span class="tag yes">Platform code is open-source on GitHub from day one</span>
        <span class="tag yes">All finances publicly visible in real time</span>
      </div>
    </div>

    <div class="callout">
      <p>The open-source license is the most important governance mechanism. If the organisation is ever captured or goes dormant, anyone can fork it, use the name, and continue. The movement cannot be killed by killing the organisation.</p>
    </div>
  </div>

  <!-- MODULE 10 -->
  <div class="module" id="m9">
    <div class="module-header">
      <div class="module-number">10</div>
      <div class="module-title-block">
        <div class="module-tag">Technology</div>
        <div class="module-title">The digital platform</div>
        <div class="module-intro">One lightweight progressive web app — no app store required, works on any smartphone, functional on 2G. Four core functions only. No feature creep.</div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Function 1 — Spot map</div>
      <h3>A live public map of all spots</h3>
      <p style="margin-bottom:1rem;">Anyone can submit a spot — one photo, one GPS pin, one sentence description. 90 seconds. No signup required to nominate. Each spot has a live status:</p>
      <div class="tags">
        <span class="status nominated">Nominated</span>
        <span class="status funded">Funded</span>
        <span class="status cleaned">Cleaned</span>
        <span class="status maintained">Maintained</span>
        <span class="status attention">Needs attention</span>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Function 2 — Clean reports</div>
      <h3>Permanent public record for every spot</h3>
      <p>After cleaning, the team submits: GPS-verified before photo, GPS-verified after photo, team size, materials used, waste volume estimate, disposal method, and the name of the municipal officer on the Spot Adoption Agreement. This record never disappears.</p>
    </div>

    <div class="card">
      <div class="card-label">Function 3 — Monthly check-ins</div>
      <h3>What makes the clean permanent</h3>
      <p>Every cleaned spot has a named local owner. They receive a monthly notification: <em>"How is [spot name] doing?"</em> They submit one photo and a 1–5 condition rating. If the rating drops below 3 for two consecutive months, the spot is flagged publicly and the city node is notified to mobilise a refresh team.</p>
    </div>

    <div class="card">
      <div class="card-label">Function 4 — Micro-funding</div>
      <h3>Peer-to-peer, not centralised</h3>
      <p>Nominated spots can enable a funding widget. Maximum ₹25,000 per spot. All donors named publicly. Funds disbursed directly to the spot team lead's UPI ID against submitted receipts. The platform trust never touches spot-level money — it flows peer to peer.</p>
    </div>

    <div class="card">
      <div class="card-label">Technical requirements</div>
      <div class="tags">
        <span class="tag yes">Progressive web app — no app store install</span>
        <span class="tag yes">Works on 2G and 3G networks</span>
        <span class="tag yes">Offline photo capture, uploads when connected</span>
        <span class="tag yes">GPS mandatory for all photo submissions</span>
        <span class="tag yes">Open source on GitHub from day one</span>
        <span class="tag yes">Target under ₹15,000/month hosting cost</span>
      </div>
    </div>
  </div>

</div>

<footer class="page-footer">
  <strong>SpotClean India</strong>
  Open-source playbook · Creative Commons Attribution licence · Free to use, adapt, and share<br><br>
  This playbook may be used by anyone, anywhere, without permission.<br>
  To contribute or build the platform: <a href="https://raulscooper.github.io"> github linkn a</a> (coming soon)
</footer>

<script>
  function show(i) {
    document.querySelectorAll('.module').forEach((m, j) => m.classList.toggle('active', j === i));
    document.querySelectorAll('.nav-item').forEach((b, j) => b.classList.toggle('active', j === i));
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
</script>

</body>
</html>
