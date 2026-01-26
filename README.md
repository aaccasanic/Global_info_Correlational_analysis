# Global Correlation Analysis
This repository contains a comprehensive analytical exploration of cross-domain relationships across multiple global indicators. The project examines how socioeconomic, demographic, environmental, health, education, and geopolitical variables interact through correlation analysis and visual inspection.

The objective is to uncover high-level structural patterns, identify strong and weak relationships between domains, and provide a foundation for further modeling or statistical research.

## Contents
- Overview
- Key Findings
- Methodology
- Visualization Outputs
- Results Summary
- Next Steps
- Repository Structure
- Requirements
- License

### 1. **Overview**
  This project analyzes relationships across six major domains using global data:
- Economy
- Health
- Education
- Demography
- Environment
- Geopolitics
  The analysis computes pairwise correlation matrices between every domain combination and visualizes them using annotated heatmaps. This approach highlights structural dependencies, contrasts, and unexpected weak interactions within the dataset.

### 2. **Key Findings (High-Level)**
 
**Strongest Domain Relationships**
- Education ↔ Health: The most consistent and strongest correlations.
- Health ↔ Demography: High correlations around mortality, fertility, and life expectancy.
- Demography ↔ Environment: Population and urbanization strongly linked to CO₂ emissions.

**Moderate Relationships**
- Environment ↔ Geopolitics: Larger countries and military forces show higher emissions.
- Economy ↔ Environment: GDP strongly correlates with CO₂ emissions and population scale.

**Weak Relationships**
- Economy ↔ Health / Education: Tax, CPI, unemployment, and similar indicators show low predictive value.
- Education ↔ Geopolitics: Minimal correlations.
  Full summary and numerical results are included within the *.ipynb* notebook.
  
### 3. **Methodology**
  **Data Preparation**
- Filtering for numeric variables
- Type normalization (e.g., handling thousands separators, numeric strings)
- Validation of integer-based indices
  
  **Computation**
- Domain-level grouping of indicators
- Cross-domain matrix generation using pairwise combinations
- Selection of valid numeric columns per domain before correlation

  **Visualization**
- Annotated heatmaps using a custom plotting function
- Consistent color scaling between -1 and +1
- Labeling for easy interpretation

### 4. **Visualization Outputs**
The repository includes 15 heatmaps covering all combinations of:
- Economy
- Health
- Education
- Demography
- Environment
- Geopolitics

Each figure includes:
- Correlation values displayed inside each cell
- Uniform color scale
- Clear labeling of rows and columns
- Automated sizing for readability

### 5. **Results Summary**
Key global drivers identified across domains:
- Life expectancy
- Infant and maternal mortality
- Literacy rate
- Tertiary education enrollment
- CO₂ emissions
- Urban population
- **GDP** (most influential economic indicator)

Weak or inconsistent drivers:
- CPI
- CPI change
- Tax revenue
- Forested area
- Unemployment rate

A compact final summary table is available within the notebook.

### 6. **Next Steps** (Recommended Analysis)

A. **Enhanced Metrics**

Introduce structural economic variables such as:
- GDP per capita
- GINI index
- HDI
- Productivity metrics

B. **Normalization & Scaling**
- Per-capita transformations
- Log scaling for poly-distributed variables (population, emissions)
- Standardization (z-scores)

C. **Advanced Modeling**
- PCA (Principal Component Analysis)
- Cluster analysis (k-means, hierarchical)
- Outlier detection
- Factor models

D. **Composite Index Construction**
Develop a cross-domain index summarizing multi-dimensional development.

### 7. Repository Structure

.
├── data/
│   ├── raw/            # Original datasets
│   ├── processed/      # Cleaned and standardized datasets
│
├── notebooks/
│   └── Global_Correlation_Analysis.ipynb
│
├── visuals/
│   └── heatmaps/       # All correlation heatmap images
│
├── src/
│   ├── preprocessing/  # Data cleaning modules
│   ├── analysis/       # Correlation and numeric processing
│   ├── visualization/  # Heatmap and plotting utilities
│   └── utils/          # Supporting helper functions
│
└── README.md

### 8. Requirements
You may include a separate requirements.txt, but key dependencies typically include:

- pandas
- numpy
- matplotlib
- itertools
- seaborn
- jupyter

### 10. Contact
Gmail: *aacccasanic@gmail.com*

