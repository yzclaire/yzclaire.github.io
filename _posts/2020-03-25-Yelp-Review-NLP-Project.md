---
title: "How to Use SHAP to Explains Machine Learning Models"
categories:
  - Blog
tags:
  - SHAP
  - Model Explanability
  - Machine Learning
---

# [How_SHAP_Explains_ML_Model](https://yzclaire.github.io/How_SHAP_Explains_ML_Model_Housing_GradientBoosting/)

This notebook intends to provide an overview of SHAP, a framework to improve model explainability, by focusing on the following four topics:

- What SHAP is?
- How SHAP works?
- What SHAP can do?
- How to use SHAP?

Read this project [here](https://yzclaire.github.io/How_SHAP_Explains_ML_Model_Housing_GradientBoosting/)

### What SHAP is?
Many frameworks have been proposed to help with improving the explainability and transparence of machine learning models. SHAP (SHapley Additive exPlanations) is one of the most popular frameworks that aims at providing explainability of machine learning algorithms.  SHAP takes a game-theory-inspired approach to explain the prediction of a machine learning model. The SHAP framework is now available in the open-source python library, SHAP, for everyone wants to understand how their models make prediction (“uncovering the blackbox”). 

### How SHAP works?
SHAP explains the output of a machine learning model by using Shapley values, a method from cooperative game theory. Shapley values is a solution to fairly distributing payoff to participating players based on the contributions by each player as they work in cooperation with each other to obtain the grand payoff.

The main idea behind SHAP framework is to explain Machine Learning models by measuring how much each feature contributes to the model prediction using Shapley values. The SHAP framework considers making a prediction for an instance in the dataset as a game, the gain (can be positive of negative) from playing the game is the difference between the actual prediction on this particular instance and the average prediction for all instances (base value). SHAP treats each feature value of the instance as a "player", who works with each other feature value to receive the gain (= the difference between predicted value and the base value). As different player (feature value) contributes to the game differently, Shapley values is the average marginal contribution by each player (feature value) across all possible coalitions. In short, Shapley values is calculated at instance level, and with the current set of feature values for a given instance, the marginal contribution of a feature value to the difference between the actual prediction on this particular instance and the base value is the estimated Shapley value for that feature value.

For detailed explanation of how SHAP values are calculated:
https://vknight.org/Year_3_game_theory_course/Content/Chapter_16_Cooperative_games/
https://christophm.github.io/interpretable-ml-book/shapley.html#general-idea

   
### What SHAP can do?
SHAP explains the output of machine learning models of all kinds.

•	Computes SHAP Values for model features at instance level
•	Computes SHAP Interaction Values including the interaction terms of features (only support SHAP TreeExplainer for now)
•	Visualize feature importance through plotting SHAP values:
    o	shap.summary_plot
    o	shap.dependence_plot
    o	shap.force_plot
    o	shap.decision_plot
    o	shap.waterfall_plot
    o	shap.image_plot

Note:
The Shap values computed by SHAP library is in the same unit of the model output, which means it varies by model. It could be “raw”, “probability”, “log-odds” or etc. You have the option to specify it when initiating a SHAP Explainer by setting parameter model_output.

### How to use SHAP?
1.	Initialize a SHAP Explainer that is compatible with the model to be explained
2.	Use the SHAP Explainer to compute Shap values for a set of X matrix (the explaining set)
3.	Create SHAP plots with SHAP values computed, the explaining set, and/or explainer.expcected_values


### Example SHAP Plots
To create example SHAP plots, I am using the [California Housing Prices](https://www.kaggle.com/camnugent/california-housing-prices) dataset from Kaggle and built a binary classification model(GradientBoostingClassifier from scikit-learn). The original target variable median_house_price (continuous) is converted to a categorical variable price_high_low (label 0 or 1), indicating the median_house_price is above 50 percentile or below 50 percentiles. The model is trained to classifier whether a house is at the higher price range or lower price range.

[Click Here for the Notebook of this Project](https://yzclaire.github.io/How_SHAP_Explains_ML_Model_Housing_GradientBoosting/)


### SHAP library
https://github.com/slundberg/shap
