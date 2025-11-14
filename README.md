# 🤖 Student Mark Predictor — Machine Learning Regression Model  
### End-to-End ML Pipeline • Python Package • Flask API • Model Deployment



## 📌 Overview

The **Student Mark Predictor** is a fully engineered **end-to-end machine learning system** built to predict a student’s **Math score** using demographic, socioeconomic, and academic variables.

This project includes:

- Modular ML codebase (`src/`)  
- Data ingestion, transformation, and model training pipeline  
- Automated evaluation  
- Flask API endpoint (`application.py`)  
- Model/transformer artifact storage  
- Production-style packaging (`setup.py`)  
- Research notebooks for EDA & Modeling  
- Deploy-ready structure 
- CI/CD pipelines for deployment on AZURE
- Deploy-ready structure with AWS CodePipeline 



## 🎯 Problem Statement

Using the dataset from Kaggle, predict a student’s **math score** based on:

- gender  
- race/ethnicity  
- parental level of education  
- lunch  
- test preparation course  
- reading score  
- writing score  

This ML model helps schools:  
- Identify students needing support  
- Build insight-driven interventions  
- Analyze performance drivers  

---

## 📂 Dataset Source

- **Dataset:** Students Performance in Exams  
- **Source:** https://www.kaggle.com/datasets/spscientist/students-performance-in-exams  
- **Rows:** 1000  
- **Columns:** 8  

---

## 🧱 System Architecture

The project follows a **production-grade ML structure**, broken into separate stages:

### 🔹 1. Data Ingestion
- Loads raw CSV from `notebook/data/`  
- Creates feature + target columns  
- Saves processed dataset to `artifacts/`

### 🔹 2. Data Transformation  
- Encoding categorical variables  
- Handling missing values  
- Feature scaling  
- Train-test split  
- Saves:
  - Preprocessor object  
  - Transformed arrays  

### 🔹 3. Model Training  
Models evaluated:

- Linear Regression  
- Lasso / Ridge  
- Random Forest  
- CatBoost  
- XGBoost  
- Gradient Boosting  
- Decision Tree  

The best-performing model is saved as:

- artifacts/model.pkl


### 🔹 4. Prediction Pipeline  
Given new student data, the pipeline:

Load preprocessor → transform input → load model → predict math score

This feeds into the Flask API.

---

## 🚀 Deployment & API

### Run the Flask app:

```bash
python application.py
```

### API Endpoint 

### POST:
```bash
/predictdata
```

### Payload:

```json
{
  "gender": "female",
  "race_ethnicity": "group B",
  "parental_level_of_education": "bachelor's degree",
  "lunch": "standard",
  "test_preparation_course": "none",
  "reading_score": 90,
  "writing_score": 88
}
```


### Response:
``` json
{
  "math_score_prediction": 84.7
}

```

## 🧪 Evaluation Summary

The ML notebook performs:

- Regression evaluation

- RMSE / MAE / R² metrics

- Feature importance exploration

- Cross-model comparison

(best model depends on each model's results)

## 📁 Project Structure
```
mlproject-main/
│── app.py                # Flask API for predictions
│── src/                  # End-to-end ML pipeline modules
│── artifacts/            # Model + preprocessor
│── notebook/
│     ├── 1_EDA_STUDENT_PERFORMANCE.ipynb
│     ├── 2_MODEL_TRAINING.ipynb
│     └── data/
│── templates/            # HTML UI (optional)
│── requirements.txt
│── setup.py              # Packaging
│── README.md

```

## 🧰 Tech Stack

- Python

- Pandas / NumPy

- Scikit-learn

- CatBoost

- XGBoost

- Flask

- Matplotlib / Seaborn

- MLflow-ready architecture

- Pip-installable package structure
- Github Actions for Continuous Integration/Continuous Delivery (CI/CD) on AZURE.


Happy Coding!!!