# Gym-customers-features-and-churn
# Gym Membership Churn Prediction

![Python](https://img.shields.io/badge/Python-3.10-blue.svg) 
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-1.5-orange.svg) 
![Pandas](https://img.shields.io/badge/Pandas-2.2-yellow.svg) 
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.8-green.svg) 
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-cyan.svg) 
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

A machine learning project to predict **customer churn** in a gym.  
The model analyzes **attendance patterns, lifetime engagement, and additional spending** to identify members at risk of leaving, enabling proactive retention strategies.

---

## **Table of Contents**
1. [Business Objective](#business-objective)
2. [Dataset Overview](#dataset-overview)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Modeling Approach](#modeling-approach)
5. [Model Performance](#model-performance)
6. [Feature Insights](#feature-insights)
7. [Repository Structure](#repository-structure)
8. [Setup & Usage](#setup--usage)
9. [Actionable Recommendations](#actionable-recommendations)
10. [Future Enhancements](#future-enhancements)

---

## **Business Objective**

Customer churn is a major challenge in the fitness industry. Acquiring new members is **5x more expensive** than retaining existing ones.  
**Goal:** Build a predictive model to flag members likely to churn and enable the business to act proactively (offers, trainer outreach, loyalty programs).

---

## **Dataset Overview**

- **Source:** Internal gym management system  
- **Size:** 1,000+ members  
- **Features:** Attendance frequency, membership lifetime, additional charges  
- **Target Variable:** `Churn` (1 = Dropped out, 0 = Active)

### **Feature Description**

| Feature | Description |
|---------|-------------|
| `Avg_class_frequency_total` | Average number of classes attended during full membership |
| `Avg_class_frequency_current_month` | Average attendance during current month |
| `Lifetime` | Total duration of membership (months) |
| `Avg_additional_charges_total` | Additional spending on extra services |
| `Churn` | Target variable (1 = dropout, 0 = active) |

---

## **Exploratory Data Analysis (EDA)**

Key findings from visual and statistical analysis:

- **Skewed distributions:** Attendance and lifetime features are left-skewed (many loyal members).  
- **Churn correlation:** Low current attendance and short membership duration strongly indicate churn.  
- **Feature relationships:** Strong correlation between total and current attendance frequency.

---

## **Modeling Approach**

### **Steps**
1. Data preprocessing (scaling, encoding if needed).
2. Tested multiple classifiers:
   - Logistic Regression
   - Decision Tree
   - Random Forest
   - Support Vector Machine (SVM)
3. Evaluation using **3-Fold Cross Validation** (Accuracy metric).
4. Selected **Random Forest** as final model (best accuracy + interpretability).

---

## **Model Performance**

### **Cross-Validation Accuracy**

| Model               | Accuracy |
|---------------------|----------|
| Logistic Regression | 90.5%    |
| Decision Tree       | 88.8%    |
| Random Forest       | **91.7%**|
| SVM                 | 90.9%    |

### **ROC Curve Example**
![ROC Curve](images/roc_curve.png)

---

## **Feature Insights**

- **Lifetime (0.329)** → Strongest predictor (longer members = less churn).  
- **Current Month Attendance (0.279)** → Recent engagement crucial to retention.  
- **Total Attendance (0.263)** → Historical consistency matters.  
- **Additional Charges (0.128)** → Extra spending adds minor predictive power.

---

## **Repository Structure**

gym-churn-prediction/
├── data/
│ └── gym_members.csv
├── notebooks/
│ └── churn_model.ipynb
├── reports/
│ └── Gym_Customer_Churn_Report.docx
├── images/
│ └── roc_curve.png
├── README.md
└── requirements.txt


---

## **Setup & Usage**

### **1. Clone the Repository**
bash
git clone https://github.com/YOUR_USERNAME/gym-churn-prediction.git
cd gym-churn-prediction


 Install Dependencies
bash
Copy
Edit


Actionable Recommendations
Targeted retention campaigns: Focus on members with low attendance this month.

Proactive trainer outreach: Contact members with short lifetime or low engagement.

Upsell opportunities: High spenders may respond positively to premium offers.

Future Enhancements
Add more features: payment history, class preferences, demographics.

Deploy model as API for real-time churn scoring.

Automate weekly churn risk dashboard for gym managers.

