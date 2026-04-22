# From Light Curves to Labels

MSc Data Science project comparing classical, machine learning, and deep learning methods for Kepler exoplanet transit classification.

## Overview
This project evaluates three modelling tiers:

- Classical: Box Least Squares (BLS)
- Machine Learning: Random Forest, XGBoost, SVM
- Deep Learning: Bidirectional LSTM (BiLSTM)

The aim is to compare performance across different model types and assess the effect of feature engineering and dataset size.

## Dataset
- Source: NASA Kepler DR25 KOI catalogue
- Light curves: MAST archive via `lightkurve`
- Full labelled dataset: 6,639 KOIs
- Sample dataset: 299 merged KOI rows
- Processed light curves: 293 stars

## Methods
- Light curve cleaning, stitching, outlier removal, and flattening
- KOI feature selection + extracted light-curve statistics
- 5-fold stratified cross-validation
- Accuracy and ROC-AUC as primary evaluation metrics
- Noise-based robustness testing

## Key Results

| Model | Dataset | Accuracy | ROC-AUC |
|---|---|---:|---:|
| Random Forest | 299-sample dataset | 0.836 | 0.913 |
| XGBoost | Full dataset | 0.897 | 0.960 |
| BiLSTM | 293 sequences | 0.615 | 0.531 |
| BLS baseline | Standalone | - | 0.371 |

## Main Finding
Feature-based machine learning, especially XGBoost, outperformed both the classical BLS baseline and the BiLSTM sequence model. The results suggest that, for this task, dataset scale and informative tabular features mattered more than model complexity.

## Tools
Python, NumPy, Pandas, Scikit-learn, XGBoost, TensorFlow, Lightkurve, Astroquery, Matplotlib

## Files
- `Kepler.ipynb` — main notebook
- `Final Project Report.pdf` — final report

## Author
Hassan Naseer  
MSc Data Science, University of Hertfordshire
