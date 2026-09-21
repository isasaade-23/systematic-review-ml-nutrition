# Machine learning for predicting childhood obesity and stunting: a systematic review

Data processing code, extraction templates and derived tables for the systematic review
submitted to the *Journal of Health, Population and Nutrition*.

Corpus: 37 included studies, 39 eligible study-outcome combinations, published between
1 January 2020 and 5 August 2025.

## Contents

| Path | Content |
|---|---|
| `notebooks/01_demandas_revisores.ipynb` | Analysis of the corpus: descriptive synthesis, performance by outcome, predictor types, PRISMA counts, GRADE, updated search |
| `notebooks/02_tables_figures_update.ipynb` | Code that produces the manuscript tables and figures |
| `data/extraction/extracao_artigo1_v7.xlsx` | Data extraction form (CHARMS), sheet `Per Combination`: one row per study x outcome x algorithm |
| `data/extraction/PROBASTAI_final_20260817.xlsx` | PROBAST+AI risk-of-bias assessment in duplicate, sheet `final_analise` holds the consensus |
| `outputs/tables/` | Derived tables (CSV) behind the numbers reported in the manuscript |
| `outputs/figures/` | Figures as produced by the notebooks |
| `_archive_2025-12/` | Material of the original January submission, kept for provenance; superseded by the files above |

## Reproducing

The notebooks run on Google Colab against the extraction files in `data/extraction/`.
Only `openpyxl` is installed on top of the Colab base image; `kaleido` is pinned to `0.2.1`
for the world map panel.

## Citation

Silva IV, Assis-Souza LG, Soares MQ, Hallal PC, Chiavegatto Filho ADP. Machine learning for
predicting childhood obesity and stunting: a systematic review. Submitted.
