# CONCERT Website

This repository hosts the GitHub Pages site for the CONCERT campaign:

**Coordinated Observations of Nebulae in the Central Molecular Zone Exploring gas Recycling and Transformation**

The public site is built with Jekyll and published at:

https://CMZconcert.github.io

## Local Preview

```bash
bundle install
bundle exec jekyll serve
```

If the local Ruby/Jekyll setup is unavailable, the source can still be inspected as a mostly static landing page in `index.md`, with shared layout in `_includes/default.html` and styling in `public/css/style.css`. On macOS, `bundle install` may require the Xcode Command Line Tools because Jekyll installs native Ruby extensions.

## Content Focus

The homepage is organized around the logic of the campaign:

- why a deep small-sample campaign complements large CMZ surveys;
- how CONCERT connects clouds, filaments, cores, and disks;
- how QUARTET, MAZURKA, POLKA, BALLAD, DUET, and CHORUS fit together;
- how the campaign publications build a linked argument about star formation in the CMZ.

The ADS publication library is:

https://ui.adsabs.harvard.edu/public-libraries/ZWd6s-SbQcWQBeDGrC3kiw

## Adding Publications

Publication cards are generated from `_data/publications.yml`. To add a new CONCERT result:

1. Copy an existing item in `_data/publications.yml`.
2. Update `id`, `bibcode`, `year`, `citation`, `title`, `scale`, `program`, `summary`, `image`, `image_alt`, and the ADS/arXiv/DOI links.
3. Set `order` to control where the paper appears in the campaign narrative.
4. Add the relevant named subcampaign under `subcampaigns`, for example `DUET`, `POLKA`, `BALLAD`, or `CHORUS`.

Named subcampaign cards are generated from `_data/subcampaigns.yml`. Optional fields such as `logo`, `visualization_url`, and bilingual labels can be added there without changing the page templates.

## Bilingual Pages And Team List

- The English homepage is `index.md`.
- The Chinese homepage is `zh.md` and is published at `/zh/`.
- The language switch is in `_includes/default.html`.
- The visible team list is generated from `_data/team.yml`; include publication-list collaborators and active CONCERT paper contributors, and leave the final `et al.` entry.
- Subcampaign colors and Chinese labels live in `_data/subcampaigns.yml` and `public/css/style.css`.
- The CMZ overview image lives at `public/img/cmz-overview.png`; publication thumbnails live in `public/img/papers/`; subcampaign logos live in `public/img/`.
