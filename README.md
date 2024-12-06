# EEG-Based Drowsiness Detection

This repository contains the analysis and model development for detecting drowsiness based on EEG (electroencephalography) brainwave data. The project utilizes machine learning techniques to identify whether a subject is in a "sleepy" or "not sleepy" state based on various EEG features.

### Project Overview

In this project, we work with a Kaggle EEG dataset that records normalized features derived from different brainwave frequency bands. The goal is to classify these states using machine learning models and feature engineering techniques.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Day 1 - Data Cleaning and Exploratory Data Analysis (EDA)](#day-1-data-cleaning-and-exploratory-data-analysis-eda)
4. [Day 2 - Model Training](#day-2-model-training)
5. [Results](#results)
6. [Conclusions](#conclusions)

---

## Introduction

The objective of this project is to explore EEG data to classify a person's cognitive state as "sleepy" or "not sleepy." EEG data consists of several frequency bands (e.g., Delta, Theta, Alpha, Beta, Gamma), which are measured during brain activity. We use this data to develop a model that can predict whether a person is drowsy based on these brainwaves.

---

## Dataset Overview

The dataset contains normalized features for different brainwave frequency bands and a classification label for each instance. The classification label indicates whether the subject was "not sleepy" (0) or "sleepy" (1) based on EEG readings.

The key features in the dataset include:
- Delta, Theta, LowAlpha, HighAlpha, LowBeta, HighBeta, LowGamma, HighGamma (Brainwave frequency bands)
- Derived features (ratios and differences between frequency bands)
- Classification (binary: 0 for "Not Sleepy", 1 for "Sleepy")

---

## Day 1 - Data Cleaning and Exploratory Data Analysis (EDA)

### Data Exploration and Initial Analysis

1. **Dataset Familiarization**
   - Loaded the dataset for initial exploration.
   - Identified key variables (e.g., Delta, Theta, Classification).
  
2. **Data Cleaning**
   - Removed irrelevant features like *Attention* and *Meditation* as they did not contribute meaningfully to the analysis.
   - Cleaned data by removing outliers and handling missing or zero values. Standardized column names for consistency.

3. **Feature Engineering**
   - Derived new features that could improve the model’s ability to distinguish between the two states:
     - `Theta_LowAlpha_Ratio`
     - `Theta_HighAlpha_Ratio`
     - `Delta_Theta_Ratio`
     - `Total_Alpha`, `Total_Beta`, `Total_Gamma`
     - `High_Low_Alpha_Diff`, `High_Low_Beta_Diff`, `High_Low_Gamma_Diff`
   - Ensured data was clean, with no missing or erroneous values.

### Exploratory Data Analysis (EDA)

On Day 1, we conducted **Exploratory Data Analysis (EDA)** to better understand the dataset and identify potential patterns and relationships in the features.

#### Key Observations:
1. **Skewed Distributions**:
   - Most features, including **Delta**, **Theta**, **LowAlpha**, **HighAlpha**, **LowBeta**, **HighBeta**, **LowGamma**, and **HighGamma**, exhibited skewed distributions.
   - This required potential data transformations like normalization or scaling.

2. **Class Imbalance**:
   - The **Sleepy/Not Sleepy** classification variable showed a slight imbalance. This could influence the model's performance, and techniques like oversampling or undersampling might be applied.

3. **Feature Importance**:
   - **Delta** and **Theta** were weak indicators for distinguishing sleepy and non-sleepy states.
   - Derived features such as **`Theta_LowAlpha_Ratio`** and **`Delta_Theta_Ratio`** showed more potential in distinguishing between states.

### Visualizations

#### Box Plots:
- **Delta_Theta_Ratio**  
  ![boxplot_Delta_Theta_Ratio](https://github.com/user-attachments/assets/a6050b8b-aaf4-4b52-a5ba-fe7faed68d1e)

- **Theta_HighAlpha_Ratio**  
  ![boxplot_Theta_HighAlpha_Ratio](https://github.com/user-attachments/assets/7574c79f-1155-45bf-9332-3d651d0c5413)

- **Theta_LowAlpha_Ratio**  
  ![boxplot_Theta_LowAlpha_Ratio](https://github.com/user-attachments/assets/09a62966-16fd-4d3a-a41c-0da81288f6f6)

#### Histograms:
- **Delta**  
  ![histogram_delta](https://github.com/user-attachments/assets/edb8ec29-0c2a-49fb-b484-33b5c3224a9d)

- **Theta**  
  ![histogram_theta](https://github.com/user-attachments/assets/7589f8f8-bf78-4785-933f-fce4e241c56e)

---

## Day 2 - Model Training

### Data Preprocessing
- **Scaling Features**: Applied **StandardScaler** to normalize the features and remove bias due to feature scale differences.
- **Data Split**: Divided the dataset into training (80%) and testing (20%) sets to evaluate the model's performance on unseen data.
- **Class Imbalance Handling**: Applied **SMOTE** (Synthetic Minority Over-sampling Technique) to handle the class imbalance between "sleepy" and "not sleepy."

### Model Selection
Several classification models were considered to predict the **sleepy vs not sleepy** classification:
1. **Logistic Regression**
2. **Random Forest Classifier**
3. **Gradient Boosting Classifier**
4. **Support Vector Machine (SVM)**

#### Hyperparameter Tuning
- **GridSearchCV** was applied to tune hyperparameters for **Random Forest** and **Gradient Boosting** models, aiming to find the optimal values for better model performance.

### Model Evaluation
Evaluated models using **accuracy**, **precision**, **recall**, **F1 score**, and **ROC AUC** score. The **Random Forest** and **Gradient Boosting** classifiers performed well, with **Gradient Boosting** yielding the highest accuracy and F1 score.

#### Performance Metrics
- **Random Forest Classifier**
  - Accuracy: 92%
  - Precision: 91%
  - Recall: 93%
  - F1 Score: 92%

- **Gradient Boosting Classifier**
  - Accuracy: 93%
  - Precision: 92%
  - Recall: 94%
  - F1 Score: 93%
    
![evaluation_metrics_plot](https://github.com/user-attachments/assets/a00512a7-8a45-4637-9edf-5e666b28fd08)

---

## Results

After training and evaluating multiple models, **Gradient Boosting** performed the best, offering the highest accuracy and F1 score in distinguishing between sleepy and non-sleepy states. The model demonstrated excellent recall, which is important in scenarios where detecting sleepiness is crucial (e.g., driving drowsiness detection).

---

## Conclusions

1. **Feature Engineering**: Ratios and derived features significantly improved model performance. Features such as **`Delta_Theta_Ratio`** and **`Theta_LowAlpha_Ratio`** were strong indicators for drowsiness detection.
2. **Model Performance**: **Gradient Boosting** outperformed other models, yielding the best overall performance metrics.
3. **Future Improvements**: 
   - Explore more advanced feature engineering techniques.
   - Investigate the use of deep learning models for better performance in real-time applications.
