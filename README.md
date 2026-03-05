# Gesture Recognition with Classical Machine Learning

This project explores hand gesture classification using **classical machine learning models**.

The goal is to evaluate how well traditional ML methods perform on gesture recognition tasks using extracted features.


<br>

## Pipeline

dataset → preprocessing → feature extraction → model training → evaluation

<br>

## Models Evaluated

- Support Vector Machine (SVM)
- Random Forest
- K-Nearest Neighbors (KNN)
- Extra Trees

<br>

## Features

Examples of extracted features include:

- geometric hand features
- spatial relationships
- statistical descriptors

<br>

## Technologies

Python  
scikit-learn  
NumPy  
Pandas  

<br>

## Goal

Provide a **baseline comparison of classical ML models for gesture recognition** before moving to deep learning approaches.


<br>

## Data Exploration & Visualization

Before training the models, the gesture recognition dataset was carefully analyzed to understand its structure and statistical properties.

The analysis focused on:

- Class balance
- Missing values
- Feature scaling
- Feature variability
- Model performance comparison

For readers interested in deeper technical details, see:
- [Feature Engineering Details](#feature-engineering-details)
- [Normalization Method](#normalization-method)
- [Model Selection Rationale](#model-selection-rationale)

<br>

### Label Distribution

<p align="center">
  <img src="plots/Histogram label train-final.png" width="600" alt="Train label distribution"/>
  <br>
  <em>Label distribution for the training set</em>
</p>

<p align="center">
  <img src="plots/Histogram label test-final.png" width="600" alt="Test label distribution"/>
  <br>
  <em>Label distribution for the test set</em>
</p>

The gesture classes are approximately balanced in both datasets.  
Balanced labels reduce model bias and support fair evaluation.

<br>

### Missing Data Check

<p align="center">
  <img src="plots/MissingDatapoints1.png" width="700" alt="Missing data in training set"/>
</p>

<p align="center">
  <img src="plots/MissingDatapoints2.png" width="700" alt="Missing data in test set"/>
</p>

The heatmaps confirm that missing values are negligible, indicating good data integrity.

<br>

### Feature Variability (Boxplots)

<p align="center">
  <img src="plots/BoxPlot1-60.png" width="800"/>
</p>
<p align="center">
  <img src="plots/BoxPlot60-120.png" width="800"/>
</p>
<p align="center">
  <img src="plots/BoxPlot120-180.png" width="800"/>
</p>
<p align="center">
  <img src="plots/BoxPlot180-240.png" width="800"/>
</p>

The boxplots show structured variability across feature groups, suggesting meaningful differences between gesture classes.

<br>

### Model Comparison

<p align="center">
  <img src="plots/Model_Results_Summary.png" width="700"/>
</p>

Random Forest and Extra Trees achieved the strongest performance (~85% accuracy).  
Detailed reasoning is provided in the section below.

<br>

## Feature Engineering Details

The dataset originates from 20 tracked body joints captured using a Kinect sensor.

From the raw joint coordinates, additional features were derived:

- Pairwise cosine similarities between joint vectors
- Relative distances between selected joints
- Aggregated statistics capturing movement trends

These features encode spatial structure and relational information, transforming raw coordinates into structured representations suitable for classical ML models.

<br>

## Feature Normalization

Because joint coordinates and derived features operate on different numeric scales, normalization was applied to:

- Align feature magnitudes
- Reduce skewness
- Improve numerical stability during training

This ensures that no single feature disproportionately influences the model.

<br>

## Model Behavior

Tree-based ensemble models performed best.

Random Forest and Extra Trees work well because they:

- handle structured tabular data effectively  
- capture nonlinear relationships  
- remain robust to feature scaling differences
  
<br>

## Gesture Skeleton Reconstruction

<p align="center">
  <img src="plots/photo_2023-09-14_12-56-31.jpg" width="400"/>
  <br>
  <em>2D skeletal reconstruction from Kinect joint coordinates</em>
</p>

The skeleton representation illustrates how joint coordinates form the structural basis of the gesture features.

<br>

## Summary

- Dataset is balanced and clean  
- Features capture meaningful spatial relationships  
- Normalization ensures stable training  
- Random Forest and Extra Trees achieved ~85% accuracy  

Future work includes extending this approach toward temporal modeling and spiking neural network architectures.
