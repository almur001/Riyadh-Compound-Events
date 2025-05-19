# 📘 Temperature/Precipitation/Compound Events Analysis
## ERA5 data for Riyadh, Saudi Arabia: 2014–2024

This repository was developed for Alissa Murray's Master's Thesis, "Mapping Resilience to Compound Events in a Global Metropolis: A Case Study of Riyadh, Saudi Arabia". It contains a set of Jupyter notebooks analyzing extreme heat, precipitation, and compound events using ERA5 reanalysis data (2014–2024) for Riyadh, Saudi Arabia. The analysis includes threshold-based detection, seasonal breakdowns, geospatial heatmaps, and time-lag pairing of events.

## 📂 Notebooks
**1. Complete Precipitation Analysis.ipynb**

Focus: Analyzes daily precipitation data from ERA5 and extracts:

* Maximum daily and annual rainfall

* Top 10 rainy days per year

* Rainfall intensity thresholds: 95th, 98th, 99th, 99.9th percentiles

* Seasonal analysis of spring (MAM) rainfall events


Key Outputs:

📈 Plots of max precipitation per year

📊 Monthly distribution of rainiest days

🖼️ PNG heatmaps of annual rainiest days

🌍 GeoTIFFs for spatial mapping in QGIS

📄 CSVs summarizing extreme rainfall days and percentiles


**2. Complete Temp Analysis.ipynb**

Focus: Analyzes 2m daily max temperatures and detects heatwaves based on the 95th percentile rule (≥3 consecutive days).

Key Features:

* Detects heatwave start/end dates and durations

* Extracts hottest day per year and for each heatwave

* Computes trends in time lag from spring rain to heat

* Aligns temperature rasters to precipitation grid for consistency


Key Outputs:

📊 Heatwave frequency and duration statistics

🖼️ PNG & 🌍 GeoTIFF exports of hottest heatwave days

📄 CSVs of heatwave peaks and metadata

**3. Complete CE Analysis.ipynb**

Focus: Integrates temperature and precipitation data to identify compound events defined as:
"The most intense rainfall event of the year followed by the first subsequent heatwave (within the same calendar year)"

Key Features:

* Matches rain–heat event pairs per year (2014–2024)

* Computes Δ Days between rain and heat

* Analyzes seasonal clustering and lag time trends

* Applies statistical tests to assess trend significance

Key Outputs:

📋 CSV of compound rain/heat event pairs

📈 Linear regression of rain–heat time gaps

🖼️ Visualizations of event timelines and seasonal overlaps

## 📊 Data Sources
ERA5 hourly data on single levels from 1940 to present, from the Copernicus Climate Data Store:

* Precipitation: tp (total precipitation), converted to mm

* Temperature: t2m (2-meter air temperature), converted to °C

Hersbach, H., Bell, B., Berrisford, P., Biavati, G., Horányi, A., Muñoz Sabater, J., Nicolas, J., Peubey, C., Radu, R., Rozum, I., Schepers, D., Simmons, A., Soci, C., Dee, D., Thépaut, J-N. (2023): ERA5 hourly data on single levels from 1940 to present. Copernicus Climate Change Service (C3S) Climate Data Store (CDS), DOI: 10.24381/cds.adbb2d47 (Accessed on 15-11-2024)

## 🛠️ Tools & Libraries
* xarray, pandas, numpy

* matplotlib, seaborn

* rioxarray, rasterio for GeoTIFF export

* scipy.stats for trend/regression analysis

## 🧪 Reproducibility
* To rerun the analysis:

* Place NetCDF data files in the Data/ directory:

* precip-2014-2024-full.nc

* 2m-temp-2014-2024-full.nc

* Install required packages (via pip install -r requirements.txt).

* Run the notebooks sequentially.
