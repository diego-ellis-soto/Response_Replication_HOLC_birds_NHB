
#### This repository accompanies our response to the independent replication of Ellis-Soto et al. (2023, Nature Human Behaviour) by Bulla & Mikula (2026) and provides reproducible code to recreate and clarify key analyses.

The scripts reproduce original figures, examine temporal aggregation choices (cumulative vs annual sampling density), and provide updated workflows to support reproducible biodiversity sampling analyses using current data infrastructures.

We additionally provide reimplementations of temporal aggregation workflows and extended pipelines to facilitate transparent replication and future extensions as biodiversity and geospatial datasets continue to evolve.

[1] 01_Figure_1_Map_Replic_HOLC_NHB.qmd: Recreates Figure 1 from the original paper, generating national and city-level HOLC maps and sampling-density inset barplots for New Haven, Los Angeles, and Detroit.

[2] 02_Figure_4_dplyr_based_cum_sum.Rmd: Code to calculate cumulative sampling density using a dplyr-only workflow (avoiding plyr/dplyr namespace conflicts) (Original Figure 4).

[3] 03_Annual_sampling_dens_Figure4.Rmd: Reproduces Figure 4 using annual (non-cumulative) sampling density by HOLC grade and generates updated temporal sampling density plots.

[4] 04_Calculate_ratios_2000_2020.Rmd: Computes the A/D sampling density ratio and percent change between 2000 and 2020 using both tidyverse and data.table pipelines, documenting the matched-area and mixed-area calculations.

[5] 05_Suppl_Fig2.Rmd: Reproduces Supplementary Figure 2 from the original paper.

[6] 06_GBIF_DB_hexbin_temp_trends_post_NHB_HOLC_MS.Rmd: Extends the HOLC–GBIF sampling density analysis beyond 2020 using cloud-hosted H3-hex indexed GBIF data to explore post-study temporal trends.

## Reproducibility notes

- R version and package versions are documented via `sessionInfo()` included at the end of each R Markdown/Quarto file in this repository.
- Rendered `.html` and `.pdf` outputs containing these session details are also provided for transparency and archival reproducibility.
  - GBIF data accessed via scripted workflows described in the corresponding documents.
  
## Key packages include:

- Data manipulation: tidyverse (dplyr, tidyr, readr), glue
- Visualization: ggplot2, patchwork, ggthemes, ggpubr, ggspatial
- Spatial analysis and mapping: sf, tidycensus, mapdata, usmap
- Modeling and statistical summaries: mgcv, sjPlot
- Data access infrastructure: duckdbfs