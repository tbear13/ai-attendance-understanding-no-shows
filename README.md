# ai-attendance-understanding-no-shows
AI for Attendance: Understanding No-Shows in Maternal Virtual Visits

### 🧩 Project Updates (October 2025)

> *Note: This update follows a brief project pause due to my relocation from Georgia, USA to Germany. Work has since resumed with renewed focus on advancing data quality, analysis, and modeling.*

#### 🧠 Tasks Completed
- Conducted comprehensive **Exploratory Data Analysis (EDA)** on the cleaned dataset  
- Examined key variables such as **payer type**, **visit type**, **referral source**, and **appointment status**  
- Explored **message intent** and **patient message content** using frequency plots and word clouds  
- Visualized **no-show distribution trends** across patient demographics and visit characteristics  
- Created **timeline charts** to observe appointment scheduling and attendance patterns over time  
- Identified early signals linked to no-show likelihood (e.g., longer message length, specific payer categories)

#### 📊 Output
- Added notebook: [mat_project_eda_repo.ipynb](mat_project_eda_repo.ipynb)  
- Generated visual outputs for feature exploration and trend summaries  
- Findings will guide feature selection for the next modeling phase  

#### 🔧 Upcoming Update (Data Adjustment Phase)
- Implementing a dedicated data refinement process in [`maternal_telehealth_data_adjustment.ipynb`](maternal_telehealth_data_adjustment.ipynb)  
- Addressing identified discrepancies and improving consistency for modeling readiness  
- Preparing updated dataset version for integration into predictive modeling and dashboard development  

#### 🚀 Next Phase (Predictive Modeling & Visualization)
- Build and evaluate **machine learning models** for no-show prediction  
- Use **SHAP** and **LIME** to interpret feature importance  
- Create **dashboards** visualizing high-risk patterns and model results  

---

# Project Updates (July 2025)
### 🔧 Tasks Completed:
- Standardized column names to lowercase and snake_case for consistency
- Handled missing values:
   1. Categorical (patient_message, message_intent, stress_level) → filled with "None"
   2. Numeric (baby_age_months) → filled with 0 for unborn babies
- Verified Boolean columns were correctly typed as True/False
- Removed exact duplicate rows
- Filtered out invalid values, such as negative baby ages
- Engineered a new feature message_length to capture word count from patient_message (excluding placeholder values)
- Saved the cleaned dataset as maternal_telehealth_data_clean.csv for downstream use
### 📈 Output:
- Cleaned dataset shape: 10,150 rows × 19 columns
- File generated: maternal_telehealth_data_clean.csv
### 🚀 Next Phase:
- The upcoming EDA (Exploratory Data Analysis) update will include:
- Visual summaries of payer mix, visit types, referral sources
- Message content trends via word clouds
- Timeline plots of appointment scheduling and no-shows
### 📍 Stay tuned for Week 5: Visualizing Patterns in No-Show Behavior

---

## Project Updates (July 2025)

- Added synthetic patient messages tied to appointment outcomes (Show, No-Show, Cancelled)
- Merged these into the full dataset (~10,000 patients) with 500 message records to simulate real patient engagement rates
- Saved the final dataset as `maternal_telehealth_full_dataset.csv` for downstream EDA and modeling

## 📂 Notebook(s)

- [⚙️ Data Simulation Notebook](mat_telehealth_data_repo.ipynb)
- [🧼 Data Cleaning & Preparation](cleaning_data_mat_project_repo.ipynb)
- [🔍 Exploratory Data Analysis](mat_project_eda_repo.ipynb)

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
