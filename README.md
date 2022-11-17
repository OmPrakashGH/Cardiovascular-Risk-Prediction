# Cardiovascular Risk Prediction
<img src="https://images.ctfassets.net/eexbcii1ci83/3AGUUtHuXuzHKu1O5PFKhh/b76f6b4e18105209f858886462de28f0/Cardiovascular_disease_3.png" width="800" height="400"/>

## Introduction

* Coronary heart disease(CHD) is a narrowing or blockage of coronary arteries usually caused by the buildup of fatty material called plaque. Coronary heart disease is also called coronary artery disease, ischemic heart disease and heart disease.

* In some cases, when plaque breaks, a blood clot may block the supply to your heart muscle. This causes a heart attack.

* The damage may be caused by various factors including smoking, high blood pressure, high cholesterol, diabetes or insulin resistance, not being active (sedentary      lifestyle) etc.

## Project Objectives

* The main goal is to predict whether the patient has a 10-year risk of future coronary heart disease (CHD).
* To highlight the main variables/factors influencing 10-year risk of future coronary heart disease (CHD).
* To compare the various classification models and find out the best model for the above task.

## Dataset Information

We are given with a dataset from an ongoing cardiovascular study on residence of the town of Framingham, Massachusetts. The dataset consists of patient’s information which includes over 3000 records and 15 attributes. Each attribute is a potential risk factor and there demographic, behavioral and medical risk factors.

### Demographic:

* Sex: male or female("M" or "F")
* Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous) Behavioral
* is_smoking: whether or not the patient is a current smoker ("YES" or "NO")
* Cigs Per Day: the number of cigarettes that the person smoked on average in one day.(can be considered continuous as one can have any number of cigarettes, even half a cigarette.) Medical( history)
* BP Meds: whether or not the patient was on blood pressure medication (Nominal)
* Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)
* Prevalent Hyp: whether or not the patient was hypertensive (Nominal)
* Diabetes: whether or not the patient had diabetes (Nominal) Medical(current)
* Tot Chol: total cholesterol level (Continuous)
* Sys BP: systolic blood pressure (Continuous)
* Dia BP: diastolic blood pressure (Continuous)
* BMI: Body Mass Index (Continuous)
* Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in fact discrete, yet are considered continuous because of large number of possible values.)
* Glucose: glucose level (Continuous)

### Predict variable (desired target)

* 10-year risk of coronary heart disease CHD(binary: “1”, means “Yes”, “0” means “No”) -DV

## Feature engineering

* We have created one new feature ‘BP’ by combining ‘sysBP’ and ‘diaBP’ features.
* We have applied label encoding for ‘sex’ and ‘is_smoking’ features as it comprises of only two distinct labels.
* We have used KNN imputer with n_neighbour = 1 to impute null values.
* We have dropped some features like id, education as it don’t impact the dependent variable.
* We have applied log transformation on all the continuous variable as distribution of these variables were right skewed.

## Selection of evaluation matrix

* The dataset is imbalanced with 85% of negative class. So ‘Accuracy’ will not be a good matrix to evaluate our model.
* As this is a health care domain project, falsely classified as negative should be our focus. So basically we need to reduce the false negative predictions.
* To summarize, recall and AUC ROC score will be our go to matrix for this project.

## Conclusion

* Age and cigsPerDay are the two most important features given by most of the models.
* Logistic regression, random forest and support vector machine models are giving a good overall balanced result.
* Models like decision tree and logistic regression(by changing threshold) are giving very good recall score but they are certainly increasing the false positive predictions.
