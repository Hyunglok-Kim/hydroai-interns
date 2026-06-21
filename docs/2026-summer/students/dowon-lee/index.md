# Dowon Lee

!!! abstract "Project — Soil Moisture Data Intercomparison"
    How well do today's satellite soil moisture products agree with each other
    and with ground truth? Benchmarking **SMAP**, **SMOS**, **ASCAT**,
    **ESA CCI**, and **ERA5-Land** against **ISMN** in-situ networks.

    **Period:** Jun 22 – Aug 21, 2026 (9 weeks) · **Mentor:** Hyunglok Kim

## :material-file-document-edit-outline: My weekly log (Google Docs)

[:material-google-drive: **Open my weekly log →**](https://docs.google.com/document/d/REPLACE_WITH_DOWON_DOC_ID/edit){ .md-button .md-button--primary }

> The PI leaves comments directly inside the Doc. Use Google Docs'
> **Suggesting** mode or `@mention` for questions.

## :material-target: Research question

> _Refined in week 1 — placeholder below._

Where and when do current satellite soil moisture products agree, and
where do they systematically diverge? Are the divergences explained by
land cover, climate regime, or topography?

## :material-format-list-checks: Plan

1. **Literature scoping (W1)** — read Gruber et al. triple collocation work,
   Dorigo et al. ESA CCI papers, recent ISMN benchmark studies.
2. **Data assembly (W2–3)** — pull SMAP L3, SMOS L3, ASCAT, ESA CCI combined,
   ERA5-Land; pull ISMN stations with QC flags.
3. **Common grid (W3)** — regrid / collocate to ISMN station pixels;
   sanity-check time coverage.
4. **Metrics (W4–5)** — bias, ubRMSD, anomaly correlation; per-network and
   per-biome breakdowns; triple collocation where applicable.
5. **Driver analysis (W6)** — what predicts disagreement? Vegetation density,
   topographic complexity, RFI, freeze/thaw masking.
6. **Talk & writeup (W7–9)** — clean figures, one-page abstract, 15-min talk.

## :material-database: Data

| Dataset | What | Period | Resolution |
|---------|------|--------|------------|
| SMAP L3 | Surface soil moisture | 2015– | 36 km |
| SMOS L3 | Surface soil moisture | 2010– | 25 km |
| ASCAT | Surface soil moisture | 2007– | 12.5 km |
| ESA CCI v8+ | Combined / active / passive | 1978– | 0.25° |
| ERA5-Land | Reanalysis SM | 1950– | 0.1° |
| ISMN | In-situ network ensemble | varies | point |

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
