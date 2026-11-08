# 🌦️ Australian Weather Prediction using Machine Learning

A supervised machine learning project that classifies whether it will rain in the Melbourne region of Australia using historical weather observations.

This project explores an end-to-end machine learning workflow, covering data preprocessing, exploratory data analysis, feature engineering, model development, hyperparameter tuning and performance evaluation.

**Course:** IBM Machine Learning with Python — Final Project

---

## 📌 Project Overview

The objective of this project is to develop machine learning classification models that predict rainfall using historical weather data.

The dataset contains weather observations from multiple locations across Australia. For this project, the analysis focuses on three nearby locations:

- Melbourne
- Melbourne Airport
- Watsonia

To avoid target leakage, the prediction target is reframed: the model predicts rainfall for a given day using available weather observations from the previous day.

## 📊 Dataset

- **Dataset:** Australian Weather Dataset
- **Source:** Australian Government Bureau of Meteorology
- **Data access:** IBM Skills Network course-hosted CSV
- **Selected locations:** Melbourne, Melbourne Airport and Watsonia
- **Target variable:** `RainToday` (Yes/No)

The dataset is loaded directly from the IBM Skills Network resource within the notebook.

## ⚙️ Project Workflow

### 1. Data Loading and Exploration
- Loaded the Australian weather dataset using Pandas.
- Examined the dataset structure, feature types and missing values.
- Explored rainfall distributions and weather patterns.

### 2. Data Preprocessing
- Removed observations containing missing values.
- Addressed potential target leakage by shifting the prediction target.
- Selected observations from the three Melbourne-area locations.
- Prepared numerical and categorical features.

### 3. Feature Engineering
- Extracted seasonal information from the date column.
- Created a season-based feature for capturing weather patterns.
- Removed the original date column after feature extraction.

### 4. Exploratory Data Analysis
- Investigated the distribution of the target variable.
- Examined class imbalance between rainy and non-rainy days.
- Explored relationships between weather variables and rainfall.

### 5. Data Preparation
- Separated input features and target labels.
- Performed an 80:20 stratified train-test split.
- Applied appropriate transformations to numerical and categorical features.

### 6. Model Development
Built Scikit-learn preprocessing and classification pipelines using:

- `StandardScaler` for numerical features.
- `OneHotEncoder` for categorical features.
- `ColumnTransformer` to combine preprocessing operations.
- `Pipeline` to integrate preprocessing and model training.

### 7. Model Optimization
- Used `GridSearchCV` for hyperparameter tuning.
- Applied 5-fold cross-validation.
- Optimized the Random Forest classifier.

### 8. Model Evaluation
Evaluated model performance using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- Feature Importance

---

## 🤖 Machine Learning Models

Two classification algorithms were explored:

| Model | Test Accuracy |
|---|---:|
| Random Forest Classifier | 84% |
| Logistic Regression | 83% |

### Random Forest — Best Parameters

The optimal parameters identified through GridSearchCV were:

| Hyperparameter | Value |
|---|---:|
| Number of Estimators | 100 |
| Maximum Depth | 20 |
| Minimum Samples Split | 2 |
| Cross-validation score | 85% |

### Random Forest Classification Report

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| No Rain | 0.86 | 0.95 | 0.90 |
| Rain | 0.75 | 0.51 | 0.61 |

**Overall Test Accuracy: 84%**

### Logistic Regression Classification Report

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| No Rain | 0.86 | 0.93 | 0.89 |
| Rain | 0.68 | 0.51 | 0.58 |

**Overall Test Accuracy: 83%**

### Key Observation

Although Random Forest achieved slightly higher accuracy, both models had relatively low recall for rainy days (51%).

This highlights the importance of evaluating imbalanced classification problems using multiple metrics rather than relying solely on accuracy.

---

## 🛠️ Technologies and Libraries

- **Programming Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn
- **Development Environment:** Jupyter Notebook

## 📁 Repository Structure

```text
Australian-Weather-Prediction-ML/
│
├── README.md
├── Australian_Weather_Prediction.ipynb
├── requirements.txt
└── .gitignore
```

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/EshanG357/Australian-Weather-Prediction-ML.git
```

### 2. Navigate to the project directory

```bash
cd Australian-Weather-Prediction-ML
```

### 3. Install the dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `Australian_Weather_Prediction.ipynb` and run the cells sequentially.

**Note:** An internet connection is required to download the dataset from the IBM Skills Network resource.

---

## 📚 Learning Outcomes

Through this project, I gained practical experience in:

- Developing end-to-end supervised machine learning workflows.
- Identifying and preventing target leakage.
- Handling missing data and class imbalance.
- Performing feature engineering and data transformations.
- Building Scikit-learn pipelines using `ColumnTransformer`.
- Applying stratified sampling and cross-validation.
- Optimizing models using GridSearchCV.
- Evaluating classification models using multiple performance metrics.
- Comparing different machine learning algorithms.

## 🙏 Acknowledgements

This project was completed as the final project of the **IBM Machine Learning with Python** course.

Dataset source: [Australian Government Bureau of Meteorology](http://www.bom.gov.au/climate/dwo/)

Course materials and dataset access: [IBM Skills Network](https://skills.network/)

The project builds upon the educational workflow provided in the IBM course, with the notebook organized for portfolio presentation.

---

**Author:** [Eshan Garg](https://github.com/EshanG357)

*Exploring Machine Learning, one project at a time.* 🚀