# **EEG-Based Drowsiness Detection System for Drivers**

## **Table of Contents**
1. [Introduction](#introduction)
2. [Project Methodology](#project-methodology)
3. [Real-World Application](#real-world-application)
4. [Tools and Technologies](#tools-and-technologies)
5. [Timeline](#timeline)
6. [Limitations and Acknowledgments](#limitations-and-acknowledgments)
7. [Conclusion](#conclusion)
8. [References](#references)

---

## **1. Introduction**

### **1.1 Background**
This project is based on a dataset originally collected by a group of students using the **NeuroSky MindWave EEG sensor**. The dataset includes brainwave signals recorded from drivers in two states: **sleepy** and **not sleepy**. The original project aimed to detect drowsiness in drivers to reduce accidents caused by fatigue. The students used **machine learning algorithms** to classify these states, achieving an accuracy of **82%**. 

This project builds on their work by improving the model’s performance and exploring further applications. The dataset can be accessed on **Kaggle**: [Sleepy Driver EEG Brainwave Data](https://www.kaggle.com/datasets/naddamuhhamed/sleepy-driver-eeg-brainwave-data). Additionally, the original student proposal that details their methodology can be found [here](https://drive.google.com/file/d/1n70BcMPvtGzscGGgcBA8ruXdO0AuEr_v/view).

### **1.2 My Background**
I have a background in **psychology** and **mental health**, and I’m passionate about how **data analysis** and **AI** can solve real-world problems. My experience in **UX/UI design** allows me to create systems that are not only effective but also user-friendly, with a focus on **driver safety** and **autonomous vehicles**.

### **1.3 Project Objective**
This project aims to:
- Preprocess and analyze the **EEG dataset** to classify **sleepy** vs. **not sleepy** states.
- Improve the machine learning models used to predict drowsiness.
- Use **Tableau** to visualize insights from the model.
- Explore real-world applications in **autonomous vehicles** and **wearables** for **driver safety**.

---

## **2. Project Methodology**

### **2.1 Objective**
The goal is to develop a model that predicts whether a driver is **sleepy** or **not sleepy** based on EEG data.

### **2.2 Actions**
- Clean and preprocess the data (handle missing values, remove noise).
- Train machine learning models (e.g., **Random Forest**, **SVM**) to classify drowsiness.
- Visualize results in **Tableau** for easy understanding.

### **2.3 Process**
- **Data Exploration**: Understand the dataset by analyzing EEG features.
- **Model Training**: Apply machine learning algorithms to classify drowsiness.
- **Results**: Evaluate the model’s performance and visualize insights.

---

## **3. Real-World Application**

This project addresses real-world safety concerns related to **drowsy driving**. It can be applied in:
- **Semi-autonomous vehicles**: Monitoring driver alertness and alerting them when they’re too fatigued.
- **Wearables**: Monitoring cognitive states like drowsiness in real-time.

---

## **4. Tools and Technologies**
- **Tableau**: For creating interactive visualizations and dashboards.
- **Kaggle**: For dataset exploration and comparison with other models.
- **R**: For data preprocessing, analysis, and machine learning model development.
- **Google Sheets**: For organizing and reviewing data.
- **SQL**: For querying large datasets if needed.

---

## **5. Timeline**

| **Day** | **Tasks**                                      | **Time (hours)** |
|---------|-----------------------------------------------|-----------------|
| **Day 1** | Data exploration and preprocessing            | 4               |
| **Day 2** | Model development and evaluation              | 4               |
| **Day 3** | Advanced models and insights                  | 4               |
| **Day 4** | Documentation, sharing, and final refinements | 4               |

---

## **6. Limitations and Acknowledgments**

- **Dataset Limitations**: The dataset includes only four drivers, limiting its generalizability.
- **Sensor Limitations**: The **NeuroSky MindWave** uses a single electrode, which provides less data compared to medical-grade multi-electrode EEG systems.
  
**Acknowledgments**: Special thanks to the original student project team for their work in EEG-based drowsiness detection and providing the dataset for further exploration.

---

## **7. Conclusion**

This project uses **EEG data**, **machine learning**, and **data visualization** to address the problem of **drowsy driving**. By improving drowsiness detection models and sharing insights through visualizations, this work contributes to **autonomous vehicle** safety and the development of **wearable devices** for driver alertness monitoring.

---

## **8. References**

- **Dataset**: [Sleepy Driver EEG Brainwave Data - Kaggle](https://www.kaggle.com/datasets/naddamuhhamed/sleepy-driver-eeg-brainwave-data)
- **Original Student Proposal**: [Graduation Project Proposal](https://drive.google.com/file/d/1n70BcMPvtGzscGGgcBA8ruXdO0AuEr_v/view)
- **Google Sheets Data**: [Google Sheets - EEG Data](https://docs.google.com/spreadsheets/d/1v2mqMf1OF_VShRepqr2qyPqbUJO1ix8q0m8wZJq95Hc/edit?gid=1694143717#gid=1694143717)
