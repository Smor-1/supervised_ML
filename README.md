# supervised_ML

## Overview

In this project, the problem of unbalanced classification was tackled using a dataset containing loan related parameters to predict credit card risk. There are inherently more good loans outnumbering risky loans. This causes issues for classification machine learning algorithms to train on. Therefore, six techniques to overcome imbalanced target data were evaluated and the results can be found below. 

## Results

Naive Random Oversampling had a balanced accuracy score of 0.66. See imbalanced classification report below: 

![Image](Challenge/Naive_Random_Oversampling.png)

SMOTE oversampling had a balanced accuracy score of 0.63. See imbalanced classification report below: 

![Image](Challenge/SMOTE_Oversampling.png)

Undersampling with ClusterCentroids had a balanced accuracy score of 0.51. See imbalanced classification report below: 

![Image](Challenge/ClusterCentroids.png)

SMOTEENN combination over/undersampling had a balanced accuracy score of 0.68. See imbalanced classification report below: 

![Image](Challenge/SMOTEENN.png)

The ensemble learner BalancedRandomForestClassifier had a balanced accuracy score of 0.78. See imbalanced classification report below: 

![Image](Challenge/BalancedForest.png)

The Easy Ensemble AdaBoost Classifier had a balanced accuracy score of 0.93. See imbalanced classification report below: 

![Image](Challenge/AdaBoost.png)

## Summary 

Overall, the machine learning models had mediocre balanced accuracy scores aside from the Easy Ensemble AdaBoost Classifier. However, with each of these models there is a large discordancy between the precision scores of the majority (good, low risk loans) and the minority (bad, high risk loans) classes. The precision for high risk loans is very low across all models. This means that when our models predict a high risk loan, the reliability of it actually being a high risk loan is low due to the high number of false positives reducing our positive predictive value (i.e., precision). 

Therefore, despite achieving a high balanced accuracy score (0.93) for one of our models, I would still have to consult with the client on whether sensitivity or precision is more important to them. What I mean is that if we focus our efforts on identifying all of the high risk loans without caring too much on false positives and the reliability of a positive prediction, then our models aren't terrible considering the high recall/sensitivity for both classes of loan. In closing, it is tough to recommend a model or not because it depends what is more important to the end user of the model. 