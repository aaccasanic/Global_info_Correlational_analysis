![Python](https://img.shields.io/badge/Python-3.10+-blue)

# Global Correlation Analysis

**Language:** [English](README.en.md) | [Español](README.es.md)

## Overview

This project explores how worldwide indicators from six major domains interact through cross-domain correlation analysis:

- Economy
- Health
- Education
- Demography
- Environment
- Geopolitics

The notebook loads and prepares multiple datasets, groups variables by domain, computes pairwise correlation matrices, and visualizes the results as annotated heatmaps. The aim is to reveal broad structural patterns that can support exploratory research, hypothesis generation, and future statistical modeling.

## Project Goals

- Compare how indicators from different development domains move together.
- Highlight the strongest and weakest domain relationships.
- Provide a reproducible notebook-based workflow for cleaning, correlating, and visualizing global data.
- Create a foundation for future work such as clustering, dimensionality reduction, and causal analysis.

## Data Sources

The analysis uses the following files from the repository root:

- `World_Data_2023.csv`
- `World_Data_2023_corrected.csv`
- `Global_Weather_Repository.csv`
- `Literacy_Rate.xlsx`

The notebook also creates a cleaned version of the world dataset (`World_Data_2023_corrected.csv`) before running the final analysis.

## Workflow

1. Load the CSV and Excel datasets into pandas.
2. Correct delimiter and type issues in `World_Data_2023.csv`.
3. Organize indicators into six analytical domains.
4. Compute pairwise correlation matrices for every domain combination.
5. Render each matrix as an annotated heatmap with a fixed `[-1, 1]` color scale.

## Main Findings

- Education and Health show the most consistent strong relationships, especially around literacy, life expectancy, and mortality-related indicators.
- Health and Demography form another strong cluster, connecting fertility, birth rates, mortality, and life expectancy.
- Demography and Environment show moderate-to-strong relationships, largely driven by population scale and emissions.
- Short-term economic indicators appear weaker than long-run social indicators in this dataset, while GDP stands out as the most influential economic variable.

These findings are exploratory. They describe association patterns in the available data and should not be interpreted as proof of causation.

## Visual Outputs

The repository includes 15 heatmaps, which matches every pairwise combination across the six domains (`6 choose 2 = 15`).

![Correlation overview](visuals/correlation-coefficient.webp)

Selected previews:

<p align="center">
  <img src="visuals/heatmaps/economy_health.png" width="48%" alt="Economy vs Health heatmap">
  <img src="visuals/heatmaps/health_education.png" width="48%" alt="Health vs Education heatmap">
</p>

<p align="center">
  <img src="visuals/heatmaps/education_environment.png" width="48%" alt="Education vs Environment heatmap">
  <img src="visuals/heatmaps/environment_geopolitics.png" width="48%" alt="Environment vs Geopolitics heatmap">
</p>

You can browse the complete set in [`visuals/heatmaps`](visuals/heatmaps).

## Repository Structure

The current repository is organized around notebook-driven analysis and presentation assets:

```text
.
|-- Global_Correlation_Analysis.ipynb
|-- World_Data_2023.csv
|-- World_Data_2023_corrected.csv
|-- Global_Weather_Repository.csv
|-- Literacy_Rate.xlsx
|-- Dashboard_python_worldwide info.pbix
|-- Dashboard_worldwide_info.pbix
|-- visuals/
|   |-- correlation-coefficient.webp
|   `-- heatmaps/
|       `-- *.png
|-- README.md
|-- README.en.md
`-- README.es.md
```

## Requirements

No `requirements.txt` file is included yet. Based on the notebook imports, the project currently depends on:

- Python 3.10 or newer
- pandas
- numpy
- matplotlib
- openpyxl
- jupyter

You can install the core packages with:

```bash
pip install pandas numpy matplotlib openpyxl jupyter
```

## How to Run

1. Open `Global_Correlation_Analysis.ipynb` in Jupyter Notebook or JupyterLab.
2. Run the data loading and cleaning cells to regenerate `World_Data_2023_corrected.csv` if needed.
3. Execute the correlation and plotting cells to review the matrices and visual outputs.
4. Open the `.pbix` files in Power BI Desktop if you want to review the dashboard deliverables.

## Limitations and Next Steps

Current limitations:

- Correlation does not establish causation.
- Scale-heavy variables such as population, land area, and emissions may inflate some relationships.
- The selected economic indicators are more short-term and policy-sensitive than structural development metrics.
- Pearson correlation captures linear relationships only.

Recommended next steps:

- Add structural indicators such as GDP per capita, HDI, or inequality measures.
- Apply normalization or log transforms to scale-dominant variables.
- Test non-linear relationships with Spearman or Kendall correlation.
- Extend the workflow with clustering, PCA, or causal modeling approaches.

## Contact

If you would like to expand the analysis, build new dashboards, or prepare a more detailed report, feel free to reach out:

- Email: `aacccasanic@gmail.com`
