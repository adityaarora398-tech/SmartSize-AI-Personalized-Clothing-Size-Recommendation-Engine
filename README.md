# SmartSize AI — Personalized Clothing Size Recommendation

> **AI-powered apparel size recommendation using supervised machine learning to improve sizing confidence and reduce size-related returns in online fashion retail.**

---

## 📌 Overview

**SmartSize AI** is a machine learning-based clothing size recommendation system designed for e-commerce fashion platforms.

Online shoppers cannot physically try garments before purchasing, while sizing can vary across brands and product categories. This creates sizing uncertainty, which can contribute to returns, customer dissatisfaction, and abandoned purchases.

SmartSize AI addresses this problem by predicting a customer's most suitable clothing size using customer characteristics, previous purchasing behavior, and product-related attributes.

The project implements a **Random Forest Classifier** to predict one of six size categories:

**XS · S · M · L · XL · XXL**

---

## 🎯 Problem Statement

Traditional online size charts provide generic recommendations and may not account for individual customer characteristics or previous shopping behavior.

The goal of SmartSize AI is to build a personalized prediction system that can recommend a suitable apparel size based on available customer and product information.

### Business Objectives

* Reduce size-related product returns
* Improve customer sizing confidence
* Support personalized shopping experiences
* Improve potential conversion
* Generate actionable sizing insights
* Support better inventory and catalog decisions

---

## 🧠 Machine Learning Approach

This project treats clothing-size recommendation as a **supervised classification problem**.

### Model

**Random Forest Classifier**

Random Forest was selected because it can work with a combination of numerical and categorical input features and provides feature-importance information for interpretation.

### Prediction Classes

| Class | Size |
| ----- | ---- |
| 0     | XS   |
| 1     | S    |
| 2     | M    |
| 3     | L    |
| 4     | XL   |
| 5     | XXL  |

---

## 📊 Dataset

The project uses a **synthetic dataset created for academic purposes**. No real Myntra or customer data was used.

### Dataset Statistics

| Attribute        | Value |
| ---------------- | ----: |
| Total records    | 2,500 |
| Training records | 2,000 |
| Test records     |   500 |
| Input features   |    10 |
| Target classes   |     6 |

### Input Features

The model uses signals including:

* Age
* Gender
* Height (cm)
* Weight (kg)
* Previous Size
* Brand
* Category
* Fit Preference
* Previous Purchases
* Previous Returns

---

## 🔄 ML Pipeline

```text
Customer + Product Data
          ↓
   Exploratory Analysis
          ↓
      Data Cleaning
          ↓
     Preprocessing
          ↓
  Train / Test Split
          ↓
 Random Forest Training
          ↓
      Evaluation
          ↓
 Size Recommendation
```

The workflow follows the stages of EDA, cleaning, preprocessing, an 80/20 stratified split, and Random Forest model training.

---

## ⚙️ Model Configuration

```text
Algorithm       : Random Forest Classifier
Estimators      : 100
Class Weight    : Balanced
Random State    : 42
Train/Test Split: 80/20
```

---

## 📈 Model Performance

The model achieved:

| Metric            |    Result |
| ----------------- | --------: |
| Training Accuracy |      100% |
| Test Accuracy     | **62.4%** |

The presentation notes that the 100% training accuracy indicates potential overfitting, while the **62.4% test accuracy** represents performance on unseen data.

### Classification Performance

| Size | Precision | Recall |   F1 |
| ---- | --------: | -----: | ---: |
| XS   |      0.00 |   0.00 | 0.00 |
| S    |      0.59 |   0.26 | 0.36 |
| M    |      0.65 |   0.77 | 0.70 |
| L    |      0.54 |   0.60 | 0.57 |
| XL   |        0. |        |      |
