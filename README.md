---
marp: true
---

# Software_-Promotion-Campaign Revenue Generation Analysis with Causal ML

## Overview

This analysis explores the impact of two treatments on revenue generation within our dataset: offering discounts and providing tech support. By employing causal machine learning models, specifically Linear Regression with Shrinkage (LRS) and XGBoost (XGB), we aimed to understand which factors most significantly influence revenue generation when these treatments are applied.

## Dataset Description

Dataset: https://www.kaggle.com/datasets/hwwang98/software-usage-promotion-campaign-uplift-model/data


Our dataset contains the following features, with each entry representing a customer:

- `Global Flag`: Binary indicator of whether the customer has global offices.
- `Major Flag`: Indicates if the customer is a large consumer in their industry.
- `SMC Flag`: Denotes if the customer is a Small Medium Corporation.
- `Commercial Flag`: Binary indicator of whether the customer's business is commercial (as opposed to public sector).
- `IT Spend`: The amount spent on IT-related purchases by the customer.
- `Employee Count`: The number of employees at the customer's organization.
- `PC Count`: The number of PCs used by the customer.
- `Size`: The customer's size, typically measured by their yearly total revenue.
- `Tech Support`: Binary indicator of whether the customer received tech support.
- `Discount`: Binary indicator of whether the customer was given a discount.
- `Revenue`: The revenue generated from the customer, measured in dollars based on the amount of software purchased.

## Analysis Results

### Feature Importance for Discount Treatment

#### LRS Regression
- Key influencers for generating revenue when discounts are provided include `Tech Support`, `IT Spend`, and `PC Count`.

#### XGB Regression
- `IT Spend` was found to be the most significant factor, with `Tech Support` and `PC Count` also being important.

### Feature Importance for Tech Support Treatment

#### LRS Regression
- `Discount` emerged as the most critical feature, with `PC Count` and `IT Spend` also playing significant roles.

#### XGB Regression
- `PC Count` and `Discount` were the top factors, emphasizing the importance of IT infrastructure and financial incentives.

## Conclusions and Strategic Recommendations

The analysis reveals that IT Spend and PC Count are consistently significant across both treatments, indicating the importance of targeting customers with significant IT infrastructure and investment.

### If You Can Only Do One Campaign

- **Discount Campaign**: Given its significant impact across both models, especially for customers with high IT spend, a discount campaign could be more effective for immediate revenue boosts.
- **Tech Support Campaign**: For building long-term relationships and potentially increasing future revenue through customer loyalty, offering tech support could be more beneficial.

## Technical Setup and Analysis Approach

### Dependencies and Environment Setup

The analysis is conducted in a Python environment, requiring the installation of several packages crucial for data processing, analysis, and causal inference. Key dependencies include:

- `causalml`: A Python package that provides machine learning tools to estimate causal effects.
- Standard data science libraries such as `pandas`, `numpy`, `scikit-learn`, and `xgboost`.
- Visualization libraries such as `matplotlib` and `seaborn` for insightful data visualizations.

To replicate the analysis environment, ensure to install all the required packages listed in the `requirements.txt` file, as well as the `causalml` package for advanced causal inference techniques.

### Analytical Approach

The notebook follows a structured approach to causal analysis, starting with data preprocessing, exploratory data analysis (EDA), feature engineering, and finally, causal inference modeling using both Linear Regression with Shrinkage (LRS) and XGBoost (XGB) regression models. 

Key steps in the analysis include:

1. **Data Preprocessing**: Cleaning and preparing the data for analysis, including handling missing values, encoding categorical variables, and normalizing features.
2. **Exploratory Data Analysis (EDA)**: Conducting initial analysis to understand the data's characteristics, distributions, and relationships between features.
3. **Feature Engineering**: Creating new features or modifying existing ones to improve model performance and uncover more insights into the causal relationships.
4. **Causal Inference Modeling**: Applying causal machine learning models to estimate the impact of treatments (discounts and tech support) on revenue. This includes detailed feature importance analysis to identify the most influential factors.
5. **Model Evaluation and Validation**: Assessing model performance using appropriate metrics and validation techniques to ensure reliability and accuracy of the findings.

### Code Structure

The notebook is organized into sections corresponding to each step of the analysis, with code cells meticulously commented to explain the purpose and functionality of each code snippet. This structured approach not only facilitates understanding and replication of the analysis but also ensures transparency and rigor in the causal inference process.

## Recommendations for Replication

For analysts and data scientists looking to replicate or extend this analysis, it is recommended to:

- Review the provided `requirements.txt' file and ensure all dependencies are installed.
- Familiarize yourself with the `causalml` library's documentation and features, as it plays a pivotal role in the causal inference analysis.
- Consider extending the analysis with additional causal inference models or techniques to compare results and derive more robust insights.

## Conclusion

This README.md aims to provide a comprehensive overview of the causal ML analysis conducted to understand the impact of discounts and tech support on revenue generation. By combining technical setup details, analytical approach, and strategic recommendations, this document serves as a guide for replicating the analysis and applying its findings in a business context.
