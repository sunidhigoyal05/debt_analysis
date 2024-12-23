# debt_analysis

**Classifying Banking Crises**

**Project Overview**

This project focuses on classifying banking crises using a binary classification approach. The dataset spans 70 countries from 1980 to 2014, and the goal is to predict the occurrence of a banking crisis. Due to the high cost of false negatives in this scenario, the F1 score and ROC curve were selected as primary evaluation metrics over accuracy.

**Rationale Behind the Chosen Model**

**Problem Nature**

The task was a binary classification problem with a temporal component. The rationale behind using binary classifiers was straightforward given the nature of the problem: predicting whether a banking crisis occurs (Yes/No).

**Evaluation Metrics**

F1 Score: Prioritized for balancing precision and recall, especially in imbalanced data scenarios.

ROC Curve: Used to assess the trade-off between sensitivity (True Positive Rate) and specificity (False Positive Rate).

The metrics were chosen because the cost of a false negative (failing to identify an impending financial crisis) is significant and can lead to complacency in crisis prevention measures, potentially resulting in severe economic consequences.

**Dataset and Challenges**

**Key Features**

Country Coverage: 70 countries.

Time Period: 1980 to 2014.

Observations

No High Correlation Between Numerical Features: Verified using a heatmap.

Missing Labels: The dataset lacks labels for the years 2015 and 2016 and excludes labels for some countries, such as Ireland.

Approaches to Missing Labels

Dropping Unlabeled Countries: Ensures model accuracy by avoiding synthetic labels.

Semi-Supervised Learning: Label propagation was considered but dismissed due to the risk of generating biased and misleading results.

**Final Choice**

Approach 1 (dropping unlabeled countries) was selected to maintain the integrity and reliability of the results.

**Data Preprocessing**

**Missing Value Treatment**

Challenges: Context-specific missing values influenced by complex variables.

Technique Used: KNN Imputation was applied for better estimation while avoiding traditional mean imputation or outright removal, which could introduce biases or inaccuracies.

**Addressing Label Imbalance**

Resampling: The dataset was upsampled to create a balanced label distribution.

**Feature Engineering**

Data Merging: A code variable was created to facilitate proper data merging.

Skewed Variables: Log transformations were applied to right-skewed numerical variables.

Standardization: Numerical variables were standardized, addressing outliers in the process.

Categorical Features: Dummy variables were created for income strata and regional attributes to capture geographical and economic diversity.

**Time Series Split**

A time series split was employed to train and evaluate the model, ensuring temporal diversity in the training and testing sets.

**Model Development**

**Models Considered**

Five binary classification models were developed and evaluated. The performance metrics included:

****F1 Score****

Accuracy (used sparingly due to its limitations in this context)

ROC Curve

**Insights**

The models were designed to balance sensitivity and specificity, with priority given to minimizing false negatives to preemptively address potential financial crises.

**Potential Improvements**

Given more time and resources, the following could be explored:

Bayesian Regression Models: To better capture yearly variations in the data.

Expanded Dataset: Increasing country and time coverage to enhance model generalizability.

Subject Matter Expertise: Leveraging domain experts to refine model features and interpretations.

**Key Takeaways**

Data limitations and missing labels constrained the scope but informed strategic decisions.

F1 score and ROC curve were critical metrics for this problem, given the high cost of false negatives.

Preprocessing techniques like KNN imputation, log transformation, and standardization played pivotal roles in preparing the dataset for modeling.

Dropping unlabeled countries was chosen over semi-supervised learning to maintain result integrity.

**Conclusion**

This project demonstrates a structured approach to binary classification in the financial domain, emphasizing the importance of thoughtful metric selection and robust data preprocessing. Despite limitations, the model provides actionable insights into predicting banking crises and highlights avenues for future exploration.

