# Project Overview

This repository contains two complementary projects that analyze factors influencing Alzheimer's disease progression:

- **Project 1 (R)**: Initial exploratory analysis focusing on the relationship between socioeconomic status, education, and clinical dementia ratings
- **Project 2 (Python)**: Extended analysis with survival analysis techniques to understand cognitive decline progression

Note: This dataset was found on Kaggle. See Acknowledgements below for citation.

## Background

Alzheimer's disease is a type of dementia that affects memory, thinking, and behavior. With no current cure available, understanding progression indicators is crucial for early intervention and prevention strategies. This research investigates how socioeconomic factors and education levels may influence disease progression.

## Repository Structure

```
├── Project1.pdf                 # R-based analysis report
├── Project2.pdf                 # Python-based analysis with survival analysis
├── data/
│   ├── oasis_cross_sectional.csv
│   └── oasis_longitudinal.csv
├── scripts/
│   ├── project1_analysis.R
│   └── project2_analysis.py
└── README.md
```

## Research Hypotheses

### Project 1
Higher SES and Education levels are associated with lower CDR (Clinical Dementia Rating) scores, indicating slower progression of Alzheimer's disease.

### Project 2
Higher levels of Education and SES are associated with slower progression of cognitive decline in individuals with Alzheimer's disease.

## Dataset Description

### Variables
- **Subject ID**: Unique participant identifier
- **M/F**: Gender (Male/Female)
- **Hand**: Dominant hand (right/left)
- **Age**: Participant age
- **Educ**: Education level
- **SES**: Socioeconomic status
- **MMSE**: Mini-Mental State Examination score
- **CDR**: Clinical Dementia Rating
- **eTIV**: Estimated Total Intracranial Volume
- **nWBV**: Normalized Whole Brain Volume
- **ASF**: Atlas Scaling Factor

### Additional Variables (Longitudinal Data)
- **Group**: Dementia status (Nondemented/Demented/Converted)
- **Visit**: Visit number for longitudinal tracking
- **MR Delay**: Time between visits

## Technologies Used

### Project 1 (R)
- **Libraries**: dplyr, ggplot2, lme4, lmerTest, tidyverse
- **Methods**: 
  - Linear regression modeling
  - ANOVA analysis
  - Mixed-effects modeling for longitudinal data
  - Residual analysis and model diagnostics

### Project 2 (Python)
- **Libraries**: pandas, numpy, matplotlib, seaborn, scikit-learn, statsmodels, lifelines, sksurv
- **Methods**:
  - Linear regression with interaction terms
  - Variance Inflation Factor (VIF) analysis
  - Kaplan-Meier survival analysis
  - Cox Proportional Hazards modeling
  - Correlation analysis and visualization

## Key Findings

### Cross-Sectional Analysis
- MMSE scores show moderate negative correlation with age (-0.31) and SES (-0.26)
- Education shows positive correlation with MMSE (0.30)
- Age has significant negative effect on cognitive performance (p = 0.041)

### Survival Analysis
- **Education**: Significant protective factor against cognitive decline (coefficient: -0.18, p < 0.05)
- **Age**: Paradoxical negative association with cognitive decline risk
- **SES**: No statistically significant impact on cognitive decline progression
- **Model Performance**: Concordance index of 0.69 indicates good predictive ability

### Longitudinal Modeling
- Demented group shows significantly lower MMSE scores (-3.57, p < 0.001)
- Visit number negatively associated with MMSE (-0.37, p < 0.01)
- Brain volume (nWBV) positively associated with cognitive performance

## Statistical Methods

### Project 1
1. **Data Preprocessing**: Outlier removal using 3-standard deviation filtering
2. **Linear Modeling**: OLS regression predicting CDR scores
3. **ANOVA**: Analysis of variance accounting for age interactions
4. **Mixed-Effects Modeling**: Longitudinal analysis with random intercepts

### Project 2
1. **Multicollinearity Assessment**: VIF analysis revealing high collinearity for age (VIF: 18.88)
2. **Interaction Analysis**: Age × SES interaction effects
3. **Survival Analysis**: 
   - Kaplan-Meier estimation for cognitive decline
   - Cox Proportional Hazards modeling
4. **Model Validation**: Residual analysis and diagnostic plotting

## Prerequisites

### For Project 1 (R)
```r
install.packages(c("dplyr", "tidyr", "tidyverse", "ggplot2", "lme4", "lmerTest"))
```

### For Project 2 (Python)
```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels lifelines scikit-survival
```

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/alzheimers-analysis.git
   cd alzheimers-analysis
   ```

2. **Download the OASIS dataset**
   - Cross-sectional data: `oasis_cross_sectional.csv`
   - Longitudinal data: `oasis_longitudinal.csv`

3. **Run Project 1 (R)**
   ```r
   source("scripts/project1_analysis.R")
   ```

4. **Run Project 2 (Python)**
   ```bash
   python scripts/project2_analysis.py
   ```

## Visualizations

Both projects include comprehensive visualizations:
- Age distribution histograms
- Correlation heatmaps
- Survival curves (Kaplan-Meier)
- Residual diagnostic plots
- Longitudinal trend analysis
- Cox regression coefficient plots

## Limitations

- Sample size of ~300 patients may be insufficient for definitive conclusions
- Cross-sectional data limits causal inference
- Confounding variables and genetic factors not fully controlled
- Visit intervals in longitudinal data are irregular
- High multicollinearity detected in some models

## Recommended Future Work

- Expand sample size for more robust statistical power
- Include genetic markers and biomarkers
- Implement machine learning approaches for prediction
- Conduct longer-term longitudinal follow-up studies
- Investigate interaction effects between multiple socioeconomic factors

## References

Boysen, J. (2020). MRI and Alzheimer's Disease. Kaggle. 
https://www.kaggle.com/datasets/jboysen/mri-and-alzheimers?resource=download

*This research contributes to the understanding of Alzheimer's disease progression and highlights the importance of socioeconomic factors in cognitive health outcomes.*
