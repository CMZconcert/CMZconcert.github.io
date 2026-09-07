---
layout: default
lang: en
title: CONCERT Campaign
description: A coordinated, multi-wavelength campaign to understand how star formation operates in the Central Molecular Zone.
---

<section class="hero">
  <div>
    <p class="eyebrow">Central Molecular Zone star formation campaign</p>
    <h1>CONCERT</h1>
    <p class="campaign-full-name">Coordinated Observations of Nebulae in the Central Molecular Zone Exploring gas Recycling and Transformation</p>
    <p class="lead">CONCERT connects the turbulent, magnetized cloud environment of the Galactic Center to the small-scale physics of filaments, dense cores, disks, streamers, and protostellar feedback.</p>
    <div class="button-row">
      <a class="button" href="#publications">Publication Map</a>
      <a class="pill" href="https://ui.adsabs.harvard.edu/public-libraries/ZWd6s-SbQcWQBeDGrC3kiw" target="_blank" rel="noopener">ADS Library</a>
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
    <figure class="logic-figure">
      <img src="{{ '/public/img/cmz-overview.png' | relative_url }}" alt="Annotated multi-wavelength view of the Central Molecular Zone showing the four CONCERT target clouds">
      <figcaption>CONCERT focuses on four selected clouds across the Central Molecular Zone: clouds e/f, G0.253+0.016, the 20 km/s cloud, and Sgr C.</figcaption>
    </figure>
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
  <p class="section-intro">CONCERT uses a music-inspired naming scheme for focused observing and synthesis programs. The expanded names below show the role of each subcampaign: characterize the gas, find hidden reservoirs, measure magnetic forces, follow gas into disks, and harmonize unconnected CMZ surveys for joint studies of outflows, dense cores, and filaments.</p>
  <div class="grid">
    {% assign subcampaigns = site.data.subcampaigns %}
    {% assign publications = site.data.publications | sort: "order" %}
    {% for program in subcampaigns %}
    <article class="program-card program-{{ program.css_class }}">
      <span class="program-tag">{{ program.key }}</span>
      <h3>{{ program.title }}</h3>
      <p class="program-full-name">{{ program.full_name }}</p>
      {% if program.logo %}
      <figure class="program-logo">
        <img src="{{ program.logo | relative_url }}" alt="{{ program.logo_alt }}">
      </figure>
      {% endif %}
      <p>{{ program.summary }}</p>
      {% if program.visualization_url %}
      <p class="program-links">
        <a class="visualization-link" href="{{ program.visualization_url }}" target="_blank" rel="noopener">{{ program.visualization_label | default: "Data visualization" }}</a>
      </p>
      {% endif %}
      <div class="program-publications">
        <p class="program-publications-title">Related publications</p>
        <ul>
          {% assign publication_count = 0 %}
          {% for paper in publications %}
            {% if paper.subcampaigns contains program.key %}
              {% assign publication_count = publication_count | plus: 1 %}
              <li><a href="#{{ paper.id }}">{{ paper.citation }}</a></li>
            {% endif %}
          {% endfor %}
          {% if publication_count == 0 %}
            <li class="muted">Publication in preparation; no published paper in the current list yet.</li>
          {% endif %}
        </ul>
      </div>
    </article>
    {% endfor %}
  </div>
</section>

<section id="publications" class="section">
  <p class="eyebrow">Publication Map</p>
  <h2>How the papers connect</h2>
  <p class="section-intro">The publication map is organized by the question each paper answers. It begins with foundation papers that define the CMZ star-formation problem, then follows the CONCERT sequence from cloud-scale structure to disk-scale accretion.</p>
  <div class="grid">
    {% assign publications = site.data.publications | sort: "order" %}
    {% for paper in publications %}
    <article class="publication-card {% if paper.subcampaigns.size > 0 %}program-{{ paper.subcampaigns.first | downcase }}{% else %}program-unassigned{% endif %}" id="{{ paper.id }}">
      <div class="publication-topline">
        <time>{{ paper.year }}</time>
        <span class="publication-phase">{{ paper.phase }}</span>
      </div>
      <p class="publication-tags">
        <span class="scale">{{ paper.scale }}</span>
        <span class="publication-program">{{ paper.program }}</span>
      </p>
      {% if paper.image %}
      <figure class="publication-figure">
        <img src="{{ paper.image | relative_url }}" alt="{{ paper.image_alt }}">
      </figure>
      {% endif %}
      <a href="{{ paper.adsurl }}" target="_blank" rel="noopener">{{ paper.citation }}</a>
      <p class="publication-title">{{ paper.title }}</p>
      <p>{{ paper.summary }}</p>
      <p class="publication-links">
        <a href="{{ paper.adsurl }}" target="_blank" rel="noopener">ADS</a>
        {% if paper.arxiv %}<a href="{{ paper.arxiv }}" target="_blank" rel="noopener">arXiv</a>{% endif %}
        {% if paper.doi %}<a href="{{ paper.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
        {% if paper.visualization_url %}<a class="visualization-link" href="{{ paper.visualization_url }}" target="_blank" rel="noopener">{{ paper.visualization_label | default: "Data visualization" }}</a>{% endif %}
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
    <article class="program-card program-chorus">
      <h3>CHORUS harmonizes disconnected surveys</h3>
      <p>CHORUS gathers products from separate CMZ observing projects and reanalyzes them consistently, so outflows, dense cores, and filaments can be compared as parts of one ecosystem.</p>
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
    <p class="section-intro">The visible team list below includes collaborators represented in the current CONCERT publication list, as well as researchers actively working on CONCERT papers. CONCERT remains open to anyone interested in the campaign; please contact <a href="mailto:{{ site.email }}">{{ site.email }}</a> if you would like to get involved.</p>
    <ul class="team-list">
      {% for person in site.data.team %}
      <li{% if person.et_al %} class="team-etal"{% endif %}>{{ person.name }}</li>
      {% endfor %}
    </ul>
  </div>
</section>
