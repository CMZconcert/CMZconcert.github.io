---
layout: default
lang: zh
title: CONCERT 观测计划
description: 一个多波段协同观测计划，研究中央分子区中的恒星形成如何发生。
permalink: /zh/
---

<section class="hero">
  <div>
    <p class="eyebrow">中央分子区恒星形成观测计划</p>
    <h1>CONCERT</h1>
    <p class="campaign-full-name">Coordinated Observations of Nebulae in the Central Molecular Zone Exploring gas Recycling and Transformation</p>
    <p class="lead">CONCERT 将银河系中心湍动、磁化的分子云环境同纤维、致密核、盘、流束和原恒星反馈等小尺度物理联系起来。</p>
    <div class="button-row">
      <a class="button" href="#publications">论文图谱</a>
      <a class="pill" href="https://ui.adsabs.harvard.edu/public-libraries/ZWd6s-SbQcWQBeDGrC3kiw" target="_blank" rel="noopener">ADS 文献库</a>
    </div>
  </div>
  <aside class="hero-panel" aria-label="观测计划范围">
    <div class="metric-grid">
      <div class="metric">
        <strong>5-500 GHz</strong>
        <span>射电到亚毫米多波段覆盖</span>
      </div>
      <div class="metric">
        <strong>100 AU-100 pc</strong>
        <span>从原恒星盘到分子云环境</span>
      </div>
      <div class="metric">
        <strong>4 个云</strong>
        <span>Sgr C、20 km/s 云、G0.253+0.016 和 clouds e/f</span>
      </div>
      <div class="metric">
        <strong>ALMA + VLA + JCMT</strong>
        <span>深度拼接、偏振和长基线观测</span>
      </div>
    </div>
  </aside>
</section>

<section id="logic" class="section">
  <div class="card">
    <p class="eyebrow">项目逻辑</p>
    <h2>为什么 CONCERT 要与大面积中央分子区巡天并行</h2>
    <p class="section-intro">CMZoom 和 ACES 等大型项目提供了中央分子区的广域图景。CONCERT 则选择少量关键分子云做更深、更精细的观测，让同一批目标可以从秒差距尺度的气体流动一路追踪到致密核和约 100 AU 的盘尺度结构。</p>
    <div class="flow" aria-label="尺度链条">
      <div class="flow-step">
        <h3>分子云</h3>
        <p>测量碎裂、外压限制、密度结构和云尺度源族群。</p>
      </div>
      <div class="flow-step">
        <h3>纤维</h3>
        <p>识别激波、吸收结构、HNCO 纤维以及向致密结构供给气体的隐藏储库。</p>
      </div>
      <div class="flow-step">
        <h3>致密核</h3>
        <p>连接核质量函数、外流、磁场和局部引力流动。</p>
      </div>
      <div class="flow-step">
        <h3>原恒星盘</h3>
        <p>解析大质量原恒星周围的旋转盘、包层、旋臂和流束。</p>
      </div>
    </div>
  </div>
</section>

<section class="section">
  <div class="card">
    <h2>工作假设</h2>
    <ul class="logic-list">
      <li><strong>中央分子区环境是极端的：</strong>高湍动、高压、强潮汐场、复杂视线结构和重要的磁场作用，使这些云看起来与银河系盘面的分子云非常不同。</li>
      <li><strong>小尺度物理可能仍然熟悉：</strong>当 CONCERT 到达致密核和盘尺度时，碎裂、吸积、旋转、外流和磁场调控等大质量恒星形成的基本环节仍然在运作。</li>
      <li><strong>关键是跨尺度连接：</strong>每篇论文回答一个尺度相关的问题，而整个观测计划把这些答案串成关于气体循环和转化的一幅图景。</li>
    </ul>
  </div>
</section>

<section id="programs" class="section">
  <p class="eyebrow">子项目</p>
  <h2>命名子项目以及它们之间的关系</h2>
  <p class="section-intro">CONCERT 使用音乐相关的名称来标记不同观测子项目。它们共同构成一条逻辑链：刻画气体、寻找隐藏气体库、测量磁场作用，并继续追踪气体如何进入盘和恒星。</p>
  <div class="grid">
    {% assign subcampaigns = site.data.subcampaigns %}
    {% assign publications = site.data.publications | sort: "order" %}
    {% for program in subcampaigns %}
    <article class="program-card program-{{ program.css_class }}">
      <span class="program-tag">{{ program.key }}</span>
      <h3>{{ program.title_zh }}</h3>
      <p class="program-full-name">{{ program.full_name_zh }}</p>
      <p>{{ program.summary_zh }}</p>
      <div class="program-publications">
        <p class="program-publications-title">相关论文</p>
        <ul>
          {% assign publication_count = 0 %}
          {% for paper in publications %}
            {% if paper.subcampaigns contains program.key %}
              {% assign publication_count = publication_count | plus: 1 %}
              <li><a href="#{{ paper.id }}">{{ paper.citation }}</a></li>
            {% endif %}
          {% endfor %}
          {% if publication_count == 0 %}
            <li class="muted">当前文献列表中暂无已发表论文；相关成果正在准备中。</li>
          {% endif %}
        </ul>
      </div>
    </article>
    {% endfor %}
  </div>
</section>

<section id="publications" class="section">
  <p class="eyebrow">论文图谱</p>
  <h2>这些论文如何相互连接</h2>
  <p class="section-intro">论文图谱按照每篇论文回答的问题来组织。它从定义中央分子区恒星形成问题的基础论文开始，然后沿着 CONCERT 序列，从云尺度结构一直推进到盘尺度吸积。</p>
  <div class="grid">
    {% assign publications = site.data.publications | sort: "order" %}
    {% for paper in publications %}
    <article class="publication-card {% if paper.subcampaigns.size > 0 %}program-{{ paper.subcampaigns.first | downcase }}{% else %}program-unassigned{% endif %}" id="{{ paper.id }}">
      <div class="publication-topline">
        <time>{{ paper.year }}</time>
        <span class="publication-phase">{% if paper.phase == 'Foundation' %}基础论文{% else %}CONCERT 序列{% endif %}</span>
      </div>
      <p class="publication-tags">
        <span class="scale">{{ paper.scale_zh | default: paper.scale }}</span>
        <span class="publication-program">{{ paper.program_zh | default: paper.program }}</span>
      </p>
      <a href="{{ paper.adsurl }}" target="_blank" rel="noopener">{{ paper.citation }}</a>
      <p class="publication-title">{{ paper.title }}</p>
      <p>{{ paper.summary_zh | default: paper.summary }}</p>
      <p class="publication-links">
        <a href="{{ paper.adsurl }}" target="_blank" rel="noopener">ADS</a>
        {% if paper.arxiv %}<a href="{{ paper.arxiv }}" target="_blank" rel="noopener">arXiv</a>{% endif %}
        {% if paper.doi %}<a href="{{ paper.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
      </p>
    </article>
    {% endfor %}
  </div>
  <div class="note">
    <p><strong>阅读顺序：</strong>2015-2019 年的论文建立了 20 km/s 云、中央分子区恒星形成率和早期大质量恒星形成普查等基础。CONCERT 序列进一步加入碎裂、外流、致密核统计、纤维、连续谱源族群、原星团组装、磁场作用以及盘/包层/流束系统。整个计划因此是一条相互连接的论证链，而不是彼此孤立的个例研究。</p>
  </div>
</section>

<section class="section">
  <p class="eyebrow">背景</p>
  <h2>CONCERT 如何补充大面积中央分子区巡天</h2>
  <div class="grid">
    <article class="program-card">
      <h3>ACES 和 CMZoom 提供地图</h3>
      <p>大面积巡天定义中央分子区环境，识别纤维和源族群，并提供比较样本。</p>
    </article>
    <article class="program-card">
      <h3>CONCERT 提供深度</h3>
      <p>对少量选定分子云进行深度、匹配分辨率、多波段观测，让物理条件、磁场和盘尺度结构可以在同一批目标中被统一研究。</p>
    </article>
    <article class="program-card">
      <h3>综合图景检验普适性</h3>
      <p>目前浮现的图景是：恒星形成的小尺度物理在中央分子区仍然有效，但极端环境改变了边界条件，使同样的物理过程呈现出不寻常的样貌。</p>
    </article>
  </div>
</section>

<section id="team" class="section">
  <div class="card">
    <p class="eyebrow">团队</p>
    <h2>核心团队与合作者</h2>
    <p class="section-intro">下面列出的团队成员包括当前 CONCERT 文献列表中出现的合作者，以及正在推进 CONCERT 论文的研究者。CONCERT 对所有感兴趣的研究者开放；如果你希望参与，请通过 <a href="mailto:{{ site.email }}">{{ site.email }}</a> 联系我。</p>
    <ul class="team-list">
      {% for person in site.data.team %}
      <li{% if person.et_al %} class="team-etal"{% endif %}>{{ person.name }}</li>
      {% endfor %}
    </ul>
  </div>
</section>
