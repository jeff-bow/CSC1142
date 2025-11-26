# CSC1142 – FluNet Influenza Analytics Pipeline (Spark + Docker)

This repository contains our cloud data processing assignment for CSC1142.  
We built an end-to-end Apache Spark pipeline on top of the WHO FluNet  data, and enriched it with population data to make meaningful, comparable flu indicators across countries and years.

Our goals were:

- to ingest the raw FluNet CSV exports for all six WHO regions.
- clean and standardise them into a single global table.
- engineer useful features (like positivity rates and rolling trends).
- enrich everything with population data.
- write out an analysis-ready “gold” dataset for future analysis.

---

## Project structure

The main folders and files are:

```text
.
├── docker-compose.yml        # Jupyter + PySpark environment (Docker)
├── data/
│   ├── FluNet_AFR.csv        # Raw FluNet CSVs per WHO region
│   ├── FluNet_AMR.csv
│   ├── FluNet_EMR.csv
│   ├── FluNet_EUR.csv
│   ├── FluNet_SEAR.csv
│   ├── FluNet_WPR.csv
│   ├── external/
│   │   └── population.csv    # External population data (per country, per year)
│   └── processed/
│       ├── flunet_features/  # “Silver” / feature layer (Parquet, partitioned)
│       └── flunet_enriched/  # “Gold” / enriched analytical layer (Parquet, partitioned)
└── notebooks/
    └── flunet_pipeline_final.ipynb   # Main Spark pipeline notebook
