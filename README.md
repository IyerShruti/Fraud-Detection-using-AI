# 💳 AI-Powered Financial Transaction Fraud Detection & Analysis Project Overview 

This project implements an end-to-end AI-driven fraud detection system for financial transactions, combining machine learning predictions with interactive business intelligence visualizations.
The goal is to identify fraudulent transaction patterns, understand behavioral risk factors, and present explainable insights through a Power BI dashboard.

The system is designed to handle highly imbalanced data, where fraudulent transactions represent only ~0.13% of total records, making traditional accuracy-based approaches ineffective.

## 📊 Dataset Description 

The dataset consists of financial transaction records enriched with engineered behavioral features and model predictions.

#### Key Columns Used 

Amount
TransactionType
TransactionDate
TransactionFrequency
secs_since_prev
sum_amt_7d
cnt_7d
Actual
Predicted_Label
Predicted_Prob

Fraud distribution
0 (Non-Fraud): 995,800
1 (Fraud): 1,315

## 🚀 Feature Engineering

To capture realistic fraud behavior, multiple temporal and transactional features were engineered.

##### secs_since_prev: 

Time gap between consecutive transactions for the same customer, highlighting rapid transaction bursts.

##### sum_amt_7d:

Rolling 7-day transaction amount to capture abnormal spending accumulation.

##### cnt_7d:

Rolling 7-day transaction count to measure transaction intensity.

##### TransactionFrequency:

Encodes behavioral transaction patterns.

##### Predicted_Prob:

Model-generated fraud probability score used for confidence-based analysis.

## 🤖 Machine Learning Model

The final model used for fraud detection is XGBoost (Extreme Gradient Boosting).

#### Model Configuration

Binary classification with logistic objective

Evaluation metric: AUC

Class imbalance handled using scale_pos_weight

Early stopping applied to avoid overfitting

The model is optimized for fraud recall, ensuring fraudulent transactions are less likely to be missed.

## 👩🏻‍💻 Model Performance

Training and validation metrics show stable and reliable learning behavior.

Training AUC stabilized around 0.914

Validation AUC stabilized around 0.910

Minimal gap between training and validation curves

Early convergence indicates strong generalization

This confirms the model performs well despite extreme class imbalance.

## 📈 Power BI Dashboard Insights

Transaction Type vs Highest Spending

TRANSFER transactions show the highest average transaction amount, indicating higher fraud exposure. PAYMENT and CASH-based transactions occur more frequently but with lower average amounts.

### Total & Average Transaction Metrics

Total transaction amount processed exceeds 173 billion units.
Average transaction value is approximately 173K units, highlighting the financial impact of even rare fraud cases.

### Fraud Probability Distribution

Most transactions cluster around a fraud probability of 0.25–0.30, showing the model assigns moderate risk rather than extreme certainty, reflecting realistic fraud detection behavior.

### Amount vs Time Gap Relationship

High transaction amounts often occur within short time gaps, suggesting suspicious burst-style behavior commonly linked to fraud.

### Fraud Risk by Transaction Type

CASH_IN, PAYMENT, and TRANSFER transactions display elevated fraud probabilities during certain periods, indicating category-specific risk patterns.

### Transaction Trends Over Time

Transaction volumes decline over time, while fraud predictions remain consistently present, indicating persistent fraud risk.

### Fraud Probability Confidence

High fraud probability scores are rare but significant, reinforcing the importance of probability-based risk prioritization.

### Transaction Frequency Impact

Higher transaction frequency correlates with higher transaction amounts, validating behavioral risk assumptions used by the model.

## 🔎 Dashboard Visuals Included

KPI cards for total amount, average amount, and average fraud probability

Bar chart for transaction type vs spending

Scatter plot for amount vs time gap

Line chart for transaction trends over time

Heatmap for fraud risk by transaction type

Histogram for fraud probability confidence

Donut chart for amount distribution by transaction type

All visuals are built using model output data, ensuring explainability and analytical consistency.

## 💵 Business Value

This system enables

Early identification of high-risk transactions

Explainable fraud predictions using probability scores

Monitoring of high-exposure transaction categories

Seamless integration with BI tools for decision support

Even with a very low fraud rate, the financial impact remains substantial, making proactive detection critical.

## 💻 Technologies Used

Python
Pandas, NumPy
XGBoost
Power BI (Web)

## 📍 Conclusion

This project demonstrates a complete AI-powered fraud detection pipeline, from feature engineering and machine learning to explainable, business-ready visual analytics.
The approach balances predictive performance with interpretability, making it suitable for real-world financial fraud monitoring systems.
