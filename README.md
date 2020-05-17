
# BANK MARKETING CAMPAIGN

# Problem Statement:

There has been a revenue decline for the Portuguese bank and they would like to know what actions
to take. After investigation, we found out that the root cause is that their clients are not depositing
as frequently as before.
Knowing that term deposits allow banks to hold onto a deposit for a specific amount of time, so
banks can invest in higher gain financial products to make a profit. In addition, banks also hold better
chance to persuade term deposit clients into buying other products such as funds or insurance to
further increase their revenues.
The Portuguese bank would like to identify existing clients that have higher chance to subscribe for a
term deposit and focus marketing effort on such clients.
Find the best strategies to improve for the next marketing campaign. How can the financial institution have a greater effectiveness for future marketing campaigns? In order to answer this, we have to analyze the last marketing campaign the bank performed and identify the patterns that will help us find conclusions in order to develop future strategies.

# Data Understanding/Exploratory Data Analysis:
Once the data have been collected, we have to understand each and every variable of the data and its characteristics. This can be done by checking number and type of features, descriptive statistics and visualizations, missing values, inconsistent data records etc.

**Shape of the dataset – 45211 Rows & 17 Columns**

**Type of features – 10 Objects & 7 Integers**

**Target Variable - y (object) - [Yes,No] - Binary Classification**

**Missing Values – No missing values**

**Descriptive Statistics -**
![Descriptive Statistics](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_desc_stats.png)

### Data Visualization (Univariate Analysis) - 
From the Univariate analysis, we can understand the central tendency and spread of numerical variables and the proportion of the various levels of categorical variables. Here, numerical variables are analysed through  **Distribution plots** and categorical variables are analysed through **Count plots**.

### Outliers -
Outliers are data points that are far from other data points. In other words, they are unusual values in a dataset. In this case, there are unusual values but are not treating them as outliers as those are the cases that are more likely to subscribe a term deposit.

### Data Visualization (Bivariate Analysis) - 
From the Bivariate analysis, we can Understand the relationship between 2 variables. Here, the relationship between the dependent variable is analysed with each independent variable using the **Count plot of the crosstabs**

### Data Visualization (Multivariate Analysis) - 
From the **pairplot**, the impact of various X variables on Y variable are visualized, thereby giving clues for feature selection.


**Pairplot -**
![Pairplot](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_pairplot.png)

A heatmap is a data visualization technique that shows magnitude of a phenomenon as color in two dimensions. And using **heatmap**, the correlation between the variables are known. From that, we can also find out the highly correlated features.

**Heatmap -**
![Heatmap](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_corr.png)

# Modelling:

## Logistic Regression -
Logistic regression is a statistical method for analysing a dataset in which there are one or more independent variables that determine an outcome. The outcome is measured with a dichotomous variable (in which there are only two possible outcomes). It is used to predict a binary outcome (1 / 0, Yes / No, True / False) given a set of independent variables.

**Training Accuracy: 0.906**

**Testing Accuracy: 0.862**

## Decision Tree Classifier -
Linear regression and logistic regression models fail in situations where the relationship between features and outcome is nonlinear or where features interact with each other. Time to shine for the decision tree! Tree based models split the data multiple times according to certain cut-off values in the features. Through splitting, different subsets of the dataset are created, with each instance belonging to one subset. The final subsets are called terminal or leaf nodes and the intermediate subsets are called internal nodes or split nodes. To predict the outcome in each leaf node, the average outcome of the training data in this node is used. Trees can be used for classification and regression. There are various algorithms that can grow a tree. They differ in the possible structure of the tree (e.g. number of splits per node), the criteria how to find the splits, when to stop splitting and how to estimate the simple models within the leaf nodes. The classification and regression trees (CART) algorithm is probably the most popular algorithm for tree induction. We will focus on CART, but the interpretation is similar for most other tree types.

## Gini -

**Training Accuracy: 0.811**

**Testing Accuracy: 0.763**

## Entropy -

**Training Accuracy: 1.000**

**Testing Accuracy: 0.870**

Decision Tree - Entropy is an overfitting model as the training accuracy is 100% but the model fails to perform well in testing. Lets try pruning the decision tree which avoids overfitting. Pruning is a technique in machine learning and search algorithms that reduces the size of decision trees by removing sections of the tree that provide little power to classify instances. Pruning reduces the complexity of the final classifier, and hence improves predictive accuracy by the reduction of over fitting.

## Entropy (Pruned) -

**Training Accuracy: 0.851**

**Testing Accuracy: 0.862**

![Decision Tree](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BankMarketingDT.png)

## Random Forest Classifier -
This is a classifier that evolves from decision trees. It actually consists of many decision trees. To classify a new instance, each decision tree provides a classification for input data; random forest collects the classifications and chooses the most voted prediction as the result. The input of each tree is sampled data from the original dataset. In addition, a subset of features is randomly selected from the optional features to grow the tree at each node. Each tree is grown without pruning. Essentially, random forest enables a large number of weak or weakly-correlated classifiers to form a strong classifier.

**Training accuracy: 1.0**

**Testing accuracy: 0.899**

Random Forest Classifier is also an overfitting model.

## Gradient Boosting Classifier -
Gradient boosting classifiers are a group of machine learning algorithms that combine many weak learning models together to create a strong predictive model. Decision trees are usually used when doing gradient boosting. 

**Testing accuracy: 0.888**

**Training Accuracy: 0.929**

## CROSS VALIDATION:
Cross validation is a powerful tool that is used for estimating the predictive power of your model, and it performs better than the conventional training and test set. Using cross validation, we can create multiple training and test sets and average the scores to give us a less biased metric.

**K-Fold Cross Validation:** Cross-validation is a resampling procedure used to evaluate machine learning models on a limited data sample. The procedure has a single parameter called k that refers to the number of groups that a given data sample is to be split into. As such, the procedure is often called k-fold cross-validation. When a specific value for k is chosen, it may be used in place of k in the reference to the model, such as k=10 becoming 10-fold cross-validation. Cross-validation is primarily used in applied machine learning to estimate the skill of a machine learning model on unseen data. That is, to use a limited sample in order to estimate how the model is expected to perform in general when used to make predictions on data not used during the training of the model.

From the KFold Cross Validation, The model that has low bias error and variance error is Random Forest. Since it is an overfitting model, we can take the next model which has low variance and bias error. Gradient Boosting Classifier is the best model both in terms of accuracy and bias and variance error.

![Bias_Var_Error](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_bias_var.png)

## Model Comaparison -
Comparing the boxplots of all the models with AUC in y axis.

![Model_Comparison](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_model_comp.png)

## ROC Curves - 
A receiver operating characteristic (ROC) curve calculates the false positive rates and true positive rates across different thresholds.
The ROC curves for all the models is given below.

![ROC_curve](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_roc.png)

## Important Features from the Model -
Those variables which have positive or negative higher coeeficients are the most important features of the model. 
The important features of the model are

![Feature_importance](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_feat_imp.png)
