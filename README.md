# Rectal Microbiome of Neonates with Bloodstream Infection in Mwanza, Tanzania

Code repository for:

**Gut microbiome and causative pathogens in neonatal bloodstream infection: a case-control study in Mwanza, Tanzania**

Msanga DR, Aldejohann AM, Kampmeier S, Härtel C, Mshana SE, Kurzai O, Herz M.

## Overview

This repository contains the R code used for the statistical analyses and visualizations presented in the manuscript. The study compares the rectal microbiome (16S rRNA gene, V3–V4) of neonates with culture-confirmed bloodstream infection (BSI) and healthy neonates at Bugando Medical Centre, Mwanza, Tanzania, and relates it to the pathogen isolated from blood.

The complete downstream analysis is contained in the R notebook `analysis.ipynb`. Sequencing reads were processed upstream with nf-core/ampliseq v2.18.0 (truncation lengths 264 bp forward and 266 bp reverse, taxonomy assigned against SILVA 138.1); the software versions of this run are listed in `nf_core_ampliseq_software_mqc_versions.yml`. In the code, the group labels `sepsis` and `control` stand for neonates with BSI and healthy neonates.

## Analyses

- Harmonization of clinical metadata and descriptive statistics
- Quality control of sequencing depth, taxonomic classification and the mock community (ZymoBIOMICS D6300)
- Genus-level community composition per neonate
- Alpha diversity (Shannon, Simpson) and Bray–Curtis dissimilarity estimated with DivNet, with tests for group differences (`betta`, `testBetaDiversity`)
- Differential abundance testing with radEmu (primary model and model adjusted for antibiotic exposure during pregnancy)
- Permutation tests for concordance between the blood culture genus and the rectal microbiota, including sensitivity analyses and comparison between pathogen strata
- Comparison of culture-based rectal screening with blood culture and sequencing results

## Requirements

R (4.4.1) with the following packages:

`phyloseq`, `DivNet`, `breakaway`, `radEmu`, `vegan`, `tidyverse`, `readxl`, `janitor`, `ape`, `scales`, `patchwork`, `RColorBrewer`, `writexl`, `conflicted`

The analyses were run with phyloseq 1.48.0, DivNet 0.4.1, breakaway 4.8.5, radEmu 2.2.1.0 and vegan 2.7-2. `DivNet`, `breakaway` and `radEmu` are installed from GitHub (`adw96/DivNet`, `adw96/breakaway`, `statdivlab/radEmu`). The notebook requires Jupyter with the R kernel (IRkernel).
## Data availability

Raw sequencing reads are available from the European Nucleotide Archive under project accession PRJEB127033. Clinical metadata cannot be shared publicly because they contain patient-level information. Requests for data access can be directed to the corresponding author and are subject to approval by the responsible ethics committees. The notebook cannot be run without these inputs.

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
