# Australian Weather Prediction using Machine Learning

A supervised machine learning project that predicts whether it will rain today in the Melbourne region of Australia, using historical weather observations.

This project was completed as the final project in the **IBM Machine Learning with Python** course on IBM Skills Network. The notebook contains the completed course workflow and experiments.

## Project Overview

The goal is to build and evaluate classification models using weather observations from three nearby locations:

- Melbourne
- Melbourne Airport
- Watsonia

The original dataset contains Australian weather observations. For this localized experiment, the notebook filters the data to the three locations above and uses the previous day's rainfall (`RainYesterday`) and other weather measurements to predict the target (`RainToday`).

## Workflow

1. Load and inspect the Australian weather dataset.
2. Remove rows containing missing values.
3. Address target-feature leakage by reframing the prediction target:
   - `RainTomorrow` is renamed to `RainToday`.
   - `RainToday` is renamed to `RainYesterday`.
4. Restrict the analysis to Melbourne, Melbourne Airport, and Watsonia.
5. Extract a seasonal feature from the date and remove the original date column.
6. Separate features and target, then create a stratified 80:20 train-test split.
7. Build preprocessing pipelines:
   - Standard scaling for numerical features.
   - One-hot encoding for categorical features.
8. Train and tune a Random Forest classifier using GridSearchCV.
9. Evaluate the model using accuracy, a classification report, and a confusion matrix.
10. Inspect feature importances and compare the results with Logistic Regression.

## Models and Results

### Random Forest

| Metric | Result |
|---|---:|
| Best cross-validation accuracy | 0.85 |
| Test accuracy | 0.84 |
| Recall for `Yes` (rain) | 0.51 |
| Precision for `Yes` (rain) | 0.75 |
| F1-score for `Yes` (rain) | 0.61 |

Best parameters found in the notebook:

- `n_estimators`: 100
- `max_depth`: 20
- `min_samples_split`: 2

### Logistic Regression

| Metric | Result |
|---|---:|
| Test accuracy | 0.83 |
| Recall for `Yes` (rain) | 0.51 |
| Precision for `Yes` (rain) | 0.68 |
| F1-score for `Yes` (rain) | 0.58 |

**Note:** Accuracy alone does not tell the full story. The dataset is imbalanced, and the recall for rainy days is notably lower than the recall for non-rainy days. This is an important consideration when evaluating a rainfall prediction model.

These figures are the results recorded in the completed notebook. Results can vary if the notebook is rerun with different library versions or randomization settings.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Repository Structure

```text
Australian-Weather-Prediction-ML/
├── README.md
├── requirements.txt
├── .gitignore
└── notebooks/
    └── FinalProject_AUSWeather.ipynb
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/Australian-Weather-Prediction-ML.git
cd Australian-Weather-Prediction-ML
```

### 2. Install dependencies

It is recommended to use a virtual environment.

```bash
python -m venv .venv
```

Activate it:

**Windows**
```bash
.venv\Scripts\activate
```

**macOS / Linux**
```bash
source .venv/bin/activate
```

Install the packages:

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook
```

Open `notebooks/FinalProject_AUSWeather.ipynb` and run the cells from top to bottom.

The notebook downloads the dataset from the IBM Skills Network-hosted course resource, so an internet connection is required when loading the data.

## Dataset and Acknowledgements

- The notebook and learning workflow are based on the **IBM Machine Learning with Python** course on [IBM Skills Network](https://skills.network/).
- The course notebook identifies the Australian Government Bureau of Meteorology as the original source of the weather observations: [Bureau of Meteorology – Climate Data Online](http://www.bom.gov.au/climate/dwo/).
- The CSV used by the notebook is loaded from an IBM Skills Network course-hosted resource.

Please refer to the original course and dataset sources for their respective terms of use and attribution.

## Learning Outcomes

Through this project, I practiced:

- Building end-to-end supervised learning workflows.
- Identifying and addressing target leakage.
- Handling numerical and categorical data through preprocessing pipelines.
- Using stratified train-test splitting and cross-validation.
- Performing hyperparameter tuning with GridSearchCV.
- Evaluating imbalanced classification problems beyond accuracy.
- Comparing tree-based and linear classification models.

---

*This repository documents a completed educational project. It is not intended to provide operational weather forecasts.*
