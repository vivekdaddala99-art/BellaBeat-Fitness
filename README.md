# BellaBeat-Fitness
A comprehensive business report with recommendations for BellaBeat that improve BellaBeat's app user retention and engagement

# 🏃‍♂️ Balancing Activity and Recovery: An Analysis of Step Count and Sleep Efficiency

## 📌 1. Objective

The objective of this analysis is to explore the relationship between physical activity (measured by total steps) and sleep quality (measured by sleep efficiency). The study aims to identify behavioural patterns and determine whether increased activity levels contribute to improved or diminished sleep quality.

---

## 📊 2. Data Description

The analysis uses multiple datasets capturing user activity and sleep behaviour:

* **Daily Activity Data**: Total steps and calories burned per user
* **Minute-Level Sleep Data**: Sleep states recorded at a minute-level granularity
* **User Identifier (Id)**: Used to link datasets

The sleep dataset includes categorical values representing sleep states:

* `1` → Asleep
* `2` → Restless
* `3` → Awake

---

## 🛠️ 3. Data Preparation

### 3.1 Data Cleaning

* Converted timestamp columns using `pd.to_datetime()` to ensure consistency
* Extracted date-level information for alignment

### 3.2 Data Aggregation

* Sleep data was aggregated from minute-level to daily/session-level
* Total sleep duration and sleep state counts were computed per user

### 3.3 Feature Engineering

Sleep efficiency was calculated as:

[
\text{Sleep Efficiency} = \frac{\text{Minutes Asleep}}{\text{Total Minutes (Asleep + Restless + Awake)}}
]

### 3.4 Data Merging

* Activity and sleep datasets were merged at a consistent granularity (user and date level)
* Validation checks confirmed:

  * No missing values
  * No unintended duplication

---

## 🧠 4. User Segmentation

Users were segmented based on **total step counts**:

| Activity Group | Description            |
| -------------- | ---------------------- |
| Low            | Least active users     |
| Moderate       | متوسط activity         |
| High           | Highly active users    |
| Very High      | Extremely active users |

This segmentation enables comparison of behavioural patterns across different activity levels.

---

## 📈 5. Analysis & Findings

### 5.1 Correlation Analysis

A correlation of **-0.41** was observed between total steps and sleep efficiency.

**Interpretation:**

* Indicates a moderate negative relationship
* Suggests that higher activity levels may be associated with slightly lower sleep efficiency

---

### 5.2 Sleep Efficiency by Activity Group

| Activity Group | Avg Sleep Efficiency | Count |
| -------------- | -------------------- | ----- |
| Low            | 0.9317               | 834   |
| Moderate       | 0.9326               | 1677  |
| High           | 0.8944               | 2727  |
| Very High      | 0.9061               | 309   |

---

### 5.3 Key Observations

#### 🔹 1. Optimal Activity Level

Moderate activity users exhibit the **highest sleep efficiency**, suggesting an optimal balance between physical exertion and recovery.

#### 🔹 2. Decline at Higher Activity Levels

Users in the **High activity group show a noticeable decrease** in sleep efficiency, indicating potential overexertion or reduced recovery quality.

#### 🔹 3. Non-Linear Relationship

The relationship between activity and sleep is **not linear**:

* Sleep improves from Low → Moderate
* Then declines from Moderate → High

#### 🔹 4. Dataset Distribution Insight

* Majority of users fall into the **High activity group**, making this finding statistically reliable
* The **Very High group** has fewer users and should be interpreted cautiously

---

## 💡 6. Business Insights

* Increased activity does not necessarily lead to better sleep quality
* Moderate activity appears to provide the best balance for recovery
* Excessive activity may negatively impact sleep efficiency

---

## 🚀 7. Recommendations

### ✅ 1. Promote Balanced Activity Levels

Encourage users to maintain **moderate activity levels** for optimal health outcomes.

### ✅ 2. Integrate Recovery Metrics

Fitness applications should:

* Monitor sleep alongside activity
* Provide alerts for potential overtraining

### ✅ 3. Personalised Fitness Insights

Develop user-specific recommendations based on:

* Activity levels
* Sleep quality trends

---

## ⚠️ 8. Limitations

* Sleep data is inferred from wearable devices and may contain measurement inaccuracies
* External factors (diet, stress, lifestyle) are not included
* The Very High activity group has a relatively small sample size

---

## 🧭 9. Conclusion

This analysis highlights a **trade-off between activity intensity and sleep quality**. While moderate physical activity is associated with optimal sleep efficiency, higher activity levels may slightly reduce sleep quality.

These findings emphasize the importance of balancing **activity and recovery** to achieve overall well-being.

---

## 📌 10. Tools & Technologies

* Python (Pandas, NumPy)
* Data Visualization (Matplotlib, Seaborn)
* Jupyter Notebook / Google Colab

---

## ⭐ Project Value

This project demonstrates:

* Data cleaning and preprocessing
* Multi-source data merging
* Feature engineering
* User segmentation
* Behavioural analytics
* Insight generation with business relevance

---
