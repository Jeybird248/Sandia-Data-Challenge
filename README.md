# Experiment Attempts and Results

This repository documents various attempts to predict Spanish bilingualism from brainwave data using machine learning models. A detailed description of the final results and methodology is visualized in the PDF slides stored in the `images` folder.

## Overview of Attempts

### 1. **Data Preprocessing**
- **StandardScaler**: Standardized features by removing the mean and scaling to unit variance.
- **SMOTE (Synthetic Minority Oversampling Technique)**: Addressed class imbalance by generating synthetic samples for the minority class.

### 2. **Feature Selection**
- **PCA (Principal Component Analysis)**: Reduced dimensionality while retaining the most important information.
- **Recursive Feature Elimination (RFE)**: Iteratively removed less important features to enhance model performance.

![Exploratory Data Analysis Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-3.pdf)

### 3. **Exploratory Data Analysis**
#### **Time Chunks**: 
- Divided brainwave data into pre-stimulus and event-related potential (ERP) components to analyze changes over time.
- Focused on minimum and maximum responses in specific time chunks.

![Time Chunks Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-4.pdf)

#### **Prime & Target Words**:
- Evaluated brain responses to translations and unrelated primes to identify distinctions in bilingual understanding.

![Prime & Target Words Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-5.pdf)

### 4. **Model Testing**
#### **Random Forest**:
- Provided a simple, interpretable baseline but lacked nuanced temporal and spatial data handling.
#### **1D Convolutional Neural Network (CNN)**:
- Handled temporal and spatial data effectively but suffered from lower recall and F1 scores.
#### **XGBoost**:
- **Final Model**: Chosen for its ability to capture nonlinear patterns and robustness to incomplete data.
- **Performance Metrics**:
  - **Accuracy**: 80.24%
  - **Precision (Spanish Speaking)**: 0.78
  - **Recall (Spanish Speaking)**: 0.84
  - **F1-Score (Spanish Speaking)**: 0.81

![Model Testing Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-6.pdf)

### 5. **Hyperparameter Tuning**
- Used **Randomized Search CV** for:
  - `colsample_bytree`, `learning_rate`, `max_depth`, `min_child_weight`, `n_estimators`, `reg_alpha`, `reg_lambda`, `subsample`.

![Hyperparameter Tuning Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-7.pdf)

### 6. **Top Feature Insights**
- Example: Key ERP components like `n400_P4_max`, `n170_P4_min`, and `p600_P4_max` contributed heavily to predictions.

![Feature Importance Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-8.pdf)

---

## PDF Slides
The full set of slides detailing the experiment can be found in the `images` folder:
- `Sandia Data Challenge - Team 4-<page_number>.pdf`

## How to Run the Notebook
1. Clone the repository.
2. Install dependencies listed in `requirements.txt`.
3. Run the notebook step by step to replicate the experiments.
4. Refer to the slide images in the `images` folder for detailed insights into the results and methodology.

---
