---
title: "Predicting the covid test result"
excerpt: "Image classification by using neural network <br/><img src='figures/app_screenshot.JPG' width='400'>"
collection: portfolio
categories: [Data Science, Project]
---


## Abstract
* The goal is to use classification models to predict when covid test results (positive/negative).
* Key questions to be answered
  1. Can we reliably predict covid test results based on the symptom?
  2. If the prediction is possible, what is the contribution/importance of each feature?
* An interactive dashboard/app was built. [click here](https://classification-app-20210513-v3.herokuapp.com/)

## Data
* Dataset from this published [article](https://www.nature.com/articles/s41746-020-00372-6) and corresponding [GitHub](https://github.com/nshomron/covidpred/tree/master/data).
* 1 target: corona_results (positive, negative, other)
* 8 features: age, sex, cough, shortness_of_breath, fever, sore_throat, Headache, contact_with_confirmed
* About 3 million rows: each row is one test (all 3 million rows are used in the data explanatory but only 10,000 rows are used for training the classification models for the sake of computation time)

## Tool/Packages used
* Data exploration: pandas, numpy, matplotlib
* Classification: scikit-learn, XGBoost
* Application: Streamlit, Heruko

## Modeling
* Different models are tested: KNN, LogisticRgression, NaiveBayes (Bernoulli), DecisionTree, RandomForest, Ensemble, and Boost are tested.
* Models are tuned by GridSearchCV.
* Class imbalance techniques (over/under sampling, class weight adjustment, and threshold tuning) are used to tune the models.
* Feature importance was examined in the LogisticRgression, Forest, and XGBoost.
* **Final model**: The simple LogisticRgression with a threshold of 0.1 generates balanced results
  * P-threshold: 0.1
  * Accuracy: 0.924
  * Precision: 0.58
  * Recall: 0.64
  * F1: 0.61
* **Modeling conclusions**
  * Predicting covid test results is possible
  * Recall is rather limited (~ 0.6), likely due to the asymptomatic cases

## App
* The model has been incorporated into an interactive app by using Streamlit and deployed on Heroku.
* [Click here to check it out](https://classification-app-20210513-v3.herokuapp.com/)

![OnlineApp](/figures/app_screenshot.JPG?raw=true)

## Acknowledgement
* I sincerely appreciate great suggestions from the instructors (Kim and Joan), TAs (Tawney and Ethan), and the group team (Matthew, Leslie, Jason)!
