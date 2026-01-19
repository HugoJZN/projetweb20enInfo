## Project Summary – Rainfall Prediction (RainTomorrow)

### Project Objective

The goal of this project is to **predict whether rainfall will occur the following day** (`RainTomorrow`) using historical meteorological data. Several **machine learning models** are evaluated, with particular emphasis on assessing the impact of **dimensionality reduction using Principal Component Analysis (PCA)** on model performance.

---

### Dataset Description

* **Dataset**: `Data_Weather.csv`
* **Size**: 145,460 observations with 22 explanatory variables
* **Target variable**: `RainTomorrow` (Yes / No)
* **Class imbalance**:

  * No: ~78%
  * Yes: ~22%

---

### Exploratory Data Analysis (EDA)

* No missing values detected after inspection
* Analysis of variable distributions and inter-feature correlations
* Clear visualization of the target class imbalance

---

### Data Preprocessing

* Removal of non-informative features (`Date`, `Location`)
* Binary encoding of the target variable (Yes = 1, No = 0)
* Split into **training and test sets (80% / 20%)** with stratification
* Construction of a preprocessing pipeline applied exclusively to the training set, including:

  * Missing value imputation
  * Outlier detection and treatment using the IQR method
  * One-hot encoding of categorical variables
  * Feature scaling of numerical variables
  * Removal of highly correlated features
  * Class rebalancing using **SMOTE**

---

### Dimensionality Reduction with PCA

* Number of features before PCA: **60**
* Retained variance: **75%**
* Number of principal components selected: **31**
* Dimensionality reduction: **–48%**

---

### Models Evaluated

1. **Logistic Regression**
2. **KNN without dimensionality reduction**
3. **KNN with PCA**

KNN hyperparameters were optimized using **GridSearchCV**.

---

### Performance Evaluation (Test Set)

**Logistic regression** achieved the best overall performance, particularly in terms of **ROC-AUC** and **F1-score**. In contrast, **KNN** proved highly sensitive to feature dimensionality, with a noticeable decline in performance after applying PCA.

---

### Model Interpretability

Analysis of the logistic regression coefficients highlights that:

* **Humidity at 3 PM (Humidity3pm)** is the most influential predictor
* Wind speed and direction also play a significant role in rainfall prediction

---

### Detailed Analyses and Visualizations

All **plots, in-depth comparisons, confusion matrices, ROC curves, cross-validation results, and complete performance metrics** for both **KNN** and **logistic regression** models are available in the full GitHub notebook.

---

### Conclusion

* **Logistic regression** provides the best trade-off between predictive performance and interpretability
* **PCA** effectively reduces dimensionality but slightly degrades KNN performance
* **SMOTE-based class rebalancing** significantly improves the detection of rainy days

**Final recommended model: Logistic Regression without PCA**
