# Car Crash Data Clustering & Regression Analysis

Statistics final project analyzing a real-world traffic collision dataset using linear regression and K-Means clustering to explore relationships between collision type and primary contributing factor.

## Overview

Traffic collision records don't come with an obvious numeric structure, most of the useful fields (collision type, primary contributing factor) are categorical. This project encodes those categories numerically, fits a baseline linear regression across the full dataset, then uses K-Means clustering to segment the data and re-fits regression within each cluster to see whether clustering reveals stronger local relationships that a single global model misses.

## What it does

1. **Data cleaning** — loads the crash dataset, drops incomplete records.
2. **Exploratory analysis** — plots frequency distributions of collision type and primary contributing factor to understand the category breakdown before modeling.
3. **Feature encoding** — maps each categorical field (collision type, primary factor) to a numeric value ranked by frequency, so the fields can be used in regression and clustering.
4. **Baseline regression** — fits a single linear regression across the full dataset to test the overall relationship between collision type and primary factor, using mean squared error (MSE) as the fit metric.
5. **K-Means clustering** — clusters records by collision type and primary factor, tested at two granularities (k=8 and k=20), and visualizes each cluster's centroid against its nearest points.
6. **Per-cluster regression** — re-fits linear regression within each individual cluster and compares MSE across clusters against the baseline, to evaluate whether segmenting the data first produces a better local fit than one model for the whole dataset.

## Output

- Bar charts showing the frequency of each collision type and primary contributing factor.
- A baseline regression line and MSE for collision type vs. primary factor across the full dataset.
- Cluster visualizations (at k=8 and k=20) showing each cluster's centroid and its nearest points.
- Regression slope, intercept, and MSE for each individual cluster, allowing direct comparison of model fit across clusters vs. the single baseline model.

## Tech stack

Python, pandas, NumPy, scikit-learn (`KMeans`, `LinearRegression`), Matplotlib

## Notes

Originally built and run in Google Colab as a course final project; this repo contains the exported script version.
