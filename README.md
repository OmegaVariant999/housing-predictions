# California Housing: Data Cleaning and Preprocessing Pipeline

## Overview

This repository contains the end-to-end data acquisition, cleaning, and preprocessing workflow for the California Housing dataset.

## Dataset url:

https://www.kaggle.com/datasets/camnugent/california-housing-prices

## Dataset Description

- **Source**: 1990 California Housing Census Dataset
- **Records**: 20,640 census blocks
- **Original Features**: 10 (numerical coordinates, housing metrics, income, target value, and spatial categorical feature)

## Pipeline Stages

1. **Initial Data Audit**: Identified structural types, summary statistics, and missing values.
2. **Missing Value Imputation**: Imputed 207 missing values in `total_bedrooms` using the feature median to prevent skewness bias.
3. **Deduplication**: Audited records to ensure zero redundant duplicate rows.
4. **Outlier Treatment**: Applied Interquartile Range (IQR) Tukey fences (1.5 \* IQR) to cap extreme values in `total_rooms`, `total_bedrooms`, `population`, and `households`.
5. **Categorical Encoding**: One-hot encoded `ocean_proximity` using binary indicators (`drop_first=True`).
6. **Data Export**: Serialized the processed dataset to `california_housing_cleaned.csv`.

## Setup and Execution

```bash
pip install -r requirements.txt
jupyter notebook house.ipynb
```
