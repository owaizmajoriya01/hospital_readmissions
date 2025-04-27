
# 🩺 Predicting Hospital Readmissions Using Dataiku & MicroStrategy

> **End-to-End Healthcare Machine Learning Project**  
> By [Owaiz Majoriya]

---

## 📑 Project Overview

Hospital readmissions are a major healthcare concern, leading to increased healthcare costs and poorer patient outcomes.  
This project focuses on predicting whether a patient is likely to be readmitted to a hospital within 30 days, after 30 days, or not at all, based on their demographic, medical, and treatment-related features.

The project follows the complete data science life cycle:
- Data ingestion and cleaning
- Feature engineering
- Predictive modeling
- Model evaluation
- Business intelligence dashboarding

---

## 🛠️ Tools and Technologies Used

| Tool | Purpose |
|:---|:---|
| **Dataiku DSS** | Data preparation, feature engineering, model training, scoring |
| **Python (pandas)** | Data sampling and file optimization for deployment |
| **MicroStrategy AutoExpress** | Business Intelligence dashboard and data visualization |
| **Jupyter Notebook (optional)** | Data verification and sampling |
| **GitHub** | Project hosting and portfolio building |

---

## 📦 Dataset Information

- Dataset Name: **Diabetes Hospital Readmission Data**
- Size: ~28MB initially (sampled to 14MB for BI tool compatibility)
- Records: ~100,000 patients
- Attributes: 50+ including demographics, diagnoses, medications, hospital encounters, and readmission outcomes.
- Target Variable: **readmitted** (`<30`, `>30`, `NO`)

---

## 🧹 Data Preparation

Performed using **Dataiku DSS**:
- Replaced missing values (`?`) with `"Unknown"` for fields like `weight`, `payer_code`, and `medical_specialty`.
- Dropped unnecessary columns like encounter IDs and detailed medication names to optimize dataset size.
- Ensured correct data types for modeling.

---

## 🧠 Feature Engineering

- **Age Bucketing:** Converted raw age ranges into numerical buckets for better model interpretability.
- **Total Prior Visits:** Created a new feature summing inpatient, outpatient, and emergency visits to capture patient history strength.
  
New Columns:
- `age_bucket`
- `total_prior_visits`

---

## 🤖 Model Building

### Models Trained:

| Algorithm | Status | Notes |
|:---|:---|:---|
| Logistic Regression | ❌ | Training failed locally due to Mac M1 chip architecture mismatch |
| Random Forest | ✅ | Successfully trained in Dataiku Cloud (Trial Version) |
| Decision Tree | ✅ | Successfully trained as a backup simpler model |

---

### 🔥 Why Random Forest?

- Random Forest was selected because:
  - It handles **categorical and numerical variables** very well.
  - It is **robust against overfitting** compared to simple Decision Trees.
  - It provides **feature importance scores**, allowing interpretability.
  - It handles **imbalanced datasets** better when predicting minority classes (`<30` readmissions).

---

## 📈 Model Evaluation Metrics

- **ROC AUC Score (Random Forest):** 0.653
- **ROC AUC Score (Decision Tree):** 0.636
- **Confusion Matrix, Precision, Recall** were evaluated inside Dataiku AutoML Lab.
- Feature Importance was extracted for top influencing factors.

---

## 📊 Dashboarding in MicroStrategy

After prediction, results were visualized in **MicroStrategy AutoExpress**:

- 📊 **Bar Chart**: Probability of Readmission by Age Buckets
- 🥧 **Pie Chart**: Distribution of Readmissions (`<30 days`, `>30 days`, `No Readmission`)
- 📈 **Top Admission Sources** leading to early readmissions (Top 5 filtered)
- 📋 **Detailed Demographic Grids**: Gender, Race, Age vs Readmission probability

Final dashboard PDF attached!

---

## 📁 Project Folder Structure (Recommended)

```
/diabetes-readmission-prediction/
│
├── /data/
│    └── diabetic_data_prepared_scored_reduced.csv
│
├── /images/
│    ├── flow_screenshot.png
│    ├── model_training_screenshot.png
│    ├── microstrategy_dashboard.png
│
├── /notebooks/ (optional)
│    └── sampling_script.ipynb
│
├── README.md
├── dashboard_report.pdf (MicroStrategy dashboard export)
```

---

## 📝 Final Deliverables

- Cleaned and Scored Dataset
- Trained Random Forest Model
- Evaluation Metrics
- Interactive BI Dashboard
- GitHub Repository

---

## 👤 About Me

**Owaiz Majoriya**  
Aspiring Data Scientist | Machine Learning Enthusiast | Business Intelligence Developer

---

## 🚀 Future Work (Optional Enhancements)

- Tune hyperparameters of Random Forest using grid search.
- Try XGBoost / LightGBM models.
- Build Predictive Monitoring Dashboards in MicroStrategy.
- Deploy the scoring pipeline in real-time using Dataiku API nodes.

---

## 📢 Important Notes

- This project was partially trained on a Mac M1 machine initially.  
- Due to native architecture restrictions (ARM vs x86_64), modeling was shifted to **Dataiku Cloud (Trial Version)** successfully.
- MicroStrategy upload required **sampling down** to 14MB file size.
  
✅ Full project completed end-to-end using best practices.

---

## 🏆 Special Thanks

Special thanks to Dataiku and MicroStrategy for providing free trial environments for project building.

---

## 🎯 Key Skills Demonstrated

- Data Cleaning
- Feature Engineering
- AutoML
- Predictive Modeling
- Model Evaluation
- Business Intelligence Dashboarding
- Professional Project Management

---

## 🔗 Links
- [GitHub Repository] (Add Link here after you create repo)
- [Dashboard Report PDF] (Attach in repo)

---

## ✅ Status
> **Project Completed: April 2025**  
