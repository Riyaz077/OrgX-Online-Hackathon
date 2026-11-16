# **OrgX – Online Hackathon**

## AI-Driven Impulsive Spending Risk Detection System

## Project Overview

This project focuses on identifying and analysing impulsive spending behaviour among young adults using transaction-level data and machine learning. The system combines behavioural finance concepts with predictive analytics to identify unusual spending patterns, estimate individual spending risk, and generate personalized financial recommendations. Beyond risk prediction, the project aims to encourage better financial habits through timely and practical interventions.

## Problem Statement

Young adults may develop inconsistent spending habits due to emotional decisions, frequent purchases, late-night transactions, and increased spending towards the end of the month.

These patterns can affect their ability to manage budgets and maintain financial stability.

This project addresses the problem by developing a machine learning-based system that analyses spending behaviour, identifies potential financial risks, and suggests appropriate corrective actions.

## Dataset Information

**Dataset Type:** Synthetic transaction-level dataset

Real-world financial transaction data is generally restricted due to privacy and confidentiality concerns. Therefore, a synthetic dataset was created using assumptions based on common consumer spending patterns.

**Data Generation Approach:**

- Normal distributions were used to simulate average spending behaviour.
- Higher probabilities of impulse purchases were assigned to entertainment, shopping, travel, and food delivery categories.
- Increased spending activity was simulated during late-night hours (10 PM–4 AM).
- Additional spending intensity was introduced towards the end of each month (25th onwards).

## Feature Engineering

The following features were extracted and created to capture different aspects of spending behaviour.

**Time-Based Features**
- Month
- Day
- Hour
- Day of Week
- Late-Night Indicator
- End-of-Month Indicator
- Weekend Indicator

**Behavioural Features**
- Impulse Category Detection
- Impulse Spending Ratio
- Average Spending per User
- Spending Frequency Volatility

**Model-Derived Features**
- Predicted Risk Probability
- Behaviour Cluster Label
- Composite Impulse Risk Score (0–100)

## Machine Learning Models

**1. Random Forest Classifier**

Used to estimate the probability of high-risk impulsive spending.

- Identifies nonlinear relationships in spending patterns.
- Evaluates multiple behavioural and transaction-level features.
- Contributes 40% to the final composite risk score.

**2. K-Means Clustering**

Used to group users according to their spending behaviour.

The model identifies four behavioural profiles:

- Conservative Planner
- Impulsive Night-Owl
- High-Frequency Shopper
- Stable Balanced

**3. Composite Impulse Risk Scoring**

A weighted scoring mechanism combines behavioural indicators and the model's predicted risk probability to generate a score between 0 and 100.

**Risk Score Formula:**

```text
Impulse Risk Score =
    (Impulse Ratio × 0.30) +
    (Late-Night Ratio × 0.20) +
    (Frequency Volatility × 0.10) +
    (Predicted Risk Probability × 0.40)
```

The behavioural inputs are normalized to ensure consistency before calculating the final score.

## Personalized Financial Nudging System

A rule-based recommendation engine generates suggestions based on the user's spending behaviour and calculated risk level.

| Condition | Recommended Intervention |
|---|---|
| Risk Score above 75 | Budget warning |
| High late-night spending | Suggest limiting late-night shopping activity |
| End-of-month spending surge | Recommend automated savings |
 
The purpose of this component is to convert model predictions into practical recommendations that encourage healthier spending habits.

## Key Findings

- Late-night purchases and end-of-month spending patterns are associated with higher impulse risk in the simulated dataset.
- Most users fall within the medium-risk category.
- High-Frequency Shoppers and Impulsive Night-Owls show higher average risk scores.
- The personalized recommendation engine generates interventions based on individual risk patterns.

## Technologies Used

**Programming Language**
- Python

**Data Processing and Analysis**
- Pandas
- NumPy

**Machine Learning**
- Scikit-learn
- Random Forest
- K-Means Clustering

**Data Visualization**
- Matplotlib
- Seaborn

**Development Environment**
- Jupyter Notebook

## Future Scope

- Integration with real-time banking APIs, subject to user consent and data privacy requirements.
- LSTM-based models for sequential spending behaviour analysis.
- Explainable AI techniques using SHAP and LIME.
- Adaptive recommendations based on changing spending habits.
- Integration with personal financial health assessment systems.

## Author

**Mohamed Riyaz S.**  
Integrated M.Tech, Computer Science and Engineering (Business Analytics)  
VIT Chennai
