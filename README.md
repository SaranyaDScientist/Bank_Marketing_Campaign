
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

#### Data Visualization (Univariate Analysis) - 
From the Univariate analysis, we can understand the central tendency and spread of numerical variables and the proportion of the various levels of categorical variables. Here, numerical variables are analysed through  **Distribution plots** and categorical variables are analysed through **Count plots**.

#### Outliers -
Outliers are data points that are far from other data points. In other words, they are unusual values in a dataset. In this case, there are unusual values but are not treating them as outliers as those are the cases that are more likely to subscribe a term deposit.

#### Data Visualization (Bivariate Analysis) - 
From the Bivariate analysis, we can Understand the relationship between 2 variables. Here, the relationship between the dependent variable is analysed with each independent variable using the **Count plot of the crosstabs**

#### Data Visualization (Multivariate Analysis) - 
From the **pairplot**, the impact of various X variables on Y variable are visualized, thereby giving clues for feature selection.


**Pairplot -**
![Pairplot](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_pairplot.png)

A heatmap is a data visualization technique that shows magnitude of a phenomenon as color in two dimensions. And using **heatmap**, the correlation between the variables are known. From that, we can also find out the highly correlated features.

**Heatmap -**
![Heatmap](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BMC_corr.png)

# Modelling:

#### Logistic Regression -
Logistic regression is a statistical method for analysing a dataset in which there are one or more independent variables that determine an outcome. The outcome is measured with a dichotomous variable (in which there are only two possible outcomes). It is used to predict a binary outcome (1 / 0, Yes / No, True / False) given a set of independent variables.

**Training Accuracy: 0.90**

**Testing Accuracy: 0.86**

#### Decision Tree -
Linear regression and logistic regression models fail in situations where the relationship between features and outcome is nonlinear or where features interact with each other. Time to shine for the decision tree! Tree based models split the data multiple times according to certain cut-off values in the features. Through splitting, different subsets of the dataset are created, with each instance belonging to one subset. The final subsets are called terminal or leaf nodes and the intermediate subsets are called internal nodes or split nodes. To predict the outcome in each leaf node, the average outcome of the training data in this node is used. Trees can be used for classification and regression. There are various algorithms that can grow a tree. They differ in the possible structure of the tree (e.g. number of splits per node), the criteria how to find the splits, when to stop splitting and how to estimate the simple models within the leaf nodes. The classification and regression trees (CART) algorithm is probably the most popular algorithm for tree induction. We will focus on CART, but the interpretation is similar for most other tree types.

**Gini -**

**Training Accuracy: 0.81**

**Testing Accuracy: 0.77**

**Entropy -**

**Training Accuracy: 1.0**

**Testing Accuracy: 0.87**

Decision Tree - Entropy is an overfitting model as the training accuracy is 100% but the model fails to perform well in testing. Lets try pruning the decision tree which avoids overfitting. Pruning is a technique in machine learning and search algorithms that reduces the size of decision trees by removing sections of the tree that provide little power to classify instances. Pruning reduces the complexity of the final classifier, and hence improves predictive accuracy by the reduction of over fitting.

**Entropy (Pruned) -**

**Training Accuracy: 0.85**

**Testing Accuracy: 0.86**

![Decision Tree](https://github.com/SaranyaDScientist/Data_Science_Projects/blob/master/BankMarketingDT.png)

