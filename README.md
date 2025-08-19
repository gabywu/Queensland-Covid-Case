# Local Dynamics of COVID-19 Transmission in Queensland

**Exploring demographic, spatial, and seasonal COVID-19 trends across Queensland (Both start of the Pandemic, and from July 2024 to July 2025)**

---

## Executive Summary

This project investigates COVID-19 case trends in Queensland using open government data. Key insights include:

- A **demographic shift in vulnerability**, with higher incidence in **young children (0–4)** and **older adults (75–79)**.
- **Seasonal peaks** in cases during winter and early summer, aligned with typical flu seasons.
- **Metro North and Metro South** emerged as consistent hotspots.
- Data quality limitations particularly **98.1% of cases marked “Under Investigation”** in source attribution significantly affect transmission insights.

Recommendations include enhancing data completeness, improving geographic categorisation, and focusing public health responses on seasonal and demographic risks.

---

## Objectives

This analysis aims to:

- Identify **shifts in age-group vulnerability** over time  
- Explore **temporal and demographic** COVID-19 patterns  
- Assess **geographic distribution** across Hospital and Health Services (HHS) and Local Government Areas (LGAs)  
- Investigate **source attribution**

---

## Tools & Technologies

- **Python** (Jupyter Notebook)
  - `pandas`, `numpy`, `matplotlib`, `seaborn`
- AI-assisted coding tools (for validation and efficiency)

---

## Dataset Overview

- **Source**: Queensland Government Open Data Portal
- **License**: [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/)
- **Files Used**:
  1. `Queensland COVID-19 Case Line List – Age Groups`  
     - Focused on demographics, especially `AGE_GROUP_5Y`
     - Data source: [Queensland Government Open Data Portal: Age Groups](https://www.data.qld.gov.au/dataset/queensland-covid-19-case-line-list-age-groups) *(accessed 10 August 2025)*
  2. `Queensland COVID-19 Case Line List – Location & Source of Infection`  
     - Focused on `HHS`, `LGA_NAME`, and `SOURCE_INFECTION`
     - Data source: [Queensland Government Open Data Portal: Location & Sourse of Infection](https://www.data.qld.gov.au/dataset/queensland-covid-19-case-line-list-location-source-of-infection) *(accessed 10 August 2025)*
- **Total Records**: 1,854,305 (in each table)

> **Limitation:** 98.1% of source attribution marked "Under Investigation", impacting analysis of transmission pathways.

---

## Data Cleaning & Preparation

- Converted `NOTIFICATION_DATE` to datetime format
- Cleaned `AGE_GROUP_5Y` (removed text like "years")
- Removed non-essential fields (`_id`, `POSTCODE`, `SA2_CODE`, etc.)
- Missing LGA names (~1.46%) were retained (no imputation)
- No table joins were attempted due to misaligned granularity
- Preserved raw structure to reflect original reporting fidelity

---

## Exploratory Data Analysis

### Age Group Trends

- **Highest overall cases**: 25–29 age group (~164,000)
- **Most affected in 2024–25**: 0–4 and 75–79 age groups  
  - Suggests shift in vulnerability post-vaccination era

### Temporal Trends

- Peak in **October 2021**, with stabilization post-January 2023
- Notable spikes in **July and December 2024** (seasonal)

### Geographic Distribution

- **Brisbane City**: Highest case count (~475,000)
- **Metro North & Metro South**: 46.1% of all cases (combined)
- Geographic alignment inconsistencies between `HHS` and `LGA_NAME`

### Source Attribution

- Most data marked "Under Investigation"
- Cairns and Hinterland showed highest **confirmed local transmission**

---
## Key Insights

- **Demographic shifts** toward vulnerable populations (0–4, 75–79)
- **Seasonal peaks** confirm flu-period alignment
- **Brisbane metro** remains the central hotspot
- **Data limitations** reduce reliability in source-based insights

---

## Recommendations

### Data Quality

- Add **regional/urban-rural** classification
- Include a **shared identifier** across datasets for joining
- Increase **case investigation completion**

### Public Health Response

- Increase **seasonal health messaging and vaccinations**
- Focus on **Metro North/South** for high-density interventions
- Enhance support for **at-risk groups** (children, elderly)

### Further Analysis

- Examine **cross-HHS patient flows**
- Model **age-location-source** correlations to uncover deeper risk patterns

---

## 📄 Reports & Notebooks

- 📘 [Download Full Report (PDF)](./qld-covid19-data-analysis-report-2025.pdf)
- 💻 [View Analysis in Jupyter Notebook](./qld-covid19-2025.ipynb)
