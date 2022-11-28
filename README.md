# Credit_Risk_Analysis

An analysis using Machine Learning algorithms to identify credit card risk.

Overview
The purpose of this analysis is to work with Machine Learning statistical algorithms to make predictions based on data patterns. 

To complete this analysis, I used different Machine Learning techniques to evaluate the data with unbalanced classes.  The algorithms used include RandomOverSampler, SMOTE, ClusterCentroids, SMOTEENN, BalancedRandomForestClassifier, and EasyEnsembleClassifier.

Results

The original dataset contained loan applications in Q1 of 2019. The "loan status" was used to determine whether the application was considered "low" or "high" risk. Applications that had "current" as the "loan status" were classified as "low risk" and the remaining as "high risk". 

![data count](https://user-images.githubusercontent.com/108476566/204305069-c18aec77-3476-486f-8e90-e40041218107.png)


Using the 75/25% method to split the data for training vs. testing, 51,612 "low risk" and 95 "high risk" applications were categorized into the training set.

![Training Data](https://user-images.githubusercontent.com/108476566/204307022-0c34901d-e235-4ffb-be6a-cee18aea8a72.png)

Deliverable 1: Use Resampling Models to Predict Credit Risk
Oversampling
RandomOverSampler Model randomly selects from the minority class and adds it to the training set until both classifications are equal. The results classified 51,352 records each as High Risk and Low Risk.

![Oversample count](https://user-images.githubusercontent.com/108476566/204307636-ec39f634-7cab-4ff8-a8b6-8e7a96da6c3e.png)

Balanced accuracy score: 65%.

![balanced accuracy score](https://user-images.githubusercontent.com/108476566/204317225-6f7e6182-243a-410d-8010-81a6399a3047.png)


"Low Risk" had a precision rate of 100% and recall at 68%.

![predicted low risk](https://user-images.githubusercontent.com/108476566/204317952-03a7644a-3268-45c3-afc6-638e36db7896.png)


Undersampling
ClusterCentroids Model, an algorithm that identifies clusters of the majority class to generate synthetic data points that are representative of the clusters. The model classified 260 records each as High Risk and Low Risk.

![Cluster](https://user-images.githubusercontent.com/108476566/204319799-5e56a2e6-9de8-46c8-944a-51d1e638b875.png)


Balanced accuracy score was lower than the oversampling models at 54.5%.
underacc

The "High Risk" precision rate again was only at 1% with the recall at 59% giving this model an F1 score of 1%.
"Low Risk" had a precision rate of 99% and with a lower recall at 44% compared to the oversampling models.

![highrisklowrisk](https://user-images.githubusercontent.com/108476566/204320745-0f4dfb59-fad7-4b0d-9f4a-a7ef81202fdc.png)


Deliverable 2: Use the SMOTEENN algorithm to Predict Credit Risk
Combination Sampling
SMOTEENN (Synthetic Minority Oversampling Technique + Edited NearestNeighbors) Model combines aspects of both oversampling and undersampling. The model classified 68,460 records as High Risk and 62,011 as Low Risk.

SMOTEENNcount

The balanced accuracy score improved to 64.5% when using a combined sampling model.
SMOTEENNacc

The "High Risk" precision rate did not improve was only 1%, however the recall increased to 72% giving this model an F1 score of 2%.
"Low Risk" still showed a precision rate of 100% with the recall at 57%.
SMOTEENNcm

SMOTEENNclass

Deliverable 3: Use Ensemble Classifiers to Predict Credit Risk
Compare two new Machine Learning models that reduce bias to predict credit risk. The models classified 51,366 as High Risk and 246 as Low Risk.

Balancedcount

BalancedRandomForestClassifier Model, two trees of the same size and equal size to the minority class are constructed to represent one for the majority class and one for the minority class.

The balanced accuracy score increased to 78.9% for this model.
balanceacc

The "High Risk precision rate increased to 3% with the recall at 70% giving this model an F1 score of 6%.
"Low Risk" still had a precision rate of 100% with the recall at 87%.
The top feature by importance was "total_rec_prncp" at 7.9% of the total.
balancecm

balanceclass

balancefeature

EasyEnsembleClassifier Model, a set of classifiers where individual decisions are combined to classify new examples.

The balanced accuracy score increased to 93.2% with this model.
easyeacc

The "High Risk precision rate increased to 9% with the recall at 92% giving this model an F1 score of 16%.
"Low Risk" still had a precision rate of 100% with the recall now at 94%.
easycm

easyclass

Summary
In reviewing all six models, the EasyEnsembleClassifer model yielded the best results with an accuracy rate of 93.2% and a 9% precision rate when predicting "High Risk candidates. The sensitivity rate (aka recall) was also the highest at 92% compared to the other models. The result for predicting "Low Risk" was also the highest with the sensitivity rate at 94% and an F1 score of 97%. Therefore, if a model needed to be recommended to perform this type of analysis, then this one would be the clear choice.

Ranking of models in descending order based on "High Risk" results:

EasyEnsembleClassifer: 93.2% accuracy, 9% precision, 92% recall, and 16% F1 Score
BalancedRandomForestClassifer: 78.9% accuracy, 3% precision, 70% recall and 6% F1 Score
SMOTE: 65.2% accuracy, 1% precision, 61% recall and 2% F1 Score
SMOTEENN: 64.5% accuracy, 1% precision, 72% recall and 2% F1 Score
RandomOverSampler: 64.0% accuracy, 1% precision, 66% recall and 2% F1 Score
ClusterCentroids: 54.5% accuracy, 1% precision, 69% recall and 1% F1 Score
A side note that should be considered is that original dataset had 99% of the applications classified as "Low Risk" with only 1% of the data classified in the "High Risk" category. This may skew the results greatly as there is a risk that the Machine Learning algorithms are creating clusters drawing from too small of a dataset of actual "High Risk" applications. This margin of risk might not be something that banks would be comfortable accepting.
