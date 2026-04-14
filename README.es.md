![Python](https://img.shields.io/badge/Python-3.10+-blue)

# Global Correlation Analysis

**Idioma:** [English](README.en.md) | [Español](README.es.md)

## Descripción general

Este proyecto explora cómo interactúan indicadores globales de seis dominios principales mediante un análisis de correlación entre dominios:

- Economía
- Salud
- Educación
- Demografia
- Medio ambiente
- Geopolítica

El notebook carga y prepara varios conjuntos de datos, agrupa las variables por dominio, calcula matrices de correlación por pares y presenta los resultados con mapas de calor anotados. El objetivo es identificar patrones estructurales amplios que puedan servir como base para investigación exploratoria, generación de hipótesis y futuros modelos estadísticos.

## Objetivos del proyecto

- Comparar cómo se mueven conjuntamente los indicadores de distintos dominios del desarrollo.
- Resaltar las relaciones más fuertes y más débiles entre dominios.
- Ofrecer un flujo de trabajo reproducible en notebook para limpiar, correlacionar y visualizar datos globales.
- Dejar una base sólida para análisis posteriores, como agrupamiento, reducción de dimensionalidad o modelado causal.

## Fuentes de datos

El análisis utiliza los siguientes archivos ubicados en la raíz del repositorio:

- `World_Data_2023.csv`
- `World_Data_2023_corrected.csv`
- `Global_Weather_Repository.csv`
- `Literacy_Rate.xlsx`

Además, el notebook genera una versión corregida del conjunto de datos mundial (`World_Data_2023_corrected.csv`) antes de ejecutar el análisis final.

## Flujo de trabajo

1. Cargar los archivos CSV y Excel con pandas.
2. Corregir problemas de separador y tipos en `World_Data_2023.csv`.
3. Organizar los indicadores en seis dominios de análisis.
4. Calcular matrices de correlación para cada combinación de dominios.
5. Dibujar cada matriz como un mapa de calor anotado con una escala fija de `[-1, 1]`.

## Hallazgos principales

- Educación y Salud muestran las relaciones más consistentes y fuertes, especialmente en torno a alfabetización, esperanza de vida y señales ligadas a mortalidad.
- Salud y Demografía forman otro bloque sólido, conectando fecundidad, natalidad, mortalidad y esperanza de vida.
- Demografía y Medio ambiente presentan relaciones moderadas a fuertes, impulsadas en gran medida por el tamaño poblacional y las emisiones.
- Los indicadores económicos de corto plazo son más débiles que los indicadores sociales de largo plazo dentro de este conjunto de datos, aunque el PIB destaca como la variable económica más influyente.

Estos hallazgos son exploratorios. Describen asociaciones observadas en los datos disponibles y no deben interpretarse como evidencia de causalidad.

## Salidas visuales

El repositorio incluye 15 mapas de calor, que corresponden a todas las combinaciones por pares entre los seis dominios (`6 choose 2 = 15`).

![Resumen de correlaciones](visuals/correlation-coefficient.webp)

Vistas previas seleccionadas:

<p align="center">
  <img src="visuals/heatmaps/economy_health.png" width="48%" alt="Mapa de calor Economia vs Salud">
  <img src="visuals/heatmaps/health_education.png" width="48%" alt="Mapa de calor Salud vs Educacion">
</p>

<p align="center">
  <img src="visuals/heatmaps/education_environment.png" width="48%" alt="Mapa de calor Educacion vs Medio ambiente">
  <img src="visuals/heatmaps/environment_geopolitics.png" width="48%" alt="Mapa de calor Medio ambiente vs Geopolitica">
</p>

Puedes revisar la colección completa en [`visuals/heatmaps`](visuals/heatmaps).

## Estructura del repositorio

La organización actual del repositorio está centrada en el análisis con notebook y en archivos de presentación:

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

## Requisitos

Todavía no hay un archivo `requirements.txt`. Según las importaciones del notebook, el proyecto depende actualmente de:

- Python 3.10 o superior
- pandas
- numpy
- matplotlib
- openpyxl
- jupyter

Puedes instalar los paquetes principales con:

```bash
pip install pandas numpy matplotlib openpyxl jupyter
```

## Cómo ejecutarlo

1. Abre `Global_Correlation_Analysis.ipynb` en Jupyter Notebook o JupyterLab.
2. Ejecuta las celdas de carga y limpieza para regenerar `World_Data_2023_corrected.csv` si hace falta.
3. Corre las celdas de correlación y graficación para revisar las matrices y las salidas visuales.
4. Abre los archivos `.pbix` en Power BI Desktop si quieres revisar los dashboards del proyecto.

## Limitaciones y siguientes pasos

Limitaciones actuales:

- La correlación no demuestra causalidad.
- Las variables dominadas por escala, como poblacion, superficie o emisiones, pueden inflar algunas relaciones.
- Los indicadores económicos seleccionados son más sensibles al corto plazo y a políticas puntuales que a condiciones estructurales.
- La correlación de Pearson solo captura relaciones lineales.

Siguientes pasos recomendados:

- Agregar indicadores estructurales como PIB per capita, IDH o medidas de desigualdad.
- Aplicar normalización o transformaciones logarítmicas a variables dominadas por el tamaño.
- Explorar relaciones no lineales con correlacion de Spearman o Kendall.
- Ampliar el flujo de trabajo con agrupamiento, PCA o enfoques de modelado causal.

## Contacto

Si deseas ampliar el análisis, construir nuevos dashboards o preparar un informe más detallado, puedes escribir a:

- Correo: `aacccasanic@gmail.com`
