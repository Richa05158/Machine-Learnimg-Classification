# Machine Learning Classification Assignment

## 1. Problem Statement

The objective of this project is to develop and compare multiple machine learning classification algorithms to predict whether a customer will subscribe to a term deposit based on demographic and marketing campaign information.

The project implements five classification algorithms and evaluates their performance using Accuracy, AUC, Precision, Recall, F1 Score, and Matthews Correlation Coefficient (MCC).

## 2. Dataset Description

**Dataset:** Bank Marketing Dataset (bank-additional-full.csv)

**Source:** UCI Machine Learning Repository  
https://archive.ics.uci.edu/dataset/222/bank+marketing

The dataset contains information about bank customers and direct marketing campaigns. The target variable is `y`, which indicates whether a customer subscribed to a term deposit.

- `yes` – Customer subscribed.
- `no` – Customer did not subscribe.

The dataset contains 41,188 records before preprocessing. It includes numerical and categorical features.

The dataset was selected because it is suitable for binary classification and provides a realistic example of customer response prediction.

## 3. GitHub Repository Link

https://github.com/Richa05158/Machine-Learnimg-Classification

## 4. Data Preprocessing

The following preprocessing steps were performed:

1. Checked for missing values.
2. Identified and removed 12 duplicate records.
3. Examined categorical values, including unknown values.
4. Separated input features and target variable.
5. Applied median imputation and StandardScaler to numerical features.
6. Applied most-frequent imputation and OneHotEncoder to categorical features.
7. Split the dataset into 80% training data and 20% testing data.
8. Used stratified sampling to maintain class distribution.
9. Used random_state = 42 for reproducibility.
10. Fitted preprocessing transformations only on the training data.

After removing duplicates, the dataset contained 41,176 records.

Training samples: 32,940  
Testing samples: 8,236

## 5. Machine Learning Models and Evaluation

The following five classification algorithms were implemented:

1. Logistic Regression
2. Decision Tree Classifier
3. K-Nearest Neighbors (KNN)
4. Gaussian Naive Bayes
5. Random Forest Classifier

### Model Comparison Table

| Model | Accuracy | AUC | Precision | Recall | F1 Score | MCC |
|---|---:|---:|---:|---:|---:|---:|
| Logistic Regression | 0.9091 | 0.9390 | 0.6484 | 0.4213 | 0.5108 | 0.4762 |
| Decision Tree | 0.8890 | 0.7267 | 0.5074 | 0.5172 | 0.5123 | 0.4497 |
| KNN | 0.9014 | 0.8741 | 0.5858 | 0.4267 | 0.4938 | 0.4474 |
| Gaussian Naive Bayes | 0.8476 | 0.8405 | 0.3841 | 0.5841 | 0.4634 | 0.3903 |
| Random Forest | 0.9140 | 0.9424 | 0.6652 | 0.4774 | 0.5558 | 0.5183 |

### Model Performance Observations

**Logistic Regression**

Achieved an accuracy of 90.91% and an AUC of 0.9390. It demonstrated strong classification performance and good ability to distinguish between the two classes.

**Decision Tree**

Achieved an accuracy of 88.90%. It provided a recall of 0.5172 but had a comparatively lower AUC of 0.7267.

**K-Nearest Neighbors (KNN)**

Achieved an accuracy of 90.14%. It provided reasonable classification performance, although its F1 score was lower than Random Forest and Logistic Regression.

**Gaussian Naive Bayes**

Achieved an accuracy of 84.76%. It obtained the highest recall of 0.5841, indicating that it identified a larger proportion of actual subscribers than the other models.

**Random Forest**

Achieved the highest accuracy of 91.40%, AUC of 0.9424, Precision of 0.6652, F1 Score of 0.5558, and MCC of 0.5183. It demonstrated the strongest overall performance among the evaluated models.

### Overall Winner

**Random Forest Classifier**

Random Forest was the best-performing model overall based on its highest accuracy, AUC, precision, F1 score, and MCC.

However, Gaussian Naive Bayes achieved the highest recall, making it useful when identifying more actual subscribers is the priority.

## 6. Class Imbalance Observation

The target variable is imbalanced, with approximately 88.73% of records belonging to the `no` class and 11.27% belonging to the `yes` class.

This imbalance affects the models' ability to identify positive cases. Therefore, accuracy alone is not sufficient to evaluate performance. Additional metrics such as Precision, Recall, F1 Score, AUC, and MCC were considered.

## 7. Execution Instructions

1. Clone or download this GitHub repository.
2. Install the required Python libraries:

   `pip install -r requirements.txt`

3. Open the Jupyter Notebook located in the `model` folder.
4. Ensure the dataset is available in the notebook's expected location.
5. Execute the notebook cells sequentially to perform preprocessing, model training, and evaluation.

## 8. Repository Structure

```text
Machine-Learning-Classification/
│
├── model/
│   ├── README.md
│   └── main.ipynb
│
├── requirements.txt
├── test_data.csv
└── README.md
