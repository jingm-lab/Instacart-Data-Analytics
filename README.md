# Instacart End-to-End Data Analytics

## Overview

This project segments Instacart customers and mines basket associations using the public 2017 Kaggle dataset (~3M orders). The analysis is framed around basket size as the lever for GTV growth, with two intervention surfaces: personalized sponsored ads (informed by segmentation) and cart-based suggestions (informed by co-purchase rules).

## Tech Stack
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=seaborn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![mlxtend](https://img.shields.io/badge/mlxtend-3F4F75?style=for-the-badge)

## Key Findings
Customer segmentation: identified three stable segments based on organic-preference signals across 8 departments, validated via bootstrap stability analysis.

Association rules: surfaced co-purchase rules dominated by two real shopping modes, recipes assembly and pantry restocking, which are externally validated by Instacart's own recipe-to-cart feature.


## Methods
- GMM clustering
- Bootstrap stability (ARI)
- FP-growth association rules
- Lift/penetration profiling

## Quick Start

### 1. Get the data
Download the [Instacart Market Basket Analysis dataset](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis/data) from Kaggle and place the CSV files in a `Data/` folder at the repo root:

```bash
Data/
├── aisles.csv
├── departments.csv
├── order_products__prior.csv
├── orders.csv
└── products.csv

```

### 2. Install dependencies

This project uses [uv](https://docs.astral.sh/uv/) for dependency management.

```bash
# Install uv if you don't have it
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install dependencies from the lockfile
uv sync
```

### 3. Run the notebook

```bash
uv run jupyter notebook Instacart_Data_Analytics.ipynb
```

It takes approximately 11 minutes to run the entire notebook.

## Limitations
Missing prices, demographics, brand or retailer data, which limits the analysis to behavioral patterns rather than economic or demographic segmentation.