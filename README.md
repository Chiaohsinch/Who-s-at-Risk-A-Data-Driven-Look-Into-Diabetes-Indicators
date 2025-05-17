# 🧠 Who's at Risk? A Data-Driven Look Into Diabetes Indicators

A visual analytics project built using **Power BI**, **Excel**, and **Python** to explore how key health indicators relate to diabetes risk levels.  
This dashboard identifies trends and patterns across BMI categories, age groups, and biometric metrics to better understand which factors most influence diabetes risk.

📄 **[Dashboard Preview (PDF)](Project02.pdf)**

Data Source: The dataset used in this analysis was obtained from Kaggle.
Diabetes-Dashboard-Power BI - available at: [https://www.kaggle.com/datasets/aryanpatel0204/diabetes-dashboard-power-bi]

---

## 📌 Overview

This project presents a visual analysis of diabetes-related health metrics categorized by BMI, age range, and risk levels.  
It aims to uncover **high-risk populations** based on the following biometric indicators:

- 🩸 Glucose  
- 💉 Insulin  
- ⚖️ BMI  
- ❤️ Blood Pressure  
- 🧓 Age  

---

## 🧪 Feature Engineering

Several derived fields were created during preprocessing using **Excel** and **Python**:

### 🔹 Risk Classification (Based on Glucose)

Glucose values were segmented into three risk levels using clinical thresholds:

```excel
=IF(C2 < 100, "Low", IF(C2 < 150, "Medium", "High"))
```

### 🔹 BMI Category (Based on WHO Standards)

| Category      | BMI Range (kg/m²) |
|---------------|-------------------|
| Underweight   | < 18.5            |
| Normal        | 18.5 – 24.9       |
| Overweight    | 25 – 29.9         |
| Obese         | ≥ 30              |

---

## 📊 Key Insights

### 📍 Risk Group Health Profile (Treemap Summary)

| Risk Level | Avg Glucose | Avg Insulin | Avg Age | Avg Blood Pressure |
|------------|-------------|-------------|---------|--------------------|
| **High**   | 171.03      | 202.82      | 38.04   | 76.08              |
| **Medium** | 120.80      | 139.44      | 33.52   | 72.88              |
| **Low**    | 87.22       | 98.23       | 29.14   | 68.63              |

- High-risk individuals show elevated **glucose**, **insulin**, and **blood pressure** levels.
- **Age** trends higher in the high-risk group (~38 years).
- **BMI** correlates with glucose/insulin but is not always a definitive risk predictor.

---

### 📍 BMI vs. Health Indicators

Visualizations show how BMI categories intersect with risk classifications:

- **Obese individuals** in the high-risk group exhibit the highest glucose, insulin, and blood pressure levels.
- Even within **normal BMI** groups, some individuals show elevated biometric risk, indicating BMI alone is insufficient for risk detection.

---

### 📍 Glucose by Age Across Risk Groups

- Glucose levels vary with age, but **no strong upward trend** is observed.
- High-risk individuals appear across all age ranges, from 20s to 70s, suggesting **age is not the sole determinant** of risk.

---

## 📁 Dataset Description

**File**: `diabetes_cleaned_final.csv`

Preprocessing steps:
- Replaced missing or implausible zero values with `NaN`
- Added derived fields for classification and BMI category

| Column Name              | Description                                       |
|--------------------------|---------------------------------------------------|
| `Glucose`                | Plasma glucose concentration                      |
| `Insulin`                | Serum insulin (μU/mL)                             |
| `BloodPressure`          | Diastolic blood pressure (mm Hg)                 |
| `BMI`                    | Body mass index (kg/m²)                           |
| `Age`                    | Age in years                                      |
| `Pregnancies`            | Number of pregnancies                             |
| `SkinThickness`          | Triceps skinfold thickness                        |
| `DiabetesPedigreeFunction` | Genetic predisposition score                    |
| `Classification`         | Risk Level: High / Medium / Low (derived)         |
| `BMI_Category`           | Obese / Overweight / Normal / Underweight (derived) |

---

## 🛠️ Tools & Technologies

- **Python** (`pandas`, `numpy`) – Data cleansing & preprocessing  
- **Excel** – Feature engineering & early transformations  
- **Power BI** – Dashboard creation & visual storytelling  

---

## 🚀 Potential Improvements

- Implement a **custom risk score** using weighted combinations of indicators  
- Use **KMeans clustering** or **decision tree models** for risk stratification  
- Integrate **lifestyle or behavioral data** for a more comprehensive profile  
- Deploy an interactive **Power BI Web App** for real-time exploration  
