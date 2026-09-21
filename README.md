# Machine learning for predicting childhood obesity and stunting: a systematic review

Data extraction, risk-of-bias assessment and derived results for the systematic review submitted
to the *Journal of Health, Population and Nutrition*.

The review covers studies published between 1 January 2020 and 5 August 2025 and reports
**37 included studies** contributing **39 eligible study-outcome combinations**.

## Data

| File | Content |
|---|---|
| `data/extraction/data_extraction_charms.xlsx` | Data extraction form following CHARMS. Sheet `Per Combination` holds one row per study x outcome x algorithm (241 rows); sheet `Codebook` documents the fields and the standardisation rules |
| `data/extraction/probastai_assessment.xlsx` | PROBAST+AI risk-of-bias assessment. Sheet `final_analysis` holds the consensus judgement per study and domain; sheet `consensus` shows each assessor's overall judgement and the agreed result |

Both files retain AA_10 (Kar 2021), so they list 38 studies. That study was excluded from the
review because it contributes no eligible study-outcome combination, which is why the review
reports 37.

## Code

| File | Content |
|---|---|
| `notebooks/01_demandas_revisores.ipynb` | Analysis of the corpus: units of analysis, descriptive synthesis, algorithms, performance by outcome, class imbalance and heterogeneity, model purpose and prediction horizon, PROBAST+AI by domain, verification against the source PDFs, updated search, and the adapted GRADE |
| `notebooks/02_tables_figures_update.ipynb` | Produces Figure 4 and writes the final figures and the formatted tables |

The notebooks are published as they were run, organised around the points raised in peer
review, and they refer to the author's working paths on Google Drive. Cell outputs were cleared.
They read the extraction files of `data/extraction/` and write the tables of `outputs/tables/`
under the same names used in this repository.

## Derived results

`outputs/tables/` holds the tables behind the numbers reported in the article.

| File | Content |
|---|---|
| `table1_study_characteristics.csv` | Table 1: characteristics and performance of the 39 eligible study-outcome combinations |
| `table2_performance_by_outcome.csv` | Table 2: performance and heterogeneity by nutritional outcome |
| `table3_grade_certainty.csv` | Table 3: certainty of the evidence by outcome (adapted GRADE) |
| `grade_certainty_by_domain.csv` | Domain-by-domain GRADE judgements behind Table 3 |
| `supplement_records_by_database.csv` | Records retrieved by each database, original and updated search |
| `supplement_data_verification.csv` | Field-by-field verification of the extraction against the source articles |
| `supplement_probastai_domains.csv` | PROBAST+AI judgements by domain, for development and for evaluation |
| `supplement_ineligible_outcomes.csv` | Study-outcome combinations extracted and then excluded as ineligible outcomes |
| `corpus_overview.csv` | Country, data source, sample size, age range and setting per study |
| `algorithm_families.csv` | Frequency of each algorithm family, by row, by best model and by study |
| `class_imbalance.csv` | Outcome prevalence and reported imbalance handling per combination |
| `performance_by_validation.csv` | Median performance by outcome family and type of validation |
| `heterogeneity.csv` | Spread of sample size, prevalence, country and validation type by outcome |
| `leakage_classification.csv` | Model purpose and outcome-dimension anthropometry per combination |
| `figure4_predictors.csv`, `figure4_predictors_panel_a.csv`, `figure4_predictors_panel_b.csv` | Counts behind Figure 4 |
| `verification_verdicts_by_block.csv` | Verification verdicts by block of extracted fields |

`outputs/figures/` holds the four figures of the article and the three supplementary figures.

## Scope of this repository

This repository carries the extraction files, the consensus risk-of-bias assessment and the
derived tables and figures. Working material of the review process, including per-assessor
worksheets and internal reconciliation files, is not published here.

## Citation

Silva IV, Assis-Souza LG, Soares MQ, Hallal PC, Chiavegatto Filho ADP. Machine learning for
predicting childhood obesity and stunting: a systematic review. Submitted.
