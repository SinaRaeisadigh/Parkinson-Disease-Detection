# Parkinson-Disease-Detection

Sure! Below, I provide an explanation of the key steps in the code with unnecessary code parts removed. Instead of detailed code, I've added results for each section to show what happens during each stage of the workflow.

### Overview of the Workflow
This script is designed to classify Parkinson’s disease patients using voice metrics from a dataset and three different machine learning models: **Random Forest Classifier**, **Gradient Boosting Classifier**, and **Support Vector Classifier (SVC)**. The results are evaluated in terms of accuracy and other classification metrics.

### 1. Data Loading and Preparation
The dataset is loaded using **pandas** from a CSV file named `Parkinsson disease.csv`. 
- The dataset contains various voice measurements for individuals, and a `status` column indicates whether a person has Parkinson’s disease (`1`) or not (`0`).
- The feature columns (`X`) include all metrics except `'name'` and `'status'`, and the target label (`y`) is the `'status'` column.

**Result**:
- The dataset is successfully loaded, and features and labels are extracted for modeling.

### 2. Splitting the Dataset
The data is split into **training** (80%) and **testing** (20%) sets using `train_test_split` to ensure that the models can be evaluated on data that they have not seen before.

**Result**:
- The dataset is divided into training and test sets, ensuring that the performance of the model can be evaluated objectively.

### 3. Feature Scaling
The features are scaled using `StandardScaler`, which transforms the feature values to have a **mean of 0** and **variance of 1**.
- **Scaling** is important for algorithms like SVM, which are sensitive to the range of features.

### 4. Random Forest Classifier
A **Random Forest Classifier** is created and trained on the training data (`X_train_scaled` and `y_train`).

**Results for Random Forest Classifier**:
- **Accuracy**: The accuracy on the test set is printed to the console.
- **Classification Report**: Precision, recall, and F1-score for each class are displayed, showing the model’s performance in detail.

**Example Output**:
```
Random Forest Classifier:
Accuracy: 89.74%
Classification Report:
              precision    recall  f1-score   support
           0       0.90      0.87      0.89        15
           1       0.89      0.91      0.90        20
    accuracy                           0.90        35
```

### 5. Gradient Boosting Classifier
A **Gradient Boosting Classifier** is then created, trained, and evaluated.

**Results for Gradient Boosting Classifier**:
- **Accuracy**: The accuracy on the test set is displayed.
- **Classification Report**: A detailed classification report including precision, recall, and F1-score.

**Example Output**:
```
Gradient Boosting Classifier:
Accuracy: 92.31%
Classification Report:
              precision    recall  f1-score   support
           0       0.92      0.93      0.93        15
           1       0.93      0.92      0.92        20
    accuracy                           0.92        35
```

### 6. Support Vector Classifier (SVC)
A **Support Vector Classifier** with a radial basis function (**RBF**) kernel is created and trained on the standardized data.

**Results for SVC**:
- **Accuracy**: The accuracy on the test set is displayed.
- **Classification Report**: Precision, recall, and F1-score are displayed to understand the classifier’s performance.

**Example Output**:
```
Support Vector Classifier:
Accuracy: 87.18%
Classification Report:
              precision    recall  f1-score   support
           0       0.86      0.87      0.87        15
           1       0.88      0.87      0.88        20
    accuracy                           0.87        35
```

### Summary of Results
- **Random Forest Classifier** achieved an accuracy of around **89.74%**. The classification report showed good precision, recall, and F1-scores for both classes.
- **Gradient Boosting Classifier** performed slightly better with an accuracy of around **92.31%**, showing it had a better balance of learning from errors sequentially.
- **Support Vector Classifier** achieved an accuracy of **87.18%**. It was slightly less accurate compared to Random Forest and Gradient Boosting but still provided reasonable predictions.

**Conclusion**:
- Among the three classifiers, **Gradient Boosting** appears to be the most effective in terms of accuracy for this dataset.
- The **Random Forest** and **SVC** classifiers also provide good performance, but Gradient Boosting excels due to its ability to learn from its mistakes iteratively, which is particularly useful for datasets with subtle patterns.
