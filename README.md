![Feature Selection Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-1-1.jpg)

# Experiment Attempts and Results

This repository documents efforts to predict Spanish bilingualism using brainwave data collected from EEG measurements. The project combines exploratory data analysis, feature engineering, and machine learning to develop a predictive model. 

## Project Background
This dataset consists of event-related potentials (ERPs) extracted from EEG recordings of 40 participants during a language processing study. Participants were exposed to carefully constructed word pair stimuli across four languages: English, Spanish, French, and German. The study aimed to elicit distinct ERP patterns, such as the N400, which are linked to semantic processing, to assess language proficiency.

Key objectives:
- **Primary Goal**: Predict Spanish bilingualism using ERP features.
- **Bonus Objectives**: Extend predictions to German or French bilingualism or bilingualism in general.
- **Model Trust**: Emphasize explainability, performance evaluation, and feature relevance.

## Overview of Attempts

### 1. **Data Preprocessing**
- **StandardScaler**: Standardized features to have a mean of zero and unit variance, essential for models sensitive to feature scaling.
- **SMOTE**: Addressed class imbalance by oversampling the minority class (Spanish bilinguals) with synthetic examples.

![Data Preprocessing Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-3-1.jpg)

### 2. **Feature Selection**
- **PCA (Principal Component Analysis)**: Reduced high-dimensional EEG data to principal components while preserving the variance.
- **Recursive Feature Elimination (RFE)**: Iteratively removed irrelevant features to optimize model performance.

![Feature Selection Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-4-1.jpg)

### 3. **Exploratory Data Analysis**
#### **Time Chunks**:
- Segmented ERPs into pre-stimulus and ERP component time windows (e.g., N400, P200).
- Analyzed the minimum and maximum amplitudes to capture meaningful variations in brainwave responses.

![Time Chunks Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-5-1.jpg)

#### **Prime & Target Words**:
- Focused on the relationships between primes and targets (e.g., translations, repetitions, unrelated).
- Expected significant ERP differences in bilingual participants for semantically related pairs.

![Prime & Target Words Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-6-1.jpg)

### 4. **Model Testing**
#### Models Explored:
- **Random Forest**: Provided an interpretable baseline but lacked the ability to fully utilize temporal and spatial data.
- **1D Convolutional Neural Network (CNN)**: Better at capturing temporal and spatial features but had lower recall and F1 scores for bilingual predictions.
- **XGBoost**: Chosen for its ability to handle nonlinear patterns effectively and its robustness to incomplete data.

**Final Model Performance**:
- **Accuracy**: 80.24%
- **Precision (Spanish Speaking)**: 0.78
- **Recall (Spanish Speaking)**: 0.84
- **F1-Score (Spanish Speaking)**: 0.81

![Model Testing Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-7-1.jpg)

### 5. **Hyperparameter Tuning**
- Used **Randomized Search CV** to optimize hyperparameters such as:
  - `colsample_bytree`, `learning_rate`, `max_depth`, `min_child_weight`, `n_estimators`, `reg_alpha`, `reg_lambda`, and `subsample`.

![Hyperparameter Tuning Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-8-1.jpg)

### 6. **Top Feature Insights**
- Key features included specific ERP components such as:
  - `n400_P4_max`
  - `p600_P4_min`
  - `n170_Fz_max`
- These features were highly correlated with bilingualism predictions, showcasing their importance in semantic and syntactic processing.

![Feature Importance Slide](images/Sandia%20Data%20Challenge%20-%20Team%204-9-1.jpg)

---

## Conclusion
This project demonstrated the potential of EEG data in predicting language proficiency, particularly Spanish bilingualism. By leveraging ERP components and advanced machine learning techniques, we developed a model with high predictive accuracy and interpretability.
