# Customer Churn – Tree-Based Model Suite
## Objective
•	Compare the predictive performance of: Decision Tree, Random Forest, and Gradient Boosted Trees
•	Evaluate whether LightGBM can replace traditional sklearn implementations by: Eliminating manual missing-value imputation, Eliminating manual categorical encoding, Maintaining or improving predictive performance, and Improving model explainability and governance.

## Dataset Overview
•	Retail banking customer churn dataset: Approximately 5,120 training, 2,462 testing, and 2,418 validation records
•	28 predictor variables covering: Customer demographics, Banking relationships, Investment portfolio, Wealth indicators, and Customer behaviour
•	Target variable is nearly balanced (~50% churn). AUROC is therefore used as the primary evaluation metric.

## Missing Data Challenge
•	27 out of 28 variables contain missing values.
•	Average missingness is approximately 8% per feature.
•	Traditional sklearn models require: Mean/mode imputation and manual categorical encoding.
•	LightGBM avoids these steps by:nLearning optimal routing for missing values, and handling categorical variables natively.

## Key Findings
### 1. LightGBM is a Better Engineering Choice
•	Matches or slightly exceeds sklearn performance.
•	Removes arbitrary preprocessing decisions.
•	Simplifies implementation.
•	Produces more transparent model structures for governance.
### 2. Expected Model Ranking Holds
•	Performance followed the expected complexity hierarchy: Gradient Boosting > Random Forest > Decision Tree
•	Each additional ensemble technique provided modest performance improvements, although none produced a substantial gain.
### 3. Native Missing Value Handling is Valuable
•	Instead of replacing missing values with averages, LightGBM learns the best routing path for missing observations during tree construction.
•	Benefits include: Reduced preprocessing, Better auditability, More defensible model behaviour, and Consistent handling across all models.

## Recommendations
•	Adopting LightGBM as the standard implementation for tree-based churn models.
•	Prioritising feature engineering and additional data collection over further hyperparameter tuning.
•	Using TreeSHAP with LightGBM for enhanced explainability in production environments.
