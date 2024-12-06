# EEG-Based Drowsiness Detection

This repository contains the analysis and model development for detecting drowsiness based on EEG (electroencephalography) brainwave data. The project utilizes machine learning techniques to identify whether a subject is in a "sleepy" or "not sleepy" state based on various EEG features.

### Project Overview

In this project, we work with a Kaggle EEG dataset that records normalized features derived from different brainwave frequency bands. The goal is to classify these states using machine learning models and feature engineering techniques.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Day 1 - Data Cleaning and Preparation](#day-1-data-cleaning-and-preparation)
4. [Day 2 - Exploratory Data Analysis (EDA)](#day-2-exploratory-data-analysis-eda)
5. [Feature Engineering](#feature-engineering)
6. [Modeling and Results](#modeling-and-results)
7. [Conclusions](#conclusions)

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

## Day 1 - Data Cleaning and Preparation

### Data Exploration and Initial Analysis

**Morning: Data Preparation (2-3 hours)**

1. **Dataset Familiarization**
   - Loaded the dataset into R and Google Sheets for initial exploration.
   - Identified key variables (e.g., delta, theta, classification).

2. **Data Cleaning**
   - Removed irrelevant features like *Attention* and *Meditation* as they were not contributing meaningfully to the analysis.
   - Cleaned data by deleting outliers and handling missing or zero values. Standardized column names for consistency.

3. **Feature Engineering**
   - Derived new features that could improve the model’s ability to distinguish between the two states:
     - `Theta_LowAlpha_Ratio`
     - `Theta_HighAlpha_Ratio`
     - `Delta_Theta_Ratio`
     - `Total_Alpha`, `Total_Beta`, `Total_Gamma`
     - `High_Low_Alpha_Diff`, `High_Low_Beta_Diff`, `High_Low_Gamma_Diff`
   - Ensured data was clean, with no missing or erroneous values.

---

## Day 2 - Exploratory Data Analysis (EDA)

On Day 2, the focus shifted to conducting **Exploratory Data Analysis (EDA)** to better understand the dataset and identify potential patterns and relationships in the features.

### Key Observations:

1. **Skewed Distributions**:
   - Most features, including Delta, Theta, LowAlpha, HighAlpha, LowBeta, HighBeta, LowGamma, and HighGamma, exhibited skewed distributions, with many values clustered at the lower end of the scale.

2. **Class Imbalance**:
   - The classification variable (Sleepy/Not Sleepy) showed a slight imbalance with more "Not Sleepy" samples than "Sleepy."

3. **Derived Features**:
   - Ratios like `Theta_LowAlpha_Ratio`, `Theta_HighAlpha_Ratio`, and `Delta_Theta_Ratio` showed skewness, with median values lower than the means.

4. **Box Plot Analysis**:
   - **Key Indicators**:
     - `Delta_Theta_Ratio`, `Theta_HighAlpha_Ratio`, and `Theta_LowAlpha_Ratio` showed potential for distinguishing drowsiness.
   - **Weak Indicators**:
     - Features like Delta, Theta, and the total Alpha, Beta, and Gamma exhibited overlapping distributions between alert and drowsy states.

### Histograms:
- Many features demonstrated **right-skewed distributions**, while some (like `High_Low_Alpha_Diff`) had **bimodal** distributions, indicating the presence of distinct subgroups.
- Features like `Delta_Theta_Ratio` and `Theta_LowAlpha_Ratio` revealed meaningful patterns for differentiating between the two states.

---

## Feature Engineering

### New Features Derived:
- **Theta_LowAlpha_Ratio**: Ratio of Theta and Low Alpha waves.
- **Theta_HighAlpha_Ratio**: Ratio of Theta and High Alpha waves.
- **Delta_Theta_Ratio**: Ratio of Delta and Theta waves.
- **Total_Alpha**: Total Alpha power across all channels.
- **Total_Beta**: Total Beta power across all channels.
- **Total_Gamma**: Total Gamma power across all channels.
- **High_Low_Alpha_Diff**: Difference between High and Low Alpha.
- **High_Low_Beta_Diff**: Difference between High and Low Beta.
- **High_Low_Gamma_Diff**: Difference between High and Low Gamma.

These new features were engineered to capture relationships between the various brainwave activities, aiming to improve the model’s predictive power.

---

## Modeling and Results

After completing the data exploration and cleaning, various machine learning models (e.g., Logistic Regression, Random Forest, SVM) will be trained to classify the data. Evaluation metrics such as accuracy, precision, recall, and F1-score will be used to assess model performance.

---

## Conclusions

The EDA revealed important insights into the distribution of EEG features, class imbalance, and potential indicators for drowsiness. On Day 2, the focus was on understanding these features and planning the next steps in model development and performance evaluation.
