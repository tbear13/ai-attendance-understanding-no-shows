# ai-attendance-understanding-no-shows
AI for Attendance: Understanding No-Shows in Maternal Virtual Visits

## Project Updates (July 2025)

- Added synthetic patient messages tied to appointment outcomes (Show, No-Show, Cancelled)
- Merged these into the full dataset (~10,000 patients) with 500 message records to simulate real patient engagement rates
- Saved the final dataset as `maternal_telehealth_full_dataset.csv` for downstream EDA and modeling


## 🔍 Scope

This project aims to develop a machine learning model to predict **maternal telehealth appointment no-shows** using both structured patient data and unstructured message text. The final solution will combine **synthetic healthcare data generation**, **natural language processing (NLP)** for message analysis, and **classification modeling** to identify patients at risk of missing appointments.

### ✅ The project will include:
- Simulated patient demographic and appointment data (payer type, visit history, baby age, referral source)
- Simulated message text using libraries like `Faker` to model patient communication intent and emotional tone
- Preprocessing of structured data and NLP pipeline (stopwords, lemmatization, sentiment features)
- Classification modeling using Logistic Regression and Random Forest
- Model evaluation using accuracy, recall, confusion matrix, and optional SHAP/LIME interpretability
- Integration of NLP signal features (message length, stress keywords, sentiment polarity)
- Visualization of no-show trends, feature importance, and individual prediction explanations
- Robustness testing via adversarial attacks (ART library) and defensive retraining
- GitHub repository documenting the process, visuals, and deliverables

> ⚠️ This project does **not** include real patient data or live API integration.  
> It is a simulated portfolio project meant to demonstrate machine learning and NLP modeling skills with an emphasis on healthcare applications, fairness, and robustness.

### 📦 Deliverables
- Simulated dataset (structured + messages)
- Jupyter notebooks with modeling and evaluation
- Visualizations (SHAP, confusion matrix, trend plots)
- Streamlit app or dashboard (optional)
- Final report and GitHub project structure

### 🚫 Out of Scope
- HIPAA-compliant handling of real patient data
- Integration with live scheduling systems
- Production-grade deployment
