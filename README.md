**Bias Audit and Mitigation in Income Prediction Model**

This project aims to detect and mitigate bias in a machine learning model that predicts whether an individual's income exceeds $50K. The UCI Adult dataset is used for this purpose, focusing on gender (sex) as the protected attribute.

**Table of Contents**

    Project Overview
    Dataset
    Fairness Metrics
    Bias Mitigation Strategies
    Setup and Installation
    Usage
    Results
    Visualizations
    
**Project Overview**

The core objective is to:
  Build a baseline logistic regression model for income prediction.
  Evaluate the baseline model for gender-based bias using key fairness metrics.
  Implement and evaluate two bias mitigation techniques: Reweighing (pre-processing) and Threshold Adjustment (post-processing).
  Visualize the income distribution, feature correlations, and fairness metrics across different models.

**Dataset**

The UCI Adult dataset is used, which contains various demographic and socio-economic features. The target variable is income (binary: <=50K or >50K), and the protected attribute is sex.

**Fairness Metrics**

The following fairness metrics are calculated to assess bias:
    Accuracy: Overall prediction accuracy of the model.
    Statistical Parity Difference: Measures the difference in the positive prediction rate between the unprivileged group (female) and the     privileged group (male). A value close to 0 indicates fairness.
    Disparate Impact: The ratio of the positive prediction rate for the unprivileged group to that of the privileged group. A value close      to 1 (typically between 0.8 and 1.25) indicates fairness.
    Equal Opportunity Difference: Measures the difference in True Positive Rates (TPR) between the unprivileged group and the privileged       group. A value close to 0 indicates fairness.
    
**Bias Mitigation Strategies**

Two mitigation techniques are applied:
  Reweighing: A pre-processing technique that assigns different weights to training samples to balance the representation of different       groups and outcomes.
  Threshold Adjustment: A post-processing technique that adjusts the classification threshold for different groups to achieve better         fairness metrics while maintaining reasonable accuracy.
  
**Setup and Installation**
To run this code, you need Python and the following libraries:
    pandas
    numpy
    scikit-learn
    matplotlib
    seaborn
    
You can install them using pip:
pip install pandas numpy scikit-learn matplotlib seaborn

Ensure you have the adult.csv dataset in the same directory as your Python script.

**Usage**
Save the provided Python code as a .py file (e.g., bias_audit.py).
Place the adult.csv dataset in the same directory.
Run the script from your terminal:
python bias_audit.py

The script will print the fairness metrics for the baseline model, after reweighing, and after threshold adjustment. It will also display three plots: Income Distribution by Gender, Feature Correlation Matrix, and Fairness Metrics Comparison Across Models.

**Results**

The script will output the fairness metrics for each stage:
**Baseline Fairness Metrics:**

🔍 Baseline Fairness Metrics:
{'accuracy': 0.8267232367232367, 'statistical_parity': -0.1983058863644047, 'disparate_impact': 0.5646199622975518, 'equal_opportunity': -0.2319692484793961}

**After Reweighing:**

🛠️ After Reweighing:
{'accuracy': 0.8266014466014466, 'statistical_parity': -0.05389657731238699, 'disparate_impact': 0.840742512689626, 'equal_opportunity': -0.0664654881765038}

**After Threshold Adjustment:**

🎯 After Threshold Adjustment:
{'accuracy': 0.8030999030999031, 'statistical_parity': 0.003923315801740636, 'disparate_impact': 1.009951631586526, 'equal_opportunity': -0.005086054898145293}

**Visualizations**

The script generates three plots:
  Income Distribution by Gender: Shows the count of individuals in different income categories, separated by gender. This helps visualize    the initial imbalance.
  Feature Correlation Matrix: A heatmap showing the correlation coefficients between all numerical features in the dataset. This helps       identify relationships and potential sources of bias.
  Fairness Metrics Comparison Across Models: A bar chart comparing the accuracy, statistical parity, disparate impact, and equal             opportunity metrics for the baseline, reweighted, and threshold-adjusted models. This provides a clear visual of the impact of             mitigation strategies.
  python bias_audit.py
🔎 #project-overview - Google Search
 
 
