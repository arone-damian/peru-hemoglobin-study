# Non-linear Association Between Hemoglobin Levels and Gestational Age in Peruvian Pregnant Women

## Project Overview

This research investigates the non-linear associations between gestational age and hemoglobin levels among pregnant women in Peru, considering critical environmental and maternal factors. Using a comprehensive national dataset of **114,000 pregnant women** from 2022 (Peruvian Ministry of Health - MINSA), this study examines how altitude, maternal age, height, and weight influence hemoglobin concentrations throughout pregnancy.

**Key Findings:**
- **Anemia prevalence increases with altitude**: 5.4% (<1500m), 7.2% (1500–2500m), and 10.8% (>2500m).
- **Hemoglobin decreases progressively with gestational age**: weekly reduction of 0.031 g/dL (simple model) and 0.032 g/dL (adjusted model).
- **Significant interaction** between altitude and gestational age (p < 0.01), meaning the physiological changes during pregnancy are modulated by environmental hypoxia.

---

## Objectives

**Primary Objective:**
- Analyze the association between gestational age and hemoglobin levels in pregnant women in Peru during 2022, adjusting for altitude, weight, height, and maternal age.

**Secondary Objectives:**
- Determine the prevalence of severe anemia across different altitude ranges.
- Describe the distribution of hemoglobin levels by pregnancy trimester.
- Evaluate the adjusted relationship between gestational age and hemoglobin levels.

---

## 📊 Methodology

### Study Design
- Cross-sectional study using secondary data from the Peruvian Ministry of Health (MINSA) open data repository (2022).

### Population and Sample
- **114,000 pregnant women** from all regions of Peru with complete records of:
  - Hemoglobin (g/dL)
  - Gestational age (weeks)
  - Maternal age (years)
  - Weight (kg) and height (cm)
  - Altitude of residence (masl)

### Variables
- **Dependent**: Hemoglobin levels (g/dL).
- **Independent**: Gestational age (weeks), maternal age (years), altitude (masl), weight (kg), height (cm).
- **Additional**: Anemia classification according to WHO trimester-specific thresholds.

### Statistical Analysis
| Step | Method |
|------|--------|
| Descriptive | Anemia prevalence by altitude ranges (<1500m, 1500–2500m, ≥2500m) |
| Simple regression | Unadjusted effect of gestational age on hemoglobin |
| Multiple regression | Adjusted for confounders (age, BMI, altitude) |
| Interaction test | Altitude × gestational age interaction (p < 0.01) |

### Tools
- **R Programming** with `dplyr` (data manipulation) and `ggplot2` (visualization).

---

## 📈 Key Results

### Hemoglobin and Anemia by Altitude

| Altitude Range | Mean Hb (g/dL) | Anemia Prevalence |
|----------------|---------------|-------------------|
| <1500 m        | 12.3          | 5.4%              |
| 1500–2500 m    | 11.7          | 7.2%              |
| ≥2500 m        | 10.9          | 10.8%             |

### Gestational Age Effect
- **Simple linear regression**: −0.031 g/dL per week (p < 0.05).
- **Adjusted multiple regression**: −0.032 g/dL per week, confirming that altitude and maternal characteristics significantly modulate this relationship.

### Interaction
- The inclusion of an altitude × gestational age interaction term was **significant (p < 0.01)**, indicating that the impact of gestational age on hemoglobin depends on the altitude of residence.

---

## 🏥 Public Health Implications

1. **Altitude‑adjusted protocols**: Regions above 2500m require more aggressive screening and iron supplementation.
2. **Continuous monitoring**: Regular hemoglobin measurements throughout pregnancy are essential.
3. **Policy recommendations**:
   - Develop region‑specific reference ranges for hemoglobin.
   - Integrate altitude into national prenatal care guidelines.
   - Address socioeconomic and dietary determinants in future research.

---

## 💻 Repository Structure
