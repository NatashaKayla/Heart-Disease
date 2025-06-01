## 🫀 Heart Disease Classification - EDA & Predictive Modeling

This project focuses on analyzing a cardiovascular dataset to explore the patterns associated with heart disease and build predictive models based on key clinical and demographic features. It covers the full cycle from exploratory data analysis to classification model training and evaluation.

---

### 🎯 Main Objectives

* Explore the distribution and correlations of heart-related medical features
* Handle missing values and detect outliers
* Visualize class distribution for heart disease presence
* Compare statistical characteristics between patients with and without heart disease
* Train and evaluate machine learning models for heart disease classification
* Identify key predictive features contributing to model decisions

---

### 🩺 Dataset Description

The dataset contains various medical and clinical attributes, including:

* **Demographic info**: Age, Sex
* **Cardiovascular measures**: Resting Blood Pressure, Cholesterol, Fasting Blood Sugar
* **Electrocardiographic data**: Resting ECG, Maximum Heart Rate Achieved, ST depression
* **Other features**: Chest Pain Type, Exercise-Induced Angina, Slope, Number of Vessels
* **Target variable**: Presence of heart disease (0 = No, 1 = Yes)

---

### 📊 Key Analysis & Visualizations

* **Correlation heatmap** to identify strong inter-feature relationships
* **Histograms and boxplots** to understand data distribution and detect outliers
* **Count plots and pie charts** for categorical feature analysis by class
* **Bar plots** comparing heart disease occurrence across age, sex, cholesterol, etc.
* **Skewness & distribution analysis** to check for normality in numeric data

---

### 🧠 Modeling Process

**Models implemented**:

* Random Forest Classifier
* XGBoost Classifier

**Evaluation metrics**:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

Initial findings:

* Class imbalance affects recall for minority classes
* Tree-based models show solid performance but benefit from tuning

---

### ⚙️ Fine-Tuning Details

Applied **GridSearchCV** to optimize XGBoost hyperparameters:

* Tuned: `learning_rate`, `max_depth`, `n_estimators`, `subsample`
* Best parameters were selected and the model was retrained
* Performance notably improved on test data, especially recall for heart disease detection

---

### 🏆 Model Comparison: XGBoost vs Random Forest

| Metric    | Random Forest                      | XGBoost                                 |
| --------- | ---------------------------------- | --------------------------------------- |
| Accuracy  | High                               | Higher (Post-Tuning)                    |
| Recall    | Good                               | Improved, especially for minority class |
| F1-Score  | Balanced                           | Better overall balance                  |
| Precision | Slightly higher for majority class | Competitive                             |

---

### 📈 Feature Importance

From the feature importance chart, it is evident that certain features play a critical role in predicting the outputs. The **most important feature** is **Alkaline Phosphatase (U/L)**, followed closely by **Hepatomegaly**, indicating their strong influence on the model’s predictions. Other **significant contributors** include **Prothrombin, Bilirubin, SGOT, Triglycerides, and, Albumin**, all of which show a notable relationship with the target variable. Features like **Copper, Age and Platelets** also have **meaningful importance**, though to a slightly lesser extent. 

In contrast, features such as **Drug, Edema_N, and Ascites** have relatively **lower importance**, while variables like **Edema_S, Gender, and Edema_Y** contribute **minimally**. These insights suggest that focusing on the most influential features can enhance the model’s efficiency, while less significant ones might be considered for exclusion to streamline the analysis.

---

### 📌 Conclusion

* XGBoost is highly effective for heart disease prediction, particularly after hyperparameter tuning
* Key features like Alkaline Phosphatase (U/L) and Hepatomegaly are strong indicators
* Tree-based models provide interpretable and accurate predictions for clinical use
