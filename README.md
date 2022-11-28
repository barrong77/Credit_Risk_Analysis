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

![Smoteen](https://user-images.githubusercontent.com/108476566/204321671-ed18cc6b-acb1-49c8-b972-262b4f93d560.png)


The balanced accuracy score improved to 51% when using a combined sampling model.

![calculated balance accuracy](https://user-images.githubusercontent.com/108476566/204322323-add194c9-6e9f-4535-8e2b-698cada0e388.png)


Deliverable 3: Use Ensemble Classifiers to Predict Credit Risk
Compare two new Machine Learning models that reduce bias to predict credit risk. The models classified 246 as High Risk and 51,366 as Low Risk.

![machine learning](https://user-images.githubusercontent.com/108476566/204323461-013e1674-7092-41a1-a78d-65527936d831.png)


BalancedRandomForestClassifier Model, two trees of the same size and equal size to the minority class are constructed to represent one for the majority class and one for the minority class.

The balanced accuracy score increased to 78.9% for this model.

![sklearn](https://user-images.githubusercontent.com/108476566/204324052-4dc53bfb-f1c0-4d98-8a24-b743b2cad4fd.png)


The "High Risk precision rate increased to 3% with the recall at 70% giving this model an F1 score of 6%.
"Low Risk" still had a precision rate of 100% with the recall at 87%.

![predicted high risk](https://user-images.githubusercontent.com/108476566/204324601-55bcffa6-dd69-4705-9e0b-4c92813a3ac2.png)

EasyEnsembleClassifier Model, a set of classifiers where individual decisions are combined to classify new examples.

The balanced accuracy score increased to 93.2% with this model.

![EasyEnsemble](https://user-images.githubusercontent.com/108476566/204325478-c902f743-ebf6-4f84-a232-db5955d32214.png)



Summary
In reviewing all six models, the EasyEnsembleClassifer model yielded the best results (EasyEnsembleClassifer: 93.2% accuracy, 9% precision, 92% recall, and 16% F1 Score) with an accuracy rate of 93.2% and a 9% precision rate when predicting "High Risk candidates. 
