# 🕵️‍♂️ Credit Card Fraud: Forensic Audit & Risk Architecture
"The ₹43M False Positive: Why 97.8% Recall is a Financial Failure."

## 📌 Project Overview
This project moves beyond standard machine learning classification to perform a Financial Risk Audit. Using a dataset of 284,807 transactions, I developed a model to identify fraud while calculating the Real-World Operational Damage caused by False Positives (blocking innocent customers).

## The "Forensic" Problem
Standard models optimize for Recall (catching all fraud). However, in banking, every "False Alarm" carries a cost (Customer Insult, Support Calls, Churn). This project calculates the Cost-Benefit Ratio (CBR) to determine if a model is a business asset or a financial liability.

## 📊 Forensic Audit Results
### 1. Statistical vs. Operational Reality
   
| **Metric** | **All Features (Baseline)** | **Top 6 Features (Optimized)** |
| :--- | :---: | :---: |
| **SVM Recall** | 97.8% | 97.8% |
| **SVM ROC-AUC** | 0.986 | 0.937 |
| **Thieves Caught (TP)** | 133 | 133 |
| **Innocents Blocked (FP)** | 36,368 | 36,368 |

#### Proof of Dimentionality
The Dimensionality Paradox: Reducing the model from 29 features to just the Top 6 high-impact vectors ($V_{17}, V_{14}, V_{12}, V_{10}, V_{16}, V_3$) resulted in zero loss in Recall. This proves that the "Signal" of fraud is highly concentrated. However, the identical count of Innocents Blocked (36,368) confirms that the operational noise is also embedded within these primary features, necessitating a shift toward Behavioral Feature Engineering or Threshold Optimization rather than simple feature selection.

### 2. The Financial Leak (Unscaled Audit)
   Using the original transaction amounts (unscaled), the audit revealed the "Hidden Truth":

   Money Saved (TP): ₹17,956.32

   Operational Damage (FP): ₹43,641,600.00 (Based on ₹1,200 "Insult Cost" per customer)

   CBR: 0.000411 ❌

   Verdict: This model costs the bank ₹2,430 for every ₹1 it saves.

### 3. "Big Fish" Analysis (False Negatives)
   Even with 97.8% Recall, the model missed high-value "Big Fish" transactions that significantly impact the bottom line:

    Missed Fraud #1: ₹1,096.99

    Missed Fraud #2: ₹519.90

# 🛠️ Optimization: The "Golden Threshold"
  To attempt remediation, I ran a Profitability Stress Test across 200 threshold levels.
      Optimal Threshold Found: 2.4070
      Maximum Possible Profit: ₹0.00
      Status: FINANCIAL LIABILITY
      
## Conclusion: A Linear SVM cannot solve this problem profitably. The "Straight Line" boundary is too blunt to separate fraud from legitimate high-value commerce.

# 🚀 Way Forward: Risk Engineering 2.0

I. The Kernel Trick (Non-Linearity)
    Transitioning to an RBF Kernel to allow the model to "wrap" around complex fraud clusters.

II. Behavioral Feature Engineering
  Moving from static PCA vectors to Behavioral Biometrics:

  Velocity: Transactions per minute.

  Magnitude Shift: Amount / User_Historical_Median.

  Temporal Risk: High-value transactions during "Sleep Windows" (2 AM - 5 AM).

#🧰 Tech Stack
  Language: Python

  Libraries: Pandas, NumPy, Scikit-Learn, Matplotlib

  Models: Linear SVC, Decision Tree

  Key Techniques: Cost-Sensitive Learning, Threshold Optimization, Forensic Financial Auditing





   
