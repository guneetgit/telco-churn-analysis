# telco-churn-analysis
# Customer Churn Analysis + Prediction

## Problem Statement
A telecom company is losing customers. The goal is to identify 
which customers are likely to churn and understand why, so the 
retention team can intervene before it's too late.

## Dataset
- Source: IBM Telco Customer Churn (Kaggle)
- 7,043 customers, 21 features
- Class imbalance: 73% retained, 27% churned

## Tools Used
- Python (pandas, matplotlib, seaborn, scikit-learn)
- SQL (SQLite via Python)
- Google Colab

## Key Findings
1. Month-to-month contract: 42.71%, One year contract: 11.27%, Two year contract: 2.83%
2. Churned customers had significantly higher average monthly charges, suggesting pricing dissatisfaction is a key churn driver.
3. Churned customers were heavily concentrated in the first 20 months, suggesting the early relationship is the highest-risk period for customer loss.

## Model Performance
| Metric | Base Model | Balanced Model |
|--------|-----------|----------------|
| Accuracy | 79% | 73% |
| Recall (Churners) | 52% | 79% |
| ROC-AUC | 0.83 | 0.83 |

## Key Takeaway
Accuracy alone is misleading on imbalanced datasets. 
Using class_weight='balanced' improved recall on churners 
from 52% to 79%, at the cost of slightly lower precision — 
a worthwhile tradeoff given the higher cost of missing a churner.

## Limitations + Next Steps
- Address class imbalance with SMOTE
- Try Random Forest or XGBoost for better recall
- Build an interactive dashboard with Streamlit
