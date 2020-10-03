# IBM-Data-Science-Professional-Certificate
This repository contains work done for the attainment of the IBM Data Science Professional Certificate

## Introduction
Car accidents, or in general traffic accidents are a serious problem of the modern society. The World Health Organisation estimates that very year, road accidents result in more than 1.3 million deaths, 20 to 50 million of non-fatal injuries and costs economies 3% of their anual gross domestic product through lost resources, productivity and collateral damage. It is thus important to determine the factors leading to accidents, in order to develop strategies to eliminate or mitigate them to reduce the occurences of traffic accidents.

Traffic accidents lead to a variety of consequences, ranging from altercations, minor property damages to the more severe loss of human lives. Having studied the factors causing traffic accidents, a subsequent, important step is to then determine **what affects the level of severity of accidents, and if we can effectively predict the severity of the accidents**.

## Data Source
In order to answer the question on which factors affect the severity of accidents, the data should include information/attributes on the weather conditions, location, number and types of parties involved, other event factors and preferably the labelled data attribute of accident severity.

Luckily, a convenient data source has been kindly provided by the course intstructors [here](https://www.coursera.org/learn/applied-data-science-capstone/supplement/Nh5uS/downloading-example-dataset). Metadata of the dataset can be found [here](https://s3.us.cloud-object-storage.appdomain.cloud/cf-courses-data/CognitiveClass/DP0701EN/version-2/Metadata.pdf).

## Model
The main targeted feature would be the *SEVERITYCODE*, which represents the two possible state/class of the accidents - (0) Property damage only, (1) Injury. Given that this is a binary classification problem, we will explore the use of Logistic Regression (LR) and the ensemble Random Forest Classification (RF) models. Gradient Boosting Classifiers (GBC) which were found to normally provide superior results for binary and multi-class classification tasks will be implemented.

## Conclusion
Overall, we see that GBC returns the best performance compared to LR and RF, boasting a recall of 0.70 vs 0.64 and 0.63 from LR and RF respectively. The poor Jaccard score for all models however meant that the models tend to fail in predicting a large portion of the dataset correctly.

A closer look into the classification reports above show that most model suffer from poor precision for the severe case, i.e. when *severitycode* == 1 , i.e. there is a tendency for the model to make False Positives.

To further improve prediction of the models, hyperparameter tunining of the models can be carried out. However, to further greatly improve the scores, it is highly likely that we may have to look deeper into feature or data engineering to obtain better predictive features.

|Model|Jaccard|F1-Score|Precision|Recall|
|-----|-------|--------|---------|------|
|LogisticRegression|0.372980|0.681718|0.710528|0.647226|
|RandomForestClassifier|0.343732|0.648532|0.686934|0.631443|
|GradientBoostingClassifier|0.385116|0.673655|0.719399|0.702093|
