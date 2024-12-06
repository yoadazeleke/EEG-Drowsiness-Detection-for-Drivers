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

Here's an organized version of your analysis with visuals for the README:

---

## 1. **Skewed Distributions**:
   - Most features, including **Delta**, **Theta**, **LowAlpha**, **HighAlpha**, **LowBeta**, **HighBeta**, **LowGamma**, and **HighGamma**, exhibited skewed distributions. A significant number of values were clustered at the lower end of the scale, showing the need for potential data transformations like normalization or scaling.

## 2. **Class Imbalance**:
   - The classification variable (**Sleepy/Not Sleepy**) showed a slight imbalance. There were more "Not Sleepy" samples than "Sleepy," which might influence the classification model's performance. Techniques like oversampling or undersampling could be considered to address this imbalance.

## 3. **Derived Features**:
   - Derived ratios like `Theta_LowAlpha_Ratio`, `Theta_HighAlpha_Ratio`, and `Delta_Theta_Ratio` demonstrated significant skewness, with median values lower than their means, which may indicate outliers or a skewed distribution towards lower values.

## 4. **Box Plot Analysis**:
   ### **Key Indicators**:
   - Ratios such as **`Delta_Theta_Ratio`**, **`Theta_HighAlpha_Ratio`**, and **`Theta_LowAlpha_Ratio`** showed potential for distinguishing between drowsy and alert states. These features may serve as better predictors for classifying the **Sleepy/Not Sleepy** states.

   ### **Weak Indicators**:
   - Features like **Delta**, **Theta**, and the total **Alpha**, **Beta**, and **Gamma** bands showed overlapping distributions between alert and drowsy states. These features alone may not be strong indicators for predicting the classification variable.

---

### **Visualizations: Box Plots**:

#### Key Features:
- **Delta_Theta_Ratio**  
  ![boxplot_Delta_Theta_Ratio](https://github.com/user-attachments/assets/a6050b8b-aaf4-4b52-a5ba-fe7faed68d1e)

- **Theta_HighAlpha_Ratio**  
  ![boxplot_Theta_HighAlpha_Ratio](https://github.com/user-attachments/assets/7574c79f-1155-45bf-9332-3d651d0c5413)

- **Theta_LowAlpha_Ratio**  
  ![boxplot_Theta_LowAlpha_Ratio](https://github.com/user-attachments/assets/09a62966-16fd-4d3a-a41c-0da81288f6f6)

#### Weak Indicators:
- **Delta**  
  ![boxplot_delta](https://github.com/user-attachments/assets/b9657e1c-ea8a-40e8-a7ad-6264c20dec31)

- **Theta**  
  ![boxplot_theta](https://github.com/user-attachments/assets/a3682857-0fc2-446d-8da4-a466a8c6794f)

- **Alpha (Total)**  
  ![boxplot_Total_Alpha](https://github.com/user-attachments/assets/afe73c6a-26cf-4a5e-ad1f-3ba6186dd617)

- **Beta (Total)**  
  ![boxplot_Total_Beta](https://github.com/user-attachments/assets/2a42b645-944e-4a83-baf7-31b82498e384)

- **Gamma (Total)**  
  ![boxplot_Total_Gamma](https://github.com/user-attachments/assets/e0f70eb3-9c5c-4857-aa8f-28f924926256)

#### Additional Derived Features:
- **LowAlpha**  
  ![boxplot_lowAlpha](https://github.com/user-attachments/assets/ff3ebcc9-92e5-48cb-93c1-eb3989fdf5bf)

- **LowBeta**  
  ![boxplot_lowBeta](https://github.com/user-attachments/assets/ec8352b4-f7cb-4fbc-9b5e-fc5c0b016e88)

- **LowGamma**  
  ![boxplot_lowGamma](https://github.com/user-attachments/assets/1b51fa81-b44c-4324-8c1b-cd064de82850)

- **HighAlpha**  
  ![boxplot_highAlpha](https://github.com/user-attachments/assets/cd9f761d-1c0c-472a-a7f7-481d62500218)

- **HighBeta**  
  ![boxplot_highBeta](https://github.com/user-attachments/assets/5aa3c2a9-b727-48dd-bf46-77acfea6d5bc)

- **HighGamma**  
  ![boxplot_highGamma](https://github.com/user-attachments/assets/e7f8b71e-8f32-4a96-a079-e458f52c9dd3)

#### Delta and Gamma Differences:
- **High_Low_Gamma_Diff**  
  ![boxplot_High_Low_Gamma_Diff](https://github.com/user-attachments/assets/5b0deaae-621d-4c5a-a972-c63c9d66866e)

- **High_Low_Beta_Diff**  
  ![boxplot_High_Low_Beta_Diff](https://github.com/user-attachments/assets/3fb3523c-b382-4acf-9dfd-d7a03c23427a)

- **High_Low_Alpha_Diff**  
  ![boxplot_High_Low_Alpha_Diff](https://github.com/user-attachments/assets/bdc92888-c138-48e2-8e28-db8c8d07b89d)
---

### **Histograms Analysis:**

#### **Key Observations:**
1. **Right-Skewed Distributions:**
   - Many features, such as **Delta**, **Theta**, and various ratios (e.g., **Theta_LowAlpha_Ratio**, **Delta_Theta_Ratio**), show **right-skewed distributions**. This indicates that most values are concentrated toward the lower end, with some outliers stretching toward higher values.
   
2. **Bimodal Distributions:**
   - Some features, such as **High_Low_Alpha_Diff**, display **bimodal distributions**, suggesting the presence of distinct subgroups within the dataset.
   
3. **Key Patterns:**
   - Features like **Delta_Theta_Ratio** and **Theta_LowAlpha_Ratio** exhibit meaningful patterns that could help distinguish between **Sleepy** and **Not Sleepy** states.

---

#### **Histograms:**

- **Normalized Theta:**
  ![normalized_theta](https://github.com/user-attachments/assets/319ffb19-fa87-4563-ab79-b574572ea59a)

- **Normalized LowGamma:**
  ![normalized_lowgamma](https://github.com/user-attachments/assets/1e13de7f-bef8-4f8a-bd47-76e417baf31a)

- **Normalized LowBeta:**
  ![normalized_lowbeta](https://github.com/user-attachments/assets/0129d469-52af-419f-ba6f-7164970b2518)

- **Normalized LowAlpha:**
  ![normalized_lowalpha](https://github.com/user-attachments/assets/995bf716-6321-4210-8757-db01e7de0161)

- **Normalized LowAlpha_Ratio:**
  ![normalized_lowalpha_ratio](https://github.com/user-attachments/assets/7269e36c-d135-4023-9386-150697cd1d1d)

- **Normalized HighGamma:**
  ![normalized_highgamma](https://github.com/user-attachments/assets/8dad061d-a97d-4093-9346-62165f580836)

- **Normalized HighBeta:**
  ![normalized_highbeta](https://github.com/user-attachments/assets/c206dc9f-efa6-40b6-9902-ac0b2da3f2c1)

- **Normalized HighAlpha:**
  ![normalized_highalpha](https://github.com/user-attachments/assets/4e7f0718-65ab-4e62-b4ce-3f291d3e6734)

- **Normalized Delta:**
  ![normalized_delta](https://github.com/user-attachments/assets/4476fbef-92b2-4211-9234-88b6a24b7dde)

- **High-Low Gamma Difference:**
  ![highlow_gamma_diff](https://github.com/user-attachments/assets/f98ef3ba-543f-41ec-ae43-cf5f83847455)

- **High-Low Beta Difference:**
  ![highlow_beta_diff](https://github.com/user-attachments/assets/a27f25a7-3b92-4720-b138-c18a8ae92f0c)

- **High-Low Alpha Difference:**
  ![high_low_alphadiff](https://github.com/user-attachments/assets/f3dd2786-f5ae-484a-ac13-be1719a25664)

- **Delta-Theta Ratio:**
  ![delta_theta_ration](https://github.com/user-attachments/assets/e3496b23-08c8-4cbf-a082-144175817ca4)

---

This structure ensures clarity and highlights your findings while maintaining the flow of the analysis and making it easy for anyone viewing your GitHub to follow along.
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
The analysis indicated that certain features like the Delta_Theta_Ratio and Theta-based ratios could be valuable for distinguishing between sleepy and not sleepy states. The box plot and histogram analyses showed that while some features were more discriminative, others showed significant overlap, which may require further feature engineering or transformations to improve classification performance.

The EDA revealed important insights into the distribution of EEG features, class imbalance, and potential indicators for drowsiness. On Day 2, the focus was on understanding these features and planning the next steps in model development and performance evaluation.
