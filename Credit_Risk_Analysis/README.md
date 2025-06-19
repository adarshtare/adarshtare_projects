Credit-Risk-Analysis
Predicting the ability of a borrower to pay back the loan through traditional machine learning models and comparing them with ensemble methods and artificial neural networks (ANNs).

Overview
This project aims to build a classification model that predicts whether a borrower will default or fully repay a loan. It compares traditional ML algorithms, ensemble techniques like XGBoost, and artificial neural networks using Keras.

Data Overview
The dataset includes binary classification for loan repayment:

Encoding	Category	Count
1	Defaulted	5,634
0	Paid Back the amount in full	33,136

Sampling Strategy
The dataset is highly imbalanced. To address this, SMOTE (Synthetic Minority Over-sampling Technique) was used:

python
Copy
Edit
smote = SMOTE(ratio='minority')
features_c, target_c = smote.fit_sample(features_corr, target)
Evaluation Criteria
False Positive Rate (FPR)
FPR
=
𝐹
𝑃
𝐹
𝑃
+
𝑇
𝑁
FPR= 
FP+TN
FP
​
 

True Positive Rate (TPR)
TPR
=
𝑇
𝑃
𝑇
𝑃
+
𝐹
𝑁
TPR= 
TP+FN
TP
​
 

Data Preprocessing
Normalization
python
Copy
Edit
def normalize(subset):
    continious_columns = subset.select_dtypes(include=['float']).columns
    mm_scaler = preprocessing.MinMaxScaler()
    for col in continious_columns:
        subset[col] = mm_scaler.fit_transform(subset[[col]])
    return subset
Feature Engineering
Correlation matrix was used to study feature dependencies.

Scaling and normalization were applied before feeding the models.

Model Architectures
Logistic Regression Variants:
Vanilla

With class weight penalty

With custom penalties

With SMOTE Over Sampling

With data normalization

XGBoost (Extreme Gradient Boosting):
Used with the following configurations:

objective='binary:logistic'

subsample=0.8

colsample_bytree

max_depth

n_estimators

scale_pos_weight (for handling imbalance)

Artificial Neural Network (Keras):
Used under-sampled data to balance classes before training.

Performance Summary
Model Description	Sampling Method	AUC
Logistic Regression (Vanilla)	None	0.50
Logistic Regression (Class Weight)	class_weight='balanced'	0.59
Logistic Regression (SMOTE)	SMOTE Over Sampling	0.58
XGBoost	SMOTE Over Sampling	0.91
Max Voting (Bagging Ensemble)	SMOTE Over Sampling	0.80
ANN (Keras)	SMOTE Over Sampling	0.87

Conclusion
XGBoost performed best with an AUC of 0.91 and the fewest false negatives.

ANN (Keras) was also effective, achieving an AUC of 0.87.

Logistic regression models showed moderate performance, improving when sampling techniques were applied.

Would you like me to save this cleaned README as a new Markdown file for you to download or directly update your project?