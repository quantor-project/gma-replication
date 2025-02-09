# Evert et al. (2025): On the replicability of geometric multivariate analysis

## Introduction

This repository contains the complete reproduction materials for 

[!IMPORTANT]
Evert, Stephanie; Frenken, Florian; Neumann, Stella; Schneider, Gerold (to appear).
How stable are multivariate findings about register variation across varieties of English? On the replicability of geometric multivariate analysis.
To appear in _ICAME Journal_.

This paper reports a reproduction and replication of the geometric multivariate analysis (GMA) study of [Neumannn & Evert (2021)](https://www.stephanie-evert.de/PUB/NeumannEvert2021/), which investigated register variation in three varieties of English based on the corresponding three components of the International Corpus of English (ICE). We refer to their data set as ICE3 in order to distinguish it from an extended data set covering six additional components (ICE9).

Our first research question is whether the original results can reliably be **reproduced**:

- **RQ 1a:** Reproduction of Neumann & Evert (2021) with the original R scripts provided by the authors, but using an independently created new version of the ICE3 data set.
- **RQ 1b:** Reproduction of the results with our own script using the new R package [`gmatools`](https://github.com/schtepf/GMA/tree/main/pkg/gmatools).

We then investigate whether the observations also **replicate** on an extended data set (ICE9). We address two increasingly challenging research questions:

- **RQ 2:** Replication of the observations and conclusions of Neumann & Evert (2021) if data points from the additional six language varieties are added (to the same multivariate space).
- **RQ 3:** Full replication of Neumann & Evert (2021) on the extended ICE9 data set (with a completely new multivariate analysis).

## File overview

`prepare_data.Rmd`: Pre-processing of the data set, slightly adapted from the reproduction materials of Neumann & Evert (2021) to take the six additional ICE components into account. This notebook re-creates `ice_preprocessed.rda` from the input files and generates some illustrative plots in directory `pdf_journal/`.

- `ice_features.tsv`, `ice_metadata.csv`, `text_categories.tsv`: Original data files read by the pre-processing script.
- `ice_preprocessed.rda`: Pre-processed data set so analysis scripts can directly be run from the repository.

`repro_neumann_evert.Rmd`: Reproduction of Neumann & Evert (2021) using a slightly modified version of their analysis script (from the reproduction materials) **[RQ 1a]**. The notebook was adjusted to reduce the ICE9 data set to the ICE3 components; 3D plots and interactive visualisations were removed as they are not part of our replication study. PDF plots are saved to directory `pdf_repro/`.

- `multivar_utils.R`: Library of analysis function included in the reproduction materials (unmodified from the original except for a minor bugfix).

`gma_replication.Rmd`: Reproduction and replication of Neumann & Evert (2021) using our own analysis code based on the [`gmatools`](https://github.com/schtepf/GMA/tree/main/pkg/gmatools) package **[RQ 1b, RQ 2, RQ 3]**. PDF plots are saved to directory `pdf_journal/`.

## Prerequisites

The following R packages are needed in order to run the notebook for the main reproduction/replication study:

- `gmatools`
- `data.table`
- `ggplot2`
- `corpora`

These additional packages are required for the the pre-processing script (mostly for overview plots and tables).

- `colorspace`
- `ggExtra`
- `grid`
- `kableExtra`
- `seriation`

The original analysis script of Neumann & Evert (2021) as included here needs some further packages (in addition to all packages listed above):

- `DT`
- `e1071`
- `gplots`
- `magrittr`
- `MASS`

## Licence

The software and all other materials in this repository are distributed under the terms of the GNU General Public License Version 3, June 2007.
The terms of the license are in a file called LICENSE in this directory.
