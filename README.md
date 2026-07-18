# AI Anomaly Detection

Network anomaly detection on the NSL-KDD dataset using XGBoost and an autoencoder neural network, with threshold-based anomaly detection.

## Overview

This project applies both classical machine learning and deep learning techniques to detect anomalous network traffic. It was built as part of an NVIDIA Deep Learning Institute workshop assessment on anomaly detection.

## Dataset

**NSL-KDD**, published by the University of New Brunswick — an improved version of the classic KDD Cup dataset with redundant and duplicate records removed, making it a more reliable benchmark for network intrusion detection.

## Objectives

1. **XGBoost model** — a GPU-accelerated, multi-class supervised model trained to classify network traffic types, evaluated with accuracy and a confusion matrix.
2. **Autoencoder neural network** — a deep learning model trained to learn the structure of normal traffic, used to flag anomalies via reconstruction error.
3. **Anomaly detection thresholding** — determining the optimal threshold (via ROC/AUC analysis) that separates normal from anomalous packets based on reconstruction error.

## Approach

- **Preprocessing**: cleaning and preparing the NSL-KDD data for both models.
- **XGBoost**: multi-class classification of traffic types on GPU, evaluated against a >90% accuracy target.
- **Autoencoder**: encoder-decoder architecture trained on normal traffic to reconstruct input; anomalies are flagged where reconstruction error exceeds a computed threshold.
- **Evaluation**: confusion matrices and accuracy scores for both models, plus ROC/AUC-based threshold selection for the autoencoder.

## Requirements

- Python 3
- `xgboost`
- `tensorflow` / `keras`
- `numpy`, `pandas`, `matplotlib`
- GPU recommended for XGBoost training

## Usage

Open `Ai Anomaly Detection.ipynb` in Jupyter and run the cells in order. The notebook is self-contained, walking through data loading, preprocessing, model training, and evaluation for both the XGBoost classifier and the autoencoder.

## Results

- XGBoost classifier: >90% accuracy on traffic classification
- Autoencoder: >90% accuracy on anomaly detection via reconstruction-error thresholding
