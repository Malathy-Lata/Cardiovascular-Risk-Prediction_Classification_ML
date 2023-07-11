# Cardiovascular-Risk-Prediction_Classification_ML

**1. Introduction:**

*Cardiovascular diseases (CVDs) are the primary cause of mortality worldwide. According to WHO, 19.1 million people died from CVDs in 2020.

*Though CVDs cannot be treated, predicting the risk of the disease and taking the necessary precautions and medications can help to avoid severe symptoms and, in some cases, even death.

*Since most CVDs can be prevented with behavioral changes and following certain necessary precautions, accurate prediction of the future risk of heart disease becomes crucial. This will either help prevent the disease or early detection which in turn allows better management of the disease with counseling and medical therapy.

*The dataset is from an ongoing cardiovascular study on residents of the town of Framingham, Massachusetts. This project aims to develop a classification model that can predict if a patient is at risk of coronary heart disease (CHD) over a period of 10 years, based on demographic, lifestyle, and medical history.



**2. EDA Summary:**

*The target variable 'ten_year_chd' correlated positively with factors such as age, pulse pressure, and prevalent hypertension.

*Only ~15% (around 500 patients) of the patients in the study were eventually exposed to the risk of Cardiac Heart Disease(CHD) and the rest of the patients were not exposed to CHD after the end of the 10-year study.

*Education Level 1 (1478) included most of the study participants, followed by Level 2(990), Level 3 (549), and Level 4 (373). As the education level increases, the incidence of cardiovascular diseases decreases.

*Female participants(1923) were slightly more in number than males (1467). Almost males and females have a similar risk of future incidence of CHD. Both male and female patients have a similar risk for future incidence of cardiovascular diseases according to age. Mostly both males and females falling under the category of age nearing 50 years and 60 years have a higher risk of developing future CHD.

*The dataset consisted of almost similar proportions of smokers and non-smokers. Smokers pose an almost similar risk of developing a cardiac disease as non-smokers.

*There were only 100 participants on BP medication.

*Majority of the patients, around 3500 study participants did not have a history of stroke.

*Around 1000 participants have hypertension while the rest had no history of hypertension at the time of the study. Prevalent hypertension increases the chances of developing CVDs.

*>3000 participants were non-diabetic and only a minimal number of patients (87) were diabetic.

*Individuals aged above 45 years pose a comparatively higher risk of CHD.

*The higher the systolic and diastolic BP, the higher the risk of incidence of cardiovascular diseases.

*Higher total cholesterol levels also increase the risk of cardiac disease slightly.

*The higher the pulse pressure, the larger the risk of developing cardiovascular disease.

*According to the study population, prevalent stroke and diabetes do not increase the risk of CVDs.

**3. Modeling Summary:**

**A. Logistic Regression:**

*In statistics, the (binary) logistic model is a statistical model that models the probability of one event (out of two alternatives) taking place by having the log odds (the logarithm of the odds) for the event be a linear combination of one or more independent variables.

*This can be considered as the baseline model to obtain predictions since it is easy to explain.

*Logistic Regression train recall: 0.69

*Logistic Regression test recall: 0.68

**B. K-nearest Neighbors:**

*The k-nearest neighbors algorithm, also known as KNN, is a non-parametric, supervised learning classifier, which uses proximity to make classifications or predictions about the grouping of an individual data point.

*Best hyperparameters: K = 43

*K nearest neighbors train recall: 0.83

*K nearest neighbors test recall: 0.68

**C. Naive Bayes:**

*Naive Bayes classifiers are a collection of classification algorithms based on Bayes’ Theorem. It is not a single algorithm but a family of algorithms where all of them share a common principle, i.e., every pair of features being classified is independent of each other.

*Best hyperparameters: var_smoothing= 1.0

*Naïve Bayes train recall: 0.58

*Naïve Bayes test recall: 0.54

**D. Decision Tree:**

*A Decision tree is a flowchart-like tree structure, where each internal node denotes a test on an attribute, each branch represents an outcome of the test, and each leaf node (terminal node) holds a class label.

*Best hyperparameters: max_depth: 1, min_samples_leaf: 0.1, min_samples_split: 0.1

*Decision tree train recall: 0.84

*Decision tree test recall: 0.77

**E. Support Vector Machines:**

*Support Vector Machine (SVM) is a supervised machine learning algorithm used for both classification and regression. The objective of SVM algorithm is to find a hyperplane in an N-dimensional space that distinctly classifies the data points.

*Best hyperparameters: C: 1, gamma: 0.01, kernel: 'rbf'

*SVM train recall: 0.74

*SVM test recall: 0.68

**F. XG Boost:**

*In this algorithm, decision trees are created in sequential form. Weights play an important role in XGBoost. Weights are assigned to all the independent variables which are then fed into the decision tree which predicts results. The weight of variables predicted wrong by the tree is increased and these variables are then fed to the second decision tree. These individual classifiers/predictors then ensemble to give a strong and more precise model. It can work on regression, classification, ranking, and user-defined prediction problems.

*Best hyperparameters: max_depth: 1, min_samples_leaf: 0.1, min_samples_split: 0.1, n_estimators: 500

*XG Boost train recall: 0.81

*XG Boost test recall: 0.43



**4. Results:**

![11](https://github.com/Malathy-Lata/Cardiovascular-Risk-Prediction_Classification_ML/assets/114274732/e827d814-c5d2-4f2b-a820-f8fb3fe81190)

**5. Conclusions**

*The given dataset of cardiovascular risk prediction consists of 3390 rows and 17 different columns which include behavioral, demographic, and medical (current and past) factors that might play a role in predicting future risk of cardiovascular disease.

*The missing values were either replaced with median or mode values, respectively.

*Since there are 304(more number) missing values in the glucose column, filling the null values with either mean or mode will return a biased result. Hence to avoid biased results, KNN imputation can be performed.

*Our target variable (future risk of CHD) correlates positively with age, pulse pressure, and prevalent hypertension.

*Only ~15% (around 500 patients) of the patients in the study were eventually exposed to the risk of Cardiac Heart Disease(CHD) and the rest of the patients were not exposed to CHD after the end of the 10-year study.

*Individuals aged above 45 years pose a comparatively higher risk of CHD.

*The higher the systolic and diastolic BP, the higher the risk of incidence of cardiovascular diseases.

*As the education level increases, the incidence of cardiovascular diseases decreases.

*Almost males and females have a similar risk of future incidence of CHD. Prevalent hypertension increases the chances of developing CVDs.

*The higher the pulse pressure, the larger the risk of developing cardiovascular disease.

*Predicting the risk of coronary heart disease is critical for reducing fatalities caused by this illness. We can avert deaths by taking the required medications and precautions if we can foresee the danger of this sickness ahead of time.

*The model we develop must have a high recall score. It is OK if the model incorrectly identifies a healthy patient as a high-risk patient because it will not result in death, but if a high-risk patient is incorrectly labeled as healthy, it may result in fatality. We were able to create a model with a recall of just 0.77 because of limited data available and limited computational power available. A recall score of 0.77 indicates that out of 100 individuals with the illness, our model will be able to classify only 77 as high-risk patients, while the remaining 33 will be classified incorrectly. Future developments must include a strategy to improve the model recall score such as involving more people in the study and including people with different medical histories.

*According to our analysis, the age of the person was the most important feature in determining the risk of a patient getting infected with CHD, followed by pulse pressure, prevalent hypertension, and total cholesterol. Diabetes, prevalent stroke, and BP medication were the least important features in determining the risk of CHD.

*From the analysis, it is found that the age of the person is the most important feature in predicting the future risk of developing Cardiovascular Disease, followed by pulse pressure, prevalent hypertension, and total cholesterol.
