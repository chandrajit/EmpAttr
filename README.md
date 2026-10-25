# Employee Attrition Prediction Using Machine Learning

## Overview

This repository contains the source code used for the development and evaluation of machine learning models for **employee attrition prediction**.

The study compares **Tree-Based** and **Non-Tree-Based** machine learning approaches for predicting whether an employee is likely to leave an organization. The implementation includes data preprocessing, feature selection, model development, cross-validation, performance evaluation, error analysis, and SHAP-based model interpretation.

The repository is intended to support the reproducibility and transparency of the research.

---

## Repository Contents

```text
Employee-Attrition-Prediction/
│
├── README.md
│
├── requirements.txt
│
├── notebooks/
│   ├── CM_TreeFinal_3_9_26.ipynb
│   └── CM_NonTreeFinal_3_9_26.ipynb
│
├── data/
│   └── README.md
│
└── results/
    └── README.md
```

---

## Jupyter Notebooks

### 1. Tree-Based Models

**File:** `CM_TreeFinal_3_9_26.ipynb`

This notebook contains the implementation and evaluation of the Tree-Based machine learning models used in the study.

The workflow includes:

* Data loading and preprocessing
* Feature preparation
* Model development
* Hyperparameter optimisation
* Cross-validation
* Model performance evaluation
* ROC-AUC analysis
* Error analysis
* Confusion matrix evaluation
* Feature importance analysis
* SHAP-based model interpretation

---

### 2. Non-Tree-Based Models

**File:** `CM_NonTreeFinal_3_9_26.ipynb`

This notebook contains the implementation and evaluation of the Non-Tree-Based machine learning models, including the final stacking approach used in the study.

The workflow includes:

* Data preprocessing
* Feature preparation and selection
* Development of individual machine learning models
* Hyperparameter optimisation
* Stacking classifier development
* Cross-validation
* Performance evaluation
* ROC-AUC analysis
* Error analysis
* Confusion matrix evaluation
* SHAP-based model interpretation

---

## Methodology

The general workflow followed in this study is illustrated below:

```text
Employee Data
      │
      ▼
Data Preprocessing
      │
      ▼
Feature Preparation / Selection
      │
      ├──────────────────┐
      ▼                  ▼
Tree-Based Models   Non-Tree-Based Models
      │                  │
      ▼                  ▼
Model Training and Hyperparameter Optimisation
      │                  │
      └─────────┬────────┘
                ▼
        Cross-Validation
                │
                ▼
      Performance Evaluation
                │
                ▼
       Final Model Selection
                │
                ▼
          Error Analysis
                │
                ▼
      SHAP-Based Interpretation
```

---

## Model Evaluation

The models are evaluated using standard classification performance metrics, including:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-score**
* **ROC-AUC**

Cross-validation is used to evaluate the generalisation performance and stability of the models.

---

## Error Analysis

The final models are further examined using confusion matrix-based error analysis.

The following classification outcomes are considered:

* **True Negative (TN):** Employee correctly predicted as not leaving.
* **False Positive (FP):** Employee predicted to leave but actually does not leave.
* **False Negative (FN):** Employee predicted not to leave but actually leaves.
* **True Positive (TP):** Employee correctly predicted to leave.

The total number of classification errors is calculated as:

$$
\text{Total Errors} = FP + FN
$$

The error rate is calculated as:

$$
\text{Error Rate (\%)} =
\frac{FP + FN}{\text{Total Number of Observations}}
\times 100
$$

---

## Model Interpretation

SHAP (SHapley Additive exPlanations) is used to interpret the predictions and determine the importance of individual features.

The mean absolute SHAP value for a feature is calculated as:

$$
\text{Mean SHAP}_j =
\frac{1}{N}
\sum_{i=1}^{N}
|\text{SHAP}_{ij}|
$$

where:

* \(N\) represents the number of observations.
* \(\text{SHAP}_{ij}\) represents the SHAP value of feature \(j\) for observation \(i\).

The relative importance of each feature is calculated as:

$$
\text{Relative Importance}_j(\%) =
\frac{\text{Mean Absolute SHAP}_j}
{\sum_{k=1}^{p}\text{Mean Absolute SHAP}_k}
\times 100
$$

Relative importance represents the percentage share of a feature's mean absolute SHAP value relative to the total SHAP-based importance of all features.

---

## Requirements

The analysis was implemented using Python and commonly used machine learning libraries.

The main libraries include:

* Python
* NumPy
* Pandas
* Scikit-learn
* Matplotlib
* Seaborn
* SHAP
* XGBoost
* LightGBM
* CatBoost

The exact library versions used in the analysis should be listed in the `requirements.txt` file.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/Employee-Attrition-Prediction.git
```

Navigate to the repository directory:

```bash
cd Employee-Attrition-Prediction
```

Install the required libraries:

```bash
python -m pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open and run the notebooks from the `notebooks/` directory.

---

## Reproducibility

To reproduce the analysis:

1. Install the required Python libraries.
2. Obtain the dataset from the source specified in the research paper.
3. Place the dataset in the appropriate `data/` directory.
4. Update the dataset path in the notebooks if required.
5. Run the notebooks from the beginning to the end.

Random seeds and experimental settings used in the analysis are specified within the notebooks.

---


## Citation

If you use or refer to this code, please cite the associated research paper:

> **[Authors]. [Title of the Article]. [Journal Name], [Year].**

The complete citation and DOI will be added after publication.

---

## Authors

**Chandrajit Mohan**


Additional author details will be provided according to the associated research publication.

---

## License

This repository is provided for research and academic purposes.

A suitable open-source licence, such as the MIT License, may be added to this repository.
