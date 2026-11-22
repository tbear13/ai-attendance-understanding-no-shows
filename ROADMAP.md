
# AI for Attendance: Project Roadmap

**Project:** Understanding No-Shows in Maternal Virtual Visits  
**Project Type:** Data Science & Machine Learning Portfolio  
**Status:** In Progress — Predictive Modeling Next  
**Last Updated:** November 2026  
**Focus Areas:** Synthetic Healthcare Data, EDA, NLP, Predictive Modeling, Model Interpretability

---

## 🎯 Project Objective

### Original Research Vision

The original objective was to investigate whether predictive analytics and targeted interventions could reduce maternal telehealth appointment no-show rates from approximately **20% to 3–5%**.

However, the original synthetic dataset already exhibited a **3.19% no-show rate** before any interventions were introduced.

Following a data adjustment investigation, I elected to preserve the original dataset rather than artificially alter appointment outcomes to match the initial research design.

### Revised Objective

The project now focuses on:

- Identifying patterns associated with missed maternal telehealth appointments.
- Developing predictive models for no-show risk.
- Investigating whether structured appointment data and simulated patient messages contain useful predictive signals.
- Evaluating model performance in the presence of class imbalance.
- Exploring interpretable, potentially actionable findings that could inform future intervention research.

**This project will investigate no-show risk prediction, not claim an intervention-driven reduction from 20% to 3–5%.**

---

## 📍 Current Project Progress

| Phase | Focus | Status |
|---|---|---|
| 1 | Planning & Setup | ✅ Completed |
| 2 | Synthetic Data Generation & Cleaning | ✅ Completed |
| 3 | Exploratory Data Analysis | ✅ Completed |
| 4 | Data Adjustment & Research Design Evaluation | ✅ Completed |
| 5 | Predictive Modeling & Evaluation | 🔜 Next |
| 6 | NLP Signal Integration | ⏳ Planned |
| 7 | Reporting & Visualization | ⏳ Planned |
| 8 | Final Documentation & Portfolio Polish | ⏳ Planned |
| 9 | Robustness & Defense | ⏳ Optional |

The original seven-phase roadmap has been expanded to document the completed EDA and research-design evaluation stages separately.

---

## ✅ Phase 1: Planning & Setup
**Original Timeline:** Weeks 1–3  
**Status:** Completed

### Tasks
- [x] Finalize project topic: maternal telehealth no-shows.
- [x] Define the initial research objective.
- [x] Include structured and unstructured patient information.
- [x] Plan NLP analysis of simulated patient messages.
- [x] Define appointment and patient characteristics.
- [x] Define simulated message intent and stress-related fields.
- [x] Set up the GitHub repository and Python notebook environment.

### Deliverables
- Project repository
- Initial research objectives
- Development roadmap

---

## ✅ Phase 2: Synthetic Data Generation & Cleaning
**Original Timeline:** Weeks 4–7  
**Status:** Completed

### Tasks
- [x] Generate synthetic appointment and patient records.
- [x] Use Faker to simulate patient communication.
- [x] Combine structured appointment information with message data.
- [x] Standardize column names and data types.
- [x] Address missing and invalid values.
- [x] Remove exact duplicate observations.
- [x] Engineer the `message_length` feature.
- [x] Export the cleaned dataset.

### Deliverables
- `maternal_telehealth_full_dataset.csv`
- `maternal_telehealth_data_clean.csv`
- Data generation notebook
- Data cleaning notebook

### Validated Dataset
- **10,150 observations**
- **19 columns**
- **324 no-show appointments**
- **3.19% no-show rate**
- **0 exact duplicate records**

### Future Preparation
- [ ] Evaluate additional NLP preprocessing, including tokenization, stopword removal, and lemmatization, during the NLP phase.

---

## ✅ Phase 3: Exploratory Data Analysis
**Status:** Completed — October 2025

### Tasks
- [x] Analyze appointment outcome distributions.
- [x] Explore payer types, referral sources, and visit characteristics.
- [x] Examine simulated patient message content and intent.
- [x] Create frequency plots and word clouds.
- [x] Explore no-show patterns across patient and appointment features.
- [x] Generate scheduling and attendance visualizations.
- [x] Identify potential predictors for subsequent modeling.

### Deliverable
- `mat_project_eda_repo.ipynb`

### Key Finding
The synthetic dataset exhibited a substantially lower no-show rate than originally intended.

This finding prompted a separate research-design investigation before proceeding to predictive modeling.

---

## ✅ Phase 4: Data Adjustment & Research Design Evaluation
**Status:** Completed — November 2026

### Purpose

Investigate the mismatch between the original research objective and the actual synthetic appointment distribution.

The original research design assumed approximately 20% no-shows, but the dataset contained only 3.19%.

### Tasks
- [x] Validate the original appointment distribution.
- [x] Confirm the original dataset contained no exact duplicate records.
- [x] Define an experimental 20% no-show baseline.
- [x] Calculate target sample sizes.
- [x] Apply experimental upsampling and downsampling.
- [x] Verify the adjusted outcome distribution.
- [x] Compare duplicate records and unique patient identifiers.
- [x] Evaluate the methodological limitations of resampling.
- [x] Document the final decision to retain the original dataset.

### Experimental Results

| Metric | Original | Resampled |
|---|---:|---:|
| Total observations | 10,150 | 10,149 |
| Unique observations | 10,150 | 7,653 |
| Duplicate observations | 0 | 2,496 |
| No-show rate | 3.19% | ~20% |

### Methodological Decision

**Retain the original cleaned dataset without changing patient records or appointment outcomes.**

Although resampling reproduced the desired numerical distribution, it did not create a new independent population with a higher no-show baseline.

The resampled dataset will remain an experimental result rather than the primary dataset for predictive modeling.

### Deliverable
- `maternal_telehealth_data_adjustment.ipynb`

### Key Lesson
A successful numerical adjustment does not necessarily resolve a mismatch between the dataset and the research question.

---

## 🔜 Phase 5: Predictive Modeling & Evaluation
**Status:** Next Phase

### Objective

Investigate whether the original synthetic dataset can support meaningful predictions of maternal telehealth appointment no-shows.

### Planned Tasks
- [ ] Review the dataset for potential target leakage.
- [ ] Define the prediction target and prediction time.
- [ ] Determine how cancelled and unresolved scheduled appointments will be handled.
- [ ] Select appropriate predictive features.
- [ ] Create independent training and testing datasets.
- [ ] Establish a baseline classifier.
- [ ] Train and evaluate Logistic Regression.
- [ ] Evaluate Random Forest or other suitable models.
- [ ] Investigate class weighting and training-only resampling.
- [ ] Compare models using minority-class performance metrics.
- [ ] Review feature importance and model interpretability.

### Planned Evaluation Metrics
- Precision
- Recall
- F1-score
- Precision-recall AUC
- Confusion matrix
- ROC-AUC where appropriate

### Planned Visualizations
- Confusion matrix
- Precision-recall curve
- ROC curve
- Feature importance chart
- Model comparison plots

### Deliverable
- `maternal_telehealth_modeling.ipynb`

---

## ⏳ Phase 6: NLP Signal Integration
**Original Timeline:** Weeks 13–16  
**Status:** Planned

### Objective

Evaluate whether simulated patient messages contribute additional predictive information beyond structured appointment features.

### Planned Tasks
- [ ] Inspect message availability and missingness.
- [ ] Preprocess message text.
- [ ] Evaluate tokenization, stopwords, and lemmatization.
- [ ] Explore keywords associated with stress or appointment barriers.
- [ ] Analyze message length and intent.
- [ ] Evaluate sentiment-related features.
- [ ] Compare structured-only and combined-feature models.
- [ ] Assess whether NLP features improve minority-class prediction.

### Planned Visualizations
- Keyword frequency charts
- Message length by appointment outcome
- Sentiment distributions
- Model comparison plots
- SHAP or LIME explanations where appropriate

---

## ⏳ Phase 7: Reporting & Visualization
**Original Timeline:** Weeks 17–19  
**Status:** Planned

### Planned Tasks
- [ ] Summarize no-show risk patterns.
- [ ] Create model performance visualizations.
- [ ] Explore appointment characteristics associated with predicted risk.
- [ ] Evaluate the feasibility of an interactive dashboard.
- [ ] Create a visual summary of research findings.

### Potential Dashboard Components
- Appointment outcome distribution
- Predicted no-show risk
- Payer and referral-source comparisons
- Model performance metrics
- Individual prediction explanations

### Optional Tools
- Streamlit
- Looker Studio
- Matplotlib
- Seaborn

---

## ⏳ Phase 8: Final Documentation & Portfolio Polish
**Original Timeline:** Weeks 20–24  
**Status:** Planned

### Planned Tasks
- [ ] Review and clean notebook code.
- [ ] Confirm notebook execution from beginning to end.
- [ ] Validate file paths and reproducibility.
- [ ] Document package dependencies.
- [ ] Update README and roadmap.
- [ ] Organize datasets, notebooks, and visual outputs.
- [ ] Prepare a final project summary.
- [ ] Document limitations and future research opportunities.
- [ ] Add selected screenshots and visual examples.

### Deliverables
- Final GitHub repository
- Reproducible notebooks
- Model evaluation summary
- Project reflection and limitations

---

## 🛡️ Phase 9: Robustness & Defense
**Original Timeline:** Weeks 25–27  
**Status:** Optional — Subject to Model Suitability

### Objective

Investigate model sensitivity to perturbations and evaluate potential defensive techniques.

### Potential Tasks
- [ ] Establish a reproducible baseline for robustness testing.
- [ ] Review compatibility with the Adversarial Robustness Toolbox (ART).
- [ ] Evaluate suitable adversarial methods for tabular classification.
- [ ] Investigate text-based perturbations for NLP features.
- [ ] Measure changes in model performance.
- [ ] Explore preprocessing or retraining defenses.
- [ ] Document limitations of adversarial testing on synthetic data.

### Potential Tools
- ART
- SHAP
- LIME
- Text perturbation libraries

The selection of adversarial techniques will depend on model architecture, feature types, and library compatibility.

---

## 🎁 Optional Extensions

- Streamlit prediction demonstration
- Interactive synthetic appointment scenarios
- Multi-model performance comparison
- Synthetic patient personas
- Structured-only versus NLP-enhanced modeling
- Expanded model explainability
- Fairness analysis where appropriate
- Intervention simulation as a separate future research exercise

---

## 🗺️ Project Visuals

### Completed
- [x] Appointment outcome distributions
- [x] Exploratory feature visualizations
- [x] Simulated message word clouds
- [x] Experimental resampling distribution
- [x] Data integrity validation table

### Planned
- [ ] Project workflow diagram
- [ ] Model comparison charts
- [ ] Confusion matrices
- [ ] Precision-recall curves
- [ ] SHAP/LIME explanations
- [ ] Structured versus NLP-enhanced comparison
- [ ] Optional dashboard screenshots

---

## 🎓 Connection to DATA 495 Capstone

The methodological lessons from this project informed my subsequent Capstone, *Bridging the Gap: Understanding Telehealth No-Shows Through Data Science*.

In the Capstone, I intentionally generated a separate synthetic dataset with an approximately 30% no-show baseline and developed predictive models using Logistic Regression and XGBoost.

The Capstone also incorporated model explainability and recommendations for potential targeted interventions.

This project and the Capstone represent different stages of my analytical development:

1. **AI for Attendance:** Initial exploration, data validation, methodological investigation, and revised predictive modeling.
2. **DATA 495 Capstone:** Refined synthetic research design, applied predictive modeling, and intervention recommendations.

The Capstone did not establish a measured intervention-driven reduction in real-world no-show rates.

---

## 📌 Project Summary

This portfolio project demonstrates the development of a synthetic maternal telehealth attendance dataset and an evolving analytical workflow.

Completed work includes data simulation, cleaning, exploratory analysis, and a documented research-design investigation.

The next phase will focus on predictive modeling using the original cleaned dataset, with attention to class imbalance, target leakage, model evaluation, and interpretability.

The project emphasizes reproducibility, transparent methodology, and critical evaluation of research assumptions.

---

## 🧠 Keywords

`#Telehealth` `#MaternalHealth` `#DataScience` `#SyntheticData` `#Python` `#EDA` `#MachineLearning` `#NLP` `#ClassImbalance` `#ModelEvaluation` `#SHAP` `#LIME`
