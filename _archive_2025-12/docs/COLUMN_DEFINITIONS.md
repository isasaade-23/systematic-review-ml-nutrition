# ðŸ“Š COLUMN DEFINITIONS - DATA EXTRACTION TEMPLATE

**Total Columns**: 64 (Columns 1-30: Basic Data | Columns 31-61: PROBAST | Columns 62-64: Other)

---

## ðŸ“˜ SECTION 1: IDENTIFICATION (Columns 1-7)

### **Column 1: ID**
- **Format**: AA_XX (e.g., AA_04, AA_28)
- **Source**: Pre-filled from master list
- **Notes**: Unique identifier for each article

### **Column 2: Title**
- **Format**: Full article title
- **Source**: PDF title page
- **Notes**: Copy exact title, maintain capitalization

### **Column 3: First Author**
- **Format**: Surname only (e.g., "Kanz" not "Ahmad Fauzan Kanz")
- **Source**: PDF authorship
- **Notes**: If multiple first authors, use first listed

### **Column 4: Year**
- **Format**: YYYY (e.g., 2024)
- **Source**: Publication year from PDF or DOI
- **Notes**: Use publication year, not submission/acceptance year

### **Column 5: Country/Region**
- **Format**: Country name (e.g., "Indonesia", "Ethiopia", "Multi-country")
- **Source**: Methods section - study setting
- **Notes**: If multiple countries, write "Multi-country" or list main ones

### **Column 6: Journal**
- **Format**: Full journal name or conference name
- **Source**: PDF header/footer or citation
- **Example**: "BMC Public Health" or "2024 6th International Conference on Cybernetics and Intelligent System (ICORIS)"
- **Notes**: Include conference details if applicable

### **Column 7: DOI**
- **Format**: Full DOI (e.g., 10.1109/ICORIS63540.2024.10903911)
- **Source**: PDF header or first page
- **Notes**: If not available, write "Not available"

---

## ðŸ‘¥ SECTION 2: POPULATION (Columns 8-12)

### **Column 8: N (sample)**
- **Format**: Number (e.g., 121000, 5432)
- **Source**: Abstract, Methods (Participants), or Results
- **Notes**: Total sample size used in analysis (after exclusions)
- **Important**: Must be INDIVIDUAL children, not households

### **Column 9: Age (months)**
- **Format**: Range (e.g., "0-60", "6-59", "24-60")
- **Source**: Methods - Participants
- **Notes**: Convert years to months if needed (5 years = 60 months)
- **If unclear**: Write age range mentioned even if approximate

### **Column 10: Sex (%F)**
- **Format**: Percentage female (e.g., "52.3%", "48%")
- **Source**: Table 1 (baseline characteristics) or Methods
- **Notes**: If only counts given, calculate percentage
- **If not reported**: "Not reported" or "NR"

### **Column 11: Prevalence (%)**
- **Format**: Percentage (e.g., "23.4%", "15%")
- **Source**: Results - outcome prevalence in sample
- **Notes**: Prevalence of PRIMARY outcome being studied
- **Example**: If studying stunting, report % stunted
- **If not reported**: "Not reported"

### **Column 12: Setting (Rural/Urban)**
- **Format**: Rural / Urban / Mixed / Not specified
- **Source**: Methods - Study setting
- **Notes**: Be specific if mentioned; use "Mixed" if both; "Not specified" if unclear

---

## ðŸŽ¯ SECTION 3: OUTCOME & MODEL (Columns 13-18)

### **Column 13: Outcome** â­ DROPDOWN
- **Options**: Stunting / Wasting / Underweight / Overweight / Obesity / Multiple
- **Source**: Title, Abstract, Methods
- **Notes**: 
  - Choose "Multiple" if predicting >1 outcome
  - Must be SPECIFIC (not generic "malnutrition")
- **Examples**:
  - "Stunting" if predicting HAZ < -2 SD
  - "Multiple" if predicting stunting AND wasting

### **Column 14: Outcome Definition**
- **Format**: Text - exact definition with z-scores/cutoffs
- **Source**: Methods - Outcome definition
- **Examples**:
  - "Stunting defined as HAZ < -2 SD (WHO 2006)"
  - "Obesity defined as BMI > 95th percentile (CDC)"
  - "Nutritional status categorized into 4 types: normal, severely stunted, tall, stunted (no z-scores specified)"
- **Key info to capture**:
  - Which standard? (WHO, CDC, national)
  - Cutoff values (z-scores, percentiles)
  - Reference year if mentioned
- **If vague**: Write what they say + note "(no specific cutoffs mentioned)"

### **Column 15: Main Algorithm**
- **Format**: Algorithm name (e.g., "Random Forest", "XGBoost", "Neural Network")
- **Source**: Methods - ML model, Results
- **Notes**: The PRIMARY algorithm used for final model
- **If multiple tested**: Choose the one they highlight as best/final

### **Column 16: Other Algorithms**
- **Format**: Comma-separated list or "None tested"
- **Source**: Methods, Results - comparison with other algorithms
- **Examples**:
  - "Logistic Regression, SVM, Decision Tree"
  - "None tested - only Random Forest used"
- **Notes**: List algorithms used for COMPARISON, not feature selection methods

### **Column 17: Feature Selection**
- **Format**: Method name or "None mentioned"
- **Source**: Methods - Feature selection, Variable selection
- **Examples**:
  - "LASSO regularization"
  - "Recursive feature elimination"
  - "Based on literature review"
  - "Stepwise selection using p-values"
  - "None - all variables included"
- **Notes**: How did they choose which variables to include in final model?

### **Column 18: Handling Missing Data**
- **Format**: Method description or "Not mentioned"
- **Source**: Methods - Statistical analysis, Data preprocessing
- **Examples**:
  - "Multiple imputation using MICE"
  - "Listwise deletion"
  - "Mean imputation"
  - "Not mentioned"
- **Notes**: How did they handle missing values?

---

## ðŸ“ˆ SECTION 4: PERFORMANCE (Columns 19-25)

**Source for all**: Results - Tables showing model performance (prioritize tables over text)

### **Column 19: AUC**
- **Format**: Decimal (0.XX) or percentage (XX%)
- **Examples**: "0.89", "89%", "0.89 (95% CI: 0.85-0.93)"
- **Notes**: 
  - AUC-ROC or C-statistic
  - If multiple models, extract BEST one
  - "Not reported" if not provided

### **Column 20: Accuracy**
- **Format**: Decimal or percentage
- **Examples**: "0.9989", "99.89%", "95.3%"
- **Notes**: Overall accuracy on TEST set (not training)

### **Column 21: Precision**
- **Format**: Decimal or percentage
- **Examples**: "0.92", "92%"
- **Notes**: Also called PPV (Positive Predictive Value)

### **Column 22: Recall**
- **Format**: Decimal or percentage
- **Examples**: "0.88", "88%"
- **Notes**: Also called Sensitivity or True Positive Rate

### **Column 23: F1-Score**
- **Format**: Decimal
- **Examples**: "0.90", "90%"
- **Notes**: Harmonic mean of precision and recall

### **Column 24: PPV (%)**
- **Format**: Percentage
- **Notes**: Same as Precision (Column 21) - may be redundant
- **If same as Precision**: Just write "Same as Precision"

### **Column 25: Other Metrics**
- **Format**: Text - list other reported metrics
- **Examples**:
  - "Specificity: 94%, NPV: 96%"
  - "Brier score: 0.12, Calibration slope: 1.02"
  - "Kappa: 0.85"
- **Notes**: Capture ANY other performance metrics mentioned

---

## ðŸ” SECTION 5: PREDICTORS (Columns 26-27)

### **Column 26: Top 5 Predictors**
- **Format**: Numbered list (1-5)
- **Source**: Results - Feature importance, SHAP values, Tables
- **Example**:
  ```
  1. Height (cm)
  2. Age (months)
  3. Maternal education
  4. Household income
  5. Birth weight
  ```
- **Notes**: 
  - Extract from SHAP, feature importance plots, or text
  - If <5 predictors, list all available
  - List in order of importance if ranked

### **Column 27: All Variables Used**
- **Format**: Comma-separated list or "See Table X"
- **Source**: Methods - Variables, Tables
- **Examples**:
  - "Age, sex, height, weight, maternal education, income, breastfeeding duration"
  - "15 sociodemographic variables (see Table 1)"
- **Notes**: 
  - If too many (>15), can reference table
  - If few (â‰¤10), list all explicitly

---

## âœ… SECTION 6: VALIDATION (Columns 28-30)

### **Column 28: Validation Type** â­ DROPDOWN
- **Options**: Cross-validation / Hold-out / External / Mixed / None
- **Source**: Methods - Model validation
- **Definitions**:
  - **Cross-validation**: k-fold CV, LOOCV
  - **Hold-out**: Train/test split (same dataset)
  - **External**: Different dataset (temporal, geographic, or different cohort)
  - **Mixed**: Both internal + external
  - **None**: Only trained, no validation mentioned
- **Notes**: Choose PRIMARY validation method

### **Column 29: Validation Details**
- **Format**: Text description
- **Examples**:
  - "10-fold cross-validation"
  - "80/20 train-test split"
  - "External validation on 2019 cohort (original model from 2017 data)"
  - "5-fold CV with stratification"

### **Column 30: External Validation?** â­ DROPDOWN
- **Options**: Yes / No / NA
- **Definition**: 
  - **Yes**: Model tested on DIFFERENT dataset (different hospital, year, region, cohort)
  - **No**: Only internal validation (CV or train/test split from same data)
  - **NA**: No validation at all
- **Key distinction**: External = completely separate data source

---

## ðŸ“ NOTES SECTION (Columns 62-64)

### **Column 62: Interpretability (SHAP/LIME)**
- **Format**: Yes (with method) / No / Not mentioned
- **Examples**:
  - "Yes - SHAP values"
  - "Yes - LIME explanations"
  - "Yes - Feature importance from Random Forest"
  - "No interpretability techniques mentioned"

### **Column 63: Code Available?**
- **Format**: Yes (with link) / No / Not mentioned
- **Examples**:
  - "Yes - github.com/author/repo"
  - "Yes - available upon request"
  - "No"
  - "Not mentioned"

### **Column 64: General Notes**
- **Format**: Free text
- **Use for**:
  - Important caveats
  - Unusual methods
  - Data quality concerns
  - Anything that doesn't fit elsewhere
- **Example**: "Suspiciously high accuracy (99.89%) suggests possible data leakage or overfitting"

---

## ðŸŽ¯ EXTRACTION TIPS BY SECTION

### **Where to find each section in typical article:**

| Data needed | Where to look (in order of priority) |
|-------------|--------------------------------------|
| N, Age, Sex | Abstract â†’ Methods (Participants) â†’ Table 1 |
| Outcome definition | Methods (Outcome) â†’ Methods (Measures) |
| Algorithms | Abstract â†’ Methods (Analysis) â†’ Results |
| Performance | Results Tables â†’ Results text â†’ Abstract |
| Top predictors | Results (Feature importance) â†’ Figures â†’ Discussion |
| Validation | Methods (Statistical Analysis) â†’ Methods (Model Development) |
| Missing data | Methods (Statistical Analysis) â†’ Methods (Data) |

### **Common mistakes to avoid:**
- âŒ Confusing training accuracy with test accuracy (use TEST)
- âŒ Missing external validation when it's mentioned later
- âŒ Assuming WHO standards when not specified
- âŒ Copying wrong metric (e.g., sensitivity when looking for specificity)
- âŒ Not checking if sample is individuals vs households

---

## ðŸ”¢ QUICK REFERENCE: METRICS DEFINITIONS

| Metric | Formula | What it means |
|--------|---------|---------------|
| **Accuracy** | (TP+TN)/(TP+TN+FP+FN) | % of all predictions correct |
| **Precision/PPV** | TP/(TP+FP) | % of positive predictions that were correct |
| **Recall/Sensitivity** | TP/(TP+FN) | % of actual positives correctly identified |
| **Specificity** | TN/(TN+FP) | % of actual negatives correctly identified |
| **F1-Score** | 2Ã—(PrecisionÃ—Recall)/(Precision+Recall) | Harmonic mean of precision & recall |
| **AUC-ROC** | Area under ROC curve | Overall discrimination ability (0.5-1.0) |

*TP=True Positive, TN=True Negative, FP=False Positive, FN=False Negative*

---

**Last updated**: December 2024
**For**: Systematic Review - ML for Childhood Nutritional Outcomes
**Version**: 1.0
