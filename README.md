
# AI for Attendance: Understanding No-Shows in Maternal Virtual Visits

A data science portfolio project exploring maternal telehealth appointment attendance through synthetic healthcare data, exploratory data analysis, natural language processing, and predictive machine learning.

This project documents both the technical development process and the methodological decisions made as the research evolved.

> **Data Privacy:** This project uses entirely synthetic patient and appointment data. No real patient records or protected health information are included.

---

## 📌 Project Overview

### Original Research Objective

The original goal of this project was to investigate whether predictive analytics and targeted interventions could reduce maternal telehealth appointment no-show rates from approximately **20% to 3–5%**.

However, exploratory analysis revealed an unexpected finding: the original synthetic dataset already exhibited a **3.19% no-show rate**, falling within the intended improvement target before any interventions were applied.

This discrepancy prompted a separate data adjustment investigation.

Rather than modifying the original data to support the initial research assumptions, I evaluated the implications of resampling and ultimately elected to preserve the original dataset.

### Revised Research Direction

The project now focuses on:

- Investigating characteristics associated with missed maternal telehealth appointments.
- Developing predictive models to identify appointments at increased risk of no-show.
- Exploring structured patient and appointment features alongside simulated patient messages.
- Evaluating classification performance in the presence of substantial class imbalance.
- Documenting methodological limitations and opportunities for future intervention research.

**The objective is to investigate predictive risk, not to claim an intervention-driven reduction that the original dataset cannot demonstrate.**

---

## 🧩 Project Update — November 2026

### 🔍 Data Adjustment & Research Design Evaluation

Following the initial data generation, cleaning, and exploratory analysis phases, I revisited the original research objective and evaluated whether the synthetic dataset supported the intended experimental design.

The original dataset contained **10,150 appointments**, including **324 no-shows (3.19%)**.

Because the intended starting baseline was approximately 20%, I investigated whether resampling could establish the proposed distribution without compromising data integrity.

### 🧠 Tasks Completed

- Validated the original appointment outcome distribution.
- Confirmed that the original dataset contained 10,150 records and zero exact duplicate observations.
- Defined an experimental distribution of 65% Show, 20% No-Show, 10% Cancelled, and 5% Scheduled.
- Applied upsampling and downsampling using `sklearn.utils.resample`.
- Verified that the experimental dataset achieved the intended numerical proportions.
- Compared total observations, duplicate records, and unique patient identifiers.
- Identified 2,496 duplicate observations in the resampled dataset.
- Evaluated the implications of using repeated records to simulate a higher no-show baseline.
- Documented the decision to preserve the original cleaned dataset.

### 📊 Validation Results

| Metric | Original Dataset | Resampled Dataset |
|---|---:|---:|
| Total observations | 10,150 | 10,149 |
| Unique observations | 10,150 | 7,653 |
| Duplicate observations | 0 | 2,496 |
| Unique patient IDs | 10,150 | 7,653 |
| No-show rate | 3.19% | ~20% |

The resampling experiment successfully reproduced the intended numerical distribution.

However, upsampling introduced repeated observations rather than generating new independent patient appointments.

The resulting dataset therefore did not establish an independent population with the higher baseline required by the original intervention research objective.

### ✅ Methodological Decision

**I elected to retain the original cleaned dataset without modifying patient identifiers, appointment outcomes, or patient records.**

Although resampling is a legitimate technique for addressing class imbalance during machine learning training, it was not an appropriate substitute for independently simulating the higher-risk population required by my original research objective.

The experimental resampled dataset will not be used as an independent evaluation population.

The original cleaned dataset, `maternal_telehealth_data_clean.csv`, will serve as the source for subsequent predictive modeling.

### 💡 Key Takeaway

This investigation reinforced the importance of validating a dataset against the research question before attempting to modify it.

Achieving a desired numerical distribution does not necessarily establish that a dataset is methodologically appropriate for the intended analysis.

Rather than force the data to conform to the original hypothesis, I chose to document the discrepancy, preserve data integrity, and adapt the subsequent research direction.

### 📂 Output

- [Data Adjustment & Research Design Evaluation](maternal_telehealth_data_adjustment.ipynb)
- Original and experimental outcome distribution visualizations
- Data integrity comparison and duplicate validation
- Documented methodological decision and research reflection

### 🚀 Next Phase: Predictive Modeling

The next phase will investigate whether the original dataset can support meaningful no-show risk predictions despite the relatively small minority class.

Planned tasks include:

- Defining the prediction target and prediction time.
- Identifying potentially outcome-dependent features and target leakage.
- Preparing independent training and testing datasets.
- Establishing baseline classification models.
- Comparing class weighting and training-only resampling where appropriate.
- Evaluating performance using precision, recall, F1-score, and precision-recall AUC.
- Investigating potentially actionable predictors of missed appointments.

The original 20%-to-3–5% intervention objective cannot be directly demonstrated using the current dataset.

---

## 🎓 Connection to My DATA 495 Capstone

### Bridging the Gap: Understanding Telehealth No-Shows Through Data Science

The lessons learned from this project informed the design of my subsequent DATA 495 Capstone.

In the Capstone, I intentionally generated a separate synthetic dataset containing approximately **1,500 appointments**, **23 variables**, and an approximately **30% no-show baseline**.

This provided a more suitable foundation for investigating attendance risk factors and developing predictive models.

The Capstone included:

- Synthetic data generation using Python, Faker, NumPy, and pandas.
- Data cleaning, validation, and exploratory analysis.
- Logistic Regression and XGBoost classification models.
- Model evaluation using accuracy, precision, recall, F1-score, and ROC-AUC.
- Model explainability using SHAP and LIME.
- Investigation of potential targeted outreach and intervention recommendations.

The Capstone developed predictive models and intervention recommendations; implementation and measurement of intervention-driven reductions were identified as future work.

Together, these projects demonstrate the progression of my analytical approach:

**Initial research design → Data validation → Methodological reflection → Refined research design → Applied predictive modeling**

---

## 🧩 Project Update — October 2025

> **Project Note:** This update followed a brief project pause due to my relocation from Georgia, USA, to Germany. Work resumed with renewed focus on advancing data quality, analysis, and modeling.

### 🧠 Tasks Completed

- Conducted comprehensive **Exploratory Data Analysis (EDA)** on the cleaned dataset.
- Examined key variables such as **payer type**, **visit type**, **referral source**, and **appointment status**.
- Explored **message intent** and **patient message content** using frequency plots and word clouds.
- Visualized **no-show distribution trends** across patient demographics and visit characteristics.
- Created **timeline charts** to examine appointment scheduling and attendance patterns.
- Identified early signals associated with no-show likelihood, including message length and payer categories.

### 📊 Output

- Added notebook: [Exploratory Data Analysis](mat_project_eda_repo.ipynb)
- Generated visual outputs for feature exploration and trend summaries.
- Identified candidate variables for subsequent predictive modeling.

### 🔧 Data Adjustment Phase — Completed November 2026

The originally planned data adjustment phase was completed in November 2026.

Experimental resampling reproduced the intended 20% no-show distribution but introduced duplicate observations without generating new independent appointments.

The original cleaned dataset was retained for subsequent modeling.

See the November 2026 update above for the complete findings and methodological decision.

---

## 🧼 Project Update — July 2025: Data Cleaning

### 🔧 Tasks Completed

- Standardized column names to lowercase and `snake_case`.
- Handled missing values:
  - Categorical fields (`patient_message`, `message_intent`, `stress_level`) were filled with `"None"`.
  - Numeric field `baby_age_months` was filled with `0` for unborn babies.
- Verified Boolean columns were correctly represented as `True` or `False`.
- Removed exact duplicate rows.
- Filtered invalid values, including negative baby ages.
- Engineered `message_length` to capture word count from patient messages, excluding placeholder values.
- Saved the cleaned dataset for downstream analysis.

### 📈 Output

- Cleaned dataset: **10,150 rows × 19 columns**
- Generated: `maternal_telehealth_data_clean.csv`
- Prepared data for exploratory analysis and predictive modeling.

---

## ⚙️ Project Update — July 2025: Synthetic Data Generation

- Generated synthetic maternal telehealth appointment records.
- Added simulated patient messages associated with appointment outcomes.
- Created approximately 500 message records to represent patient engagement.
- Combined structured appointment data with simulated communication features.
- Saved the generated dataset as `maternal_telehealth_full_dataset.csv`.

This phase established the initial synthetic dataset used for subsequent cleaning and exploratory analysis.

---

## 📂 Project Notebooks

The notebooks document the project in the order of development.

| Phase | Notebook | Status |
|---|---|---|
| 1. Data Simulation | [Data Simulation](mat_telehealth_data_repo.ipynb) | Completed |
| 2. Data Cleaning | [Data Cleaning & Preparation](cleaning_data_mat_project_repo.ipynb) | Completed |
| 3. Exploratory Analysis | [Exploratory Data Analysis](mat_project_eda_repo.ipynb) | Completed |
| 4. Research Design Evaluation | [Data Adjustment & Research Design Evaluation](maternal_telehealth_data_adjustment.ipynb) | Completed |
| 5. Predictive Modeling | Modeling notebook | In Progress |

---

## 🔍 Project Scope

This project explores maternal telehealth appointment no-shows using synthetic healthcare data, exploratory analysis, and predictive machine learning.

The current focus is on understanding potential predictors of missed appointments rather than demonstrating intervention effectiveness.

### Completed Components

- Synthetic appointment data generation
- Simulated patient message generation
- Data cleaning and feature preparation
- Exploratory Data Analysis
- Experimental resampling and data integrity validation
- Research design evaluation and methodological reflection

### Planned Components

- Classification modeling using Logistic Regression and Random Forest, with alternatives evaluated as appropriate
- NLP preprocessing and patient-message feature engineering
- Evaluation using confusion matrices, precision, recall, F1-score, and precision-recall AUC
- Feature importance and model explainability
- Investigation of message length, stress-related language, and sentiment signals
- Visualization of predicted no-show risk
- Robustness and fairness assessments, subject to data suitability
- Optional interactive dashboard using Streamlit

---

## 📦 Planned Deliverables

- Synthetic structured appointment and message datasets
- Reproducible Jupyter notebooks
- Data validation and exploratory visualizations
- Predictive classification models and evaluation results
- Model interpretation and feature analysis
- Final project documentation
- Optional Streamlit dashboard or application

---

## ⚠️ Limitations

- All patient and appointment records are synthetic.
- The original no-show rate is approximately 3.19%, substantially below the originally intended 20% baseline.
- The experimental resampled dataset contains repeated observations and is not treated as an independent population.
- Patterns in synthetic data may reflect assumptions embedded during generation.
- Predictive associations do not establish causal intervention effects.
- Model performance on synthetic data does not establish effectiveness in real healthcare settings.
- Potential target leakage and class imbalance require careful evaluation during modeling.

---

## 🚫 Out of Scope

- Processing real patient records or protected health information
- Integration with live healthcare scheduling systems
- Production-grade clinical deployment
- Claims of clinically validated intervention effectiveness

---

## 💗 Project Reflection

This project represents an important stage in my development as a data scientist.

My initial research design did not align with the outcome distribution of the synthetic dataset I generated. Rather than discard the work or manipulate the data to match my original assumptions, I investigated the discrepancy, validated the results, and documented a defensible methodological decision.

The experience reinforced the importance of questioning assumptions, maintaining data integrity, and allowing analytical findings to guide the direction of a project.

These lessons subsequently informed my DATA 495 Capstone and continue to shape my approach to data science and machine learning.
