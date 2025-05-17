# 🧠 Who's at Risk? A Data-Driven Look Into Diabetes Indicators

A visual analytics project built with **Power BI**, **Excel**, and **Python**, exploring how key health indicators relate to diabetes risk levels.  
The dashboard identifies trends and patterns across different BMI categories, age groups, and biometric metrics to better understand which factors most influence diabetes risk.

![Dashboard Preview](Project02.pdf)

---

## 📌 Overview

This dashboard presents a visual analysis of diabetes-related health indicators across BMI categories, age ranges, and risk classifications.  
It explores the **correlation between biometric metrics and diabetes risk**, aiming to uncover high-risk populations based on:

- 🩸 Glucose  
- 💉 Insulin  
- ⚖️ BMI  
- ❤️ Blood Pressure  
- 🧓 Age  

---

## 🧪 Feature Engineering

Several derived fields were created during preprocessing using **Excel** and **Python**:

### 🔹 Risk Classification (based on Glucose)

Glucose values were classified using the following logic:

```excel
=IF(C2<100, "Low", IF(C2<150, "Medium", "High"))

---

## 📊 Key Insights

### 📍 Risk Group Health Profile (Treemap Summary)

| Risk Level | Avg Glucose | Avg Insulin | Avg Age | Avg Blood Pressure |
|------------|-------------|-------------|---------|--------------------|
| **High**   | 171.03      | 202.82      | 38.04   | 76.08              |
| **Medium** | 120.80      | 139.44      | 33.52   | 72.88              |
| **Low**    | 87.22       | 98.23       | 29.14   | 68.63              |

- High-risk individuals have consistently higher **Glucose, Insulin, and Blood Pressure** levels.
- Age also trends higher in the high-risk group (~38 years).
- BMI alone is **not a sufficient predictor**, but is highly correlated with glucose and insulin elevation.

---


### 📍 BMI vs. Health Indicators

Two combined visualizations illustrate how **BMI categories** and **risk groups** influence average indicator values:

- **Obese individuals** in the High Risk group show the **highest levels** of Glucose, Insulin, and Blood Pressure.
- **Even within normal BMI groups**, high glucose and insulin readings are observed in Medium/High Risk classifications.

---

### 📍 Glucose by Age Across Risk Groups

- Glucose levels vary across age in all risk groups, **with no strong upward trend**, indicating that **age alone does not determine glucose elevation**.
- High-risk individuals appear across all age ranges, from 20s to 70s.

---

## 📁 Dataset Description

File: `diabetes_cleaned_final.csv`  
- Missing or implausible zero values were replaced with `NaN`
- Added derived columns:
  - - `Classification`: High, Medium, Low 
  - - `BMI_Category`: Obese, Overweight, Normal, Underweight

| Column Name        | Description |
|--------------------|-------------|
| `Glucose`          | Plasma glucose concentration |
| `Insulin`          | Serum insulin (μU/mL) |
| `BloodPressure`    | Diastolic blood pressure (mm Hg) |
| `BMI`              | Body mass index (kg/m²) |
| `Age`              | Age in years |
| `Pregnancies`      | Derived: Obese / Overweight / Normal / Underweight |
| `SkinThickness`    | Derived: Obese / Overweight / Normal / Underweight |
| `DiabetesPedigreeFunction`     | Derived: Obese / Overweight / Normal / Underweight |
| `Classification`   | Risk Level: High / Medium / Low |

---

## 📊 Tools Used

- **Excel** – Feature engineer
- **Power BI** – Visual analytics and dashboard development
- **Python (pandas, numpy)** – Data preprocessing and cleansing

---

## 📈 Potential Improvements

- Add a custom **Risk Score** formula using weighted indicators
- Apply **KMeans or Decision Tree** for unsupervised / supervised risk classification
- Integrate **behavioral or lifestyle data** (if available) for holistic profiling
- Enable live **web-embedded Power BI report** (via public Power BI service)

---

