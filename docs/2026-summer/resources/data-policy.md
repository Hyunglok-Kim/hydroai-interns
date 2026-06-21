# Data & compute policy

A few simple rules so the repo stays usable and nothing leaks.

## :material-folder-cog: Where big files go — **not in the repo**

| Size | Where it goes |
|------|---------------|
| < 1 MB (small CSV, JSON, config) | Commit to repo |
| 1–25 MB (final figures, sample data) | Commit, but think first |
| > 25 MB (raw satellite tiles, NetCDF stacks) | **Lab storage**, not git |

!!! danger "Never commit"
    - Raw downloaded satellite granules (HDF5, NetCDF, GeoTIFF stacks)
    - API keys, passwords, `.env` files
    - Anything from a `Downloads/` or `data/raw/` folder

Add to `.gitignore` instead. When in doubt, ask before `git add`.

## :material-server-network: Where raw data lives

> _PI to fill in once the cluster paths are decided._

- **Lab NAS** — `/Volumes/HydroAI/data/...`
- **University HPC** — `/scratch/hkim/interns2026/...`
- **Cloud bucket** — `s3://hydroai-interns-2026/` _(read-only)_

Mount or symlink these into your project; do **not** copy into the repo.

## :material-format-quote-close: Citing datasets

Every dataset you use in a figure or claim must be cited. Put citations in
your project's `references.md`. Use the dataset's *official citation* —
don't invent one.

| Dataset | Cite as |
|---------|---------|
| SMAP L3 SM | Entekhabi et al., 2010, *Proc. IEEE*; product DOI from NSIDC |
| SMOS L3 | Kerr et al., 2010, *Proc. IEEE*; product DOI from CATDS |
| ESA CCI SM | Dorigo et al., 2017, *RSE*; Gruber et al., 2019, *ESSD* |
| ERA5 / ERA5-Land | Hersbach et al., 2020, *QJRMS*; Muñoz-Sabater et al., 2021, *ESSD* |
| ISMN | Dorigo et al., 2021, *VZJ* |
| IBTrACS | Knapp et al., 2010, *BAMS* |

## :material-recycle: Reproducibility minimums

- Every analysis script starts from raw data and runs end-to-end.
- Random seeds set explicitly.
- A `requirements.txt` or `environment.yml` lives next to your code.
- Your final figures should be regenerable by *someone else* running one command.
