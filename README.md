# 🏭 Industrial IoT Predictive Maintenance

AI system that predicts industrial machine failures **before** they happen, using IoT sensor data and Machine Learning. The system reduces maintenance costs by an estimated **75.8%** by enabling predictive maintenance instead of reactive maintenance.

---

## 📊 Dataset

- **Source:** AI4I 2020 Predictive Maintenance Dataset (UCI ML Repository)
- **Samples:** 10,000 rows × 14 columns
- **Target:** Machine failure (binary classification)
- **Challenge:** Highly imbalanced (96.6% normal, 3.4% failures)

---

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn, XGBoost, Imbalanced-learn (SMOTE), SHAP, Matplotlib, Seaborn
- **Environment:** Google Colab

---

## 🚀 Methodology

### 1. Exploratory Data Analysis (EDA)
- Target distribution analysis (imbalanced dataset detected)
- Failure modes breakdown (TWF, HDF, PWF, OSF, RNF)
- Correlation analysis between features and target

### 2. Feature Engineering
Created 5 physics-based features:
- **Temp_Difference:** Process temperature - Air temperature
- **Power_W:** Torque × Angular velocity (mechanical power)
- **Tool_Stress:** Tool wear × Torque
- **Wear_per_RPM:** Wear ratio per rotation
- **Thermal_Load:** Temperature diff × Power

### 3. Handling Imbalanced Data
- Applied **SMOTE** to balance classes in the training set
- Used **F1-Score** and **Recall** as primary metrics

### 4. Models Trained

| Model | F1-Score | ROC-AUC | Recall |
|-------|----------|---------|--------|
| Logistic Regression | 0.30 | 0.936 | 0.87 |
| Random Forest | 0.69 | 0.986 | 0.85 |
| **XGBoost (Best)** | **0.72** | **0.981** | **0.79** |

### 5. Model Interpretation (SHAP)
Top features driving failure predictions:
1. Tool wear [min]
2. Rotational speed [rpm]
3. Power_W
4. Temp_Difference
5. Tool_Stress

### 6. Anomaly Detection
Applied **Isolation Forest** for unsupervised anomaly detection to catch unknown failure patterns.

---

## 💰 Business Impact

| Scenario | Annual Cost |
|----------|-------------|
| Without AI (Reactive) | ~41.4M EGP |
| With AI (Predictive) | ~10.0M EGP |
| **Savings** | **~31.4M EGP (75.8%)** |

---

## 📁 Files

- `Untitled30.ipynb` — Full analysis notebook (EDA, feature engineering, SMOTE, model training, SHAP, business impact)
- `Predictive_Maintenance_Report.docx` — Detailed technical report
- `Predictive_Maintenance_Smart_Factory.pptx` — Presentation slides

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/ousef2312/Industrial-IoT-Predictive-Maintenance.git
