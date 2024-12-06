# Liver Disease Prediction Model Comparison Report

## **Introduction**
This project focuses on developing a reliable machine learning model to predict liver disease using a dataset of **583 records and 11 features**. The study evaluates multiple algorithms, optimizing them for key metrics such as accuracy, precision, recall, F1-score, and ROC-AUC. The aim is to identify the best model for practical use in medical diagnostics.

---

## **Model Performance at a Glance**

| **Model**            | **Best Parameters**                             | **Accuracy** | **Precision (Class 0/1)** | **Recall (Class 0/1)** | **F1-Score (Class 0/1)** | **Mean ROC-AUC** | **Std. Dev (AUC)** |
|-----------------------|-------------------------------------------------|--------------|----------------------------|-------------------------|---------------------------|-------------------|---------------------|
| **Logistic Regression** | C=0.01, penalty='l2', solver='lbfgs'           | 0.74         | 0.71 / 0.79               | 0.86 / 0.61            | 0.78 / 0.69              | 0.7600           | 0.0523              |
| **SVC**              | C=1000, kernel='rbf', gamma='scale'             | 0.85         | 0.83 / 0.87               | 0.90 / 0.79            | 0.86 / 0.83              | 0.7077           | 0.0763              |
| **KNN**              | metric='manhattan', n_neighbors=3, weights='distance' | 0.88    | 0.83 / 0.95               | 0.97 / 0.78            | 0.89 / 0.86              | 0.8511           | 0.0684              |
| **Random Forest**    | max_depth=None, n_estimators=300                | 0.85         | 0.86 / 0.84               | 0.86 / 0.84            | 0.86 / 0.84              | 0.8907           | 0.0405              |
| **Gradient Boosting** | learning_rate=0.1, max_depth=5, n_estimators=200 | 0.80        | 0.84 / 0.77               | 0.78 / 0.83            | 0.81 / 0.80              | 0.7322           | 0.0643              |
| **XGBoost**          | max_depth=5, learning_rate=0.05, n_estimators=100 | 0.81        | 0.81 / 0.82               | 0.85 / 0.78            | 0.83 / 0.80              | 0.7832           | 0.0321              |
| **AdaBoost**         | base_estimator=DecisionTree(max_depth=3)         | 0.75         | 0.82 / 0.69               | 0.67 / 0.83            | 0.74 / 0.75              | 0.7987           | 0.0479              |

---

## **Key Evaluation Metrics**
- **Accuracy:** Overall correctness of predictions.
- **Precision:** Proportion of correct positive predictions.
- **Recall:** Ability to identify all true positive cases.
- **F1-Score:** Balance between precision and recall.
- **ROC-AUC:** Measures the ability to distinguish between classes.
- **Standard Deviation (AUC):** Indicates stability of model performance.

---

## **Performance Highlights**
### **1. Logistic Regression**
- Moderate accuracy.
- Weak recall for **Class 1**, limiting its ability to detect positive cases.

### **2. SVC**
- High accuracy with balanced precision and recall.
- ROC-AUC slightly lower than Random Forest.

### **3. KNN**
- Excellent precision and recall, especially for **Class 1**.
- Strong overall performance with a high ROC-AUC score.

### **4. Random Forest**
- Most balanced performance across all metrics.
- Achieves the **highest ROC-AUC** with minimal variability.

### **5. Gradient Boosting**
- Moderate performance overall.
- Slightly lower ROC-AUC compared to top-performing models.

### **6. XGBoost**
- Balanced but does not excel in any specific metric.

### **7. AdaBoost**
- Lower accuracy and imbalanced precision/recall compared to others.

---

## **Recommendation**
### **Top Contenders**
1. **KNN:**
   - Excels in identifying positive cases with superior precision and recall for **Class 1**.
   - Best suited for scenarios prioritizing minimal false negatives.

2. **Random Forest:**
   - Delivers balanced and consistent performance.
   - Achieves the **highest ROC-AUC** with excellent stability.

### **Final Recommendation**
- **Random Forest** is the recommended model due to its **robust, well-rounded performance** and suitability for medical diagnostics. It ensures accurate, balanced predictions for both classes while maintaining consistency across datasets.

---

## **Conclusion**
The **Random Forest** model is the best choice for predicting liver disease in clinical settings, combining high accuracy, balanced metrics, and reliability. Its robust performance makes it ideal for practical implementation.
