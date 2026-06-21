---
layout: default
title: CONCERT Campaign
description: A coordinated, multi-wavelength campaign to understand how star formation operates in the Central Molecular Zone.
---

<section class="hero">
  <div>
    <p class="eyebrow">Central Molecular Zone star formation campaign</p>
    <h1>CONCERT</h1>
    <p class="lead">CONCERT is a coordinated campaign to connect the turbulent, magnetized cloud environment of the Galactic Center to the small-scale physics of filaments, dense cores, disks, streamers, and protostellar feedback.</p>
    <div class="button-row">
      <a class="button" href="#publications">Publication Map</a>
      <a class="pill" href="https://ui.adsabs.harvard.edu/public-libraries/ZWd6s-SbQcWQBeDGrC3kiw" target="_blank" rel="noopener">ADS Library</a>
      <a class="pill" href="https://github.com/CMZconcert/CMZconcert.github.io" target="_blank" rel="noopener">GitHub</a>
    </div>
  </div>
  <aside class="hero-panel" aria-label="Campaign scope">
    <div class="metric-grid">
      <div class="metric">
        <strong>5-500 GHz</strong>
        <span>multi-band radio/submillimeter coverage</span>
      </div>
      <div class="metric">
        <strong>100 AU-100 pc</strong>
        <span>from disks to cloud context</span>
      </div>
      <div class="metric">
        <strong>4 clouds</strong>
        <span>Sgr C, the 20 km/s cloud, G0.253+0.016, and clouds e/f</span>
      </div>
      <div class="metric">
        <strong>ALMA + VLA + JCMT</strong>
        <span>deep mosaics, polarization, and long baselines</span>
      </div>
    </div>
  </aside>
</section>

<section id="logic" class="section">
  <div class="card">
    <p class="eyebrow">Campaign Logic</p>
    <h2>Why CONCERT exists alongside large CMZ surveys</h2>
    <p class="section-intro">Large programs such as CMZoom and ACES give the community the wide-area view. CONCERT deliberately goes deeper and finer on a small, carefully chosen sample so that the same clouds can be followed from parsec-scale gas flows down to dense cores and 100 AU-scale disk structures.</p>
    <div class="flow" aria-label="Scale flow">
      <div class="flow-step">
        <h3>Clouds</h3>
        <p>Measure fragmentation, pressure confinement, density structure, and cloud-wide source populations.</p>
      </div>
      <div class="flow-step">
        <h3>Filaments</h3>
        <p>Identify shocks, absorption structures, HNCO fibers, and gas reservoirs feeding dense structures.</p>
      </div>
      <div class="flow-step">
        <h3>Cores</h3>
        <p>Connect core mass functions, outflows, magnetic fields, and local gravitational flows.</p>
      </div>
      <div class="flow-step">
        <h3>Disks</h3>
        <p>Resolve rotating disks, envelopes, spirals, and streamers around massive protostars.</p>
      </div>
    </div>
  </div>
</section>

<section class="section">
  <div class="card">
    <h2>The working hypothesis</h2>
    <ul class="logic-list">
      <li><strong>The CMZ environment is exotic:</strong> high turbulence, high pressure, strong tidal fields, complex line-of-sight structure, and dynamically important magnetic fields make the clouds look very different from Galactic disk clouds.</li>
      <li><strong>The microphysics may still be familiar:</strong> when CONCERT reaches core and disk scales, the basic ingredients of massive star formation - fragmentation, infall, rotation, outflows, and magnetic regulation - still appear to operate.</li>
      <li><strong>The key is connection across scales:</strong> each publication answers one scale-dependent question, but the campaign is designed so the answers feed into one coherent picture of gas recycling and transformation in the CMZ.</li>
    </ul>
  </div>
</section>

<section id="programs" class="section">
  <p class="eyebrow">Programs</p>
  <h2>Named subcampaigns and how they fit together</h2>
  <p class="section-intro">CONCERT uses a music-inspired naming scheme for focused observing programs. The names are useful shorthand for the campaign logic: characterize the gas, find hidden reservoirs, measure magnetic forces, then follow gas into disks.</p>
  <div class="grid">
    <article class="program-card">
      <span class="program-tag">QUARTET</span>
      <h3>Quad-band excitation mapping</h3>
      <p>Four ALMA bands toward Sgr C, with 12-m, 7-m, and TP data, are designed to sample gas density and temperature from cloud to core scales. This program connects physical conditions to N-PDFs and core mass functions.</p>
    </article>
    <article class="program-card">
      <span class="program-tag">MAZURKA</span>
      <h3>Molecular absorption and hidden gas</h3>
      <p>CO and related absorption filaments reveal gas that can be missed in emission-only views. These structures test whether foreground reservoirs, self-absorption, and shocks reshape the apparent CMZ cloud structure.</p>
    </article>
    <article class="program-card">
      <span class="program-tag">POLKA</span>
      <h3>Polarization of cores and disks</h3>
      <p>ALMA Band 7 polarization resolves magnetic fields around dense cores. The goal is to compare magnetic tension, gravity, and turbulent distortion where gas is actively moving into cores.</p>
    </article>
    <article class="program-card">
      <span class="program-tag">BALLAD</span>
      <h3>Broadband long-baseline disks</h3>
      <p>Long-baseline ALMA observations use line forests and continuum structure to separate disks, envelopes, spirals, and streamers around massive protostars in the CMZ.</p>
    </article>
    <article class="program-card">
      <span class="program-tag">DUET</span>
      <h3>Dual-band continuum census</h3>
      <p>Matched 1.3 mm and 3 mm observations provide cloud-wide spectral indices and a source census, linking dust cores, free-free emission, and evolutionary stage across multiple CMZ clouds.</p>
    </article>
  </div>
</section>

<section id="publications" class="section">
  <p class="eyebrow">Publication Map</p>
  <h2>How the papers connect</h2>
  <p class="section-intro">The publication map is organized by the question each paper answers. It begins with foundation papers that define the CMZ star-formation problem, then follows the CONCERT sequence from cloud-scale structure to disk-scale accretion.</p>
  <div class="grid">
    {% assign publications = site.data.publications | sort: "order" %}
    {% for paper in publications %}
    <article class="publication-card" id="{{ paper.id }}">
      <div class="publication-topline">
        <time>{{ paper.year }}</time>
        <span class="publication-phase">{{ paper.phase }}</span>
      </div>
      <p class="publication-tags">
        <span class="scale">{{ paper.scale }}</span>
        <span class="publication-program">{{ paper.program }}</span>
      </p>
      <a href="{{ paper.adsurl }}" target="_blank" rel="noopener">{{ paper.citation }}</a>
      <p class="publication-title">{{ paper.title }}</p>
      <p>{{ paper.summary }}</p>
      <p class="publication-links">
        <a href="{{ paper.adsurl }}" target="_blank" rel="noopener">ADS</a>
        {% if paper.arxiv %}<a href="{{ paper.arxiv }}" target="_blank" rel="noopener">arXiv</a>{% endif %}
        {% if paper.doi %}<a href="{{ paper.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
      </p>
    </article>
    {% endfor %}
  </div>
  <div class="note">
    <p><strong>Reading the sequence:</strong> the 2015-2019 papers establish the 20 km/s cloud, CMZ star-formation rates, and the early-phase census. The CONCERT sequence then adds fragmentation, outflows, core statistics, filaments, continuum source populations, protocluster assembly, magnetic forces, and disk/envelope/streamer systems. The campaign is therefore a connected argument, not a set of isolated case studies.</p>
  </div>
</section>

<section class="section">
  <p class="eyebrow">Context</p>
  <h2>How CONCERT complements wide-field CMZ surveys</h2>
  <div class="grid">
    <article class="program-card">
      <h3>ACES and CMZoom provide the map</h3>
      <p>Wide-field surveys define the CMZ environment, identify filaments and source populations, and provide comparison samples.</p>
    </article>
    <article class="program-card">
      <h3>CONCERT provides depth</h3>
      <p>Deep, matched-resolution, multi-band observations of selected clouds allow physical conditions, magnetic fields, and disk-scale structures to be studied in the same targets.</p>
    </article>
    <article class="program-card">
      <h3>The synthesis tests universality</h3>
      <p>The emerging picture is that star-formation microphysics still works in the CMZ, but the extreme environment changes the boundary conditions and makes the same physics appear unusual.</p>
    </article>
  </div>
</section>

<section id="team" class="section">
  <div class="card">
    <p class="eyebrow">Team</p>
    <h2>Core team and collaborators</h2>
    <p class="section-intro">CONCERT is led by a SHAO-centered team with collaborators across Asia, Europe, and North America.</p>
    <ul class="team-list">
      <li>Xing Lu</li>
      <li>Jixiang Weng</li>
      <li>Feichi Li</li>
      <li>Guangran Wang</li>
      <li>Yuhua Liu</li>
      <li>Jiancheng Feng</li>
      <li>Xu Zhang</li>
      <li>Suinan Zhang</li>
      <li>Fengwei Xu</li>
      <li>Kai Yang</li>
      <li>Zhenying Zhang</li>
      <li>Xing Pan</li>
      <li>Yu Cheng</li>
      <li>Shanghuo Li</li>
      <li>Junhao Liu</li>
      <li>Sihan Jiao</li>
      <li>Qizhou Zhang</li>
      <li>Adam Ginsburg</li>
      <li>Hauyu Baobab Liu</li>
      <li>Cara Battersby</li>
      <li>Daniel Walker</li>
      <li>Ashley Barnes</li>
      <li>Jonathan Henshaw</li>
      <li>Elizabeth A. C. Mills</li>
      <li>Thushara Pillai</li>
      <li>Jens Kauffmann</li>
      <li>Steven Longmore</li>
    </ul>
  </div>
</section>
