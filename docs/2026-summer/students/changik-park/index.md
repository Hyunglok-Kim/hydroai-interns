# Changik Park

!!! abstract "Project — Brown Ocean Effect"
    How and when do wet land surfaces sustain — or even re-intensify —
    tropical cyclones after landfall? Built on **SMAP** soil moisture,
    **IBTrACS** storm tracks, and **ERA5** reanalysis.

    **Period:** Jun 22 – Aug 21, 2026 (9 weeks) · **Mentor:** Hyunglok Kim

## :material-file-document-edit-outline: My weekly log (Google Docs)

[:material-google-drive: **Open my weekly log →**](https://docs.google.com/document/d/REPLACE_WITH_CHANGIK_DOC_ID/edit){ .md-button .md-button--primary }

> The PI leaves comments directly inside the Doc. Use Google Docs'
> **Suggesting** mode or `@mention` for questions.

## :material-target: Research question

> _Refined in week 1 — placeholder below._

Under what land-surface and atmospheric conditions does the brown ocean
effect occur over the continental US, and can we predict its likelihood
from pre-landfall soil moisture state?

## :material-format-list-checks: Plan

1. **Literature scoping (W1)** — read foundational Andersen & Shepherd papers,
   recent re-analyses, and any ML approaches to the problem.
2. **Data assembly (W2–3)** — co-locate SMAP L3/L4 soil moisture, IBTrACS tracks,
   ERA5 boundary-layer and moisture fields along each storm's path.
3. **Event catalog (W3–4)** — define a "brown ocean candidate" criterion;
   build a clean catalog of post-landfall storms 2015–present.
4. **Analysis (W5–6)** — composite analysis + simple ML classifier
   (logistic / gradient boosting) for occurrence likelihood.
5. **Validation (W6–7)** — leave-one-storm-out CV, sensitivity to SMAP
   product (L3 vs L4) and ERA5 vertical levels.
6. **Talk & writeup (W8–9)** — figures, slides, 15-min final.

## :material-database: Data

| Dataset | What | Used for |
|---------|------|----------|
| SMAP L3/L4 | Surface & root-zone soil moisture | Pre-landfall land state |
| IBTrACS | Best-track TC positions, intensity | Storm trajectories |
| ERA5 | PBL height, MSE, TCWV, fluxes | Atmospheric environment |
| MERIT / SoilGrids | Topography, soil texture | Conditioning variables |

## :material-clipboard-text-clock: Weekly progress

| # | Dates | Theme | Status |
|---|-------|-------|--------|
| 1 | Jun 22 – Jun 26 | Literature scoping + kickoff talk | :material-circle-outline: not started |
| 2 | Jun 29 – Jul 03 | Data acquisition | :material-circle-outline: |
| 3 | Jul 06 – Jul 10 | Pipeline v1 | :material-circle-outline: |
| 4 | Jul 13 – Jul 17 | Mid-checkpoint talk | :material-circle-outline: |
| 5 | Jul 20 – Jul 24 | Iterate | :material-circle-outline: |
| 6 | Jul 27 – Jul 31 | Validation | :material-circle-outline: |
| 7 | Aug 03 – Aug 07 | Story & figures | :material-circle-outline: |
| 8 | Aug 10 – Aug 14 | Dress rehearsal | :material-circle-outline: |
| 9 | Aug 17 – Aug 21 | **Final talk (Aug 21)** | :material-circle-outline: |

## :material-bookshelf: Reference pipeline notes

Earlier scoping notes from the PI live in the project root at
`brown_ocean_effect/brown_ocean_pipeline.md` (outside the site folder).
