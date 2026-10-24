# Non-Linear Association Between Hemoglobin Levels and Gestational Age in Peruvian Pregnant Women

**National Cross-Sectional & Longitudinal Epidemiological Study (SIEN – INS/CENAN, 2016–2022)**

## Executive Summary

Gestational anemia is a critical public health challenge associated with low birth weight, preterm delivery, and maternal mortality. Standard World Health Organization (WHO) reference thresholds are primarily derived from European and North American populations and do not fully capture the physiological adaptations driven by extreme geographical variability and high-altitude hypoxia across Peru's coastal, Andean, and Amazonian regions.

This study evaluates the non-linear trajectory of maternal hemoglobin levels across gestational age and quantifies the effect of residential altitude and maternal anthropometric factors using nationwide surveillance records from Peru's **Nutritional Status Information System (SIEN – INS/CENAN)**.

## Key Quantitative Findings

* **Physiological Hemodilution Across Gestation:** In both bivariate and multivariate linear regression models, maternal hemoglobin decreases by **-0.0325 g/dL per week of gestational age** ($p < 0.001$), reflecting physiological plasma volume expansion during pregnancy.
* **High-Altitude Hypoxia Adaptation:** Residential altitude exerts a statistically significant positive effect on maternal hemoglobin (**+0.000617 g/dL per meter of elevation**, $p < 0.001$). Accounting for altitude and maternal covariates explains **$R^2 = 38.15\%$** of total hemoglobin variance.
* **Elevated Prevalence in Andean Regions ($\ge 2,500\text{ m}$):** Overall gestational anemia prevalence reaches **30.0%** in high-altitude settlements ($\ge 2,500\text{ m.a.s.l.}$), with severe anemia reaching **0.6%** in these high-risk zones.
* **Maternal Nutritional Status:** Maternal weight is positively associated with hemoglobin concentration (**+0.01375 g/dL per kg**, $p < 0.001$), and maternal age shows a modest positive association (**+0.0052 g/dL per year**), whereas maternal height shows no statistically significant effect ($p = 0.955$).

## Multivariate Regression Model Summary

| Predictor Variable | Estimated Effect on Hemoglobin | Statistical & Clinical Interpretation |
| :--- | :---: | :--- |
| **Gestational Age (weeks)** | -0.0325 g/dL per week | Captures progressive physiological hemodilution across trimesters |
| **Residential Altitude (meters)** | +0.000617 g/dL per meter | Reflects erythropoietic adaptation to chronic high-altitude hypoxia |
| **Maternal Weight (kg)** | +0.01375 g/dL per kg | Demonstrates the protective effect of maternal nutritional reserves |
| **Maternal Age (years)** | +0.0052 g/dL per year | Indicates a marginal positive increase with maternal age |
| **Maternal Height (cm)** | Not significant ($p = 0.955$) | No statistically significant independent effect on hemoglobin |

*Model fit: Multiple linear regression adjusted for gestational age, residential altitude, maternal weight, age, and height ($R^2 = 38.15\%$, 2022 complete-case national cohort).*

## Visual Highlights

### 1. Non-Linear Hemoglobin Percentile Curves Across Gestational Age (LOESS)
Non-parametric Locally Estimated Scatterplot Smoothing (`LOESS`, $\text{span} = 0.30$) across empirical percentiles ($P_{1}$ to $P_{99}$) reveals the non-linear physiological drop during the second trimester and identifies high-risk clinical trajectories in the lowest percentiles ($P_{1}$ and $P_{5}$).



### 2. Linear Regression of Hemoglobin by Pregnancy Trimester
Stratified linear trends across the 1st ($\le 12$ weeks), 2nd ($13\text{–}24$ weeks), and 3rd ($> 24$ weeks) trimesters demonstrate the sharpest decline during the প্রথম and second trimesters followed by stabilization in late pregnancy.



### 3. Geospatial Distribution of Gestational Anemia Across Peruvian Departments (2022)
Choropleth mapping combining SIEN epidemiological records with official INEI departmental boundary shapefiles highlights the geographical concentration of anemia across highland regions.



## Tech Stack & Statistical Methods

* **Language & Reporting:** R, RStudio, Quarto (`.qmd`)
* **Data Wrangling & Manipulation:** `tidyverse`, `dplyr`, `readr`, `tidyr`, `stringr`, `haven`
* **Statistical Modeling:** Ordinary Least Squares (OLS) Simple & Multiple Linear Regression (`stats::lm`), Non-parametric Local Regression (`LOESS` quantile smoothing)
* **Geospatial & Visual Analytics:** `sf` (Simple Features for spatial vector data), `ggplot2`, `RColorBrewer`

## Repository Structure

```text
peru-hemoglobin-study/
├── 01_analisis_nacional_anemia.qmd   # Multi-year data ingestion & harmonization pipeline (2016–2023)
├── Proyecto_final_bio.qmd            # Statistical modeling, spatial epidemiology & percentile curves
├── figures/                          # High-resolution visualizations exported from the study
│   ├── niveles_hemoglobina.png
│   ├── regresion_trimestres.png
│   └── mapa_prevalencia_peru.png
├── .gitignore                        # Excludes raw large CSV files and local R session artifacts
├── licence.txt                       # MIT License
└── README.md                         # Project documentation and executive report
```

## How to Reproduce the Analysis

1. **Clone the repository:**
   ```bash
   git clone https://github.com/arone-damian/peru-hemoglobin-study.git
   cd peru-hemoglobin-study
   ```
2. **Install required R packages:**
   ```r
   install.packages(c("tidyverse", "haven", "sf", "RColorBrewer", "knitr", "kableExtra"))
   ```
3. **Render the Quarto notebooks:**
   Place the harmonized dataset (`Limpio.csv`) and departmental shapefile (`map_dep/`) in the root directory, then execute:
   ```bash
   quarto render Proyecto_final_bio.qmd
   ```

## Public Health Policy Recommendations

1. **Altitude-Specific Clinical Thresholds:** Tailor anemia screening and iron supplementation protocols to regional elevation profiles rather than relying solely on unadjusted international cutoffs.
2. **Trimester-Targeted Surveillance:** Prioritize early second-trimester hemoglobin monitoring when physiological hemodilution accelerates the steepest decline.
3. **Regional Resource Prioritization:** Focus maternal nutrition interventions in Andean departments located at $\ge 2,500\text{ m.a.s.l.}$, where overall anemia prevalence reaches 30%.
