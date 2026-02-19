# Code Review Bot

---

# Software Defect Prediction Using Machine Learning

## Overview

This project implements a machine learning-based defect prediction system using the PROMISE Software Defect Dataset. The objective is to identify defect-prone software modules using static code metrics such as size, complexity, coupling, and object-oriented design measures.

By predicting high-risk modules early, the system enables risk-based testing and helps improve software quality while reducing unnecessary testing effort.

---

## Problem Statement

Software testing resources are limited, and applying equal effort to all modules is inefficient. Certain modules are more likely to contain defects due to high complexity, size, or coupling.

This project aims to:

* Predict whether a software module is defect-prone.
* Provide a defect probability score.
* Support risk-based testing decisions.

---

## Dataset

This project uses the PROMISE Software Defect Dataset.

The dataset contains:

* Size metrics (e.g., LOC - Lines of Code)
* Complexity metrics (Cyclomatic Complexity)
* Object-Oriented metrics (CBO, RFC, WMC, DIT)
* Halstead metrics
* Binary defect label (1 = Defective, 0 = Clean)

Each row represents one software module.

Example structure:

| loc | cbo | rfc | wmc | defect |
| --- | --- | --- | --- | ------ |
| 520 | 18  | 45  | 30  | 1      |

---

## Project Workflow

```
PROMISE Dataset
        ↓
Data Cleaning & Preprocessing
        ↓
Handle Class Imbalance (SMOTE)
        ↓
Model Training (Random Forest / XGBoost)
        ↓
Model Evaluation
        ↓
Defect Risk Prediction
```

---

## Model Training

The following models are used:

* Random Forest Classifier (Primary Model)
* XGBoost (Optional Comparison)

Evaluation metrics:

* Precision
* Recall
* F1-Score
* ROC-AUC

Recall is prioritized to minimize missing defect-prone modules.

---

## Example Input

Software metrics provided to the model:

```
LOC: 540
Cyclomatic Complexity: 26
CBO: 18
RFC: 45
WMC: 32
Halstead Volume: 380
```

## Example Output

```
Defect Probability: 0.81
Prediction: DEFECT-PRONE
Risk Level: HIGH
```

---

## Applications

* Risk-Based Testing
* Test Case Prioritization
* CI/CD Pipeline Optimization
* Software Quality Monitoring
* Early Defect Detection

---

## Technologies Used

* Python
* Pandas
* Scikit-learn
* XGBoost
* Imbalanced-learn (SMOTE)
* Matplotlib / Seaborn

---

## Future Improvements

* Hybrid model combining code metrics and review comments
* Deep learning-based prediction
* Cross-project defect prediction
* Explainable AI integration
* CI/CD automation integration

---



## License

This project is for academic and research purposes.

---

If you want, I can now give you:

* A professional folder structure
* requirements.txt content
* Sample train.py file
* Deployment version using Streamlit
