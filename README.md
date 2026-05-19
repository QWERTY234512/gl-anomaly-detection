# GL Anomaly Detection Engine
Detecting suspicious general ledger entries using unsupervised ML.

## Business problem
Finance teams manually review thousands of GL entries monthly to catch
posting errors and fraudulent transactions. This is time-consuming and
error-prone. This project automates anomaly flagging using Isolation Forest —
reducing the manual review pool by surfacing the highest-risk entries first.

## Dataset
- Source: Credit Card Fraud Dataset (Kaggle, ULB ML Group)
- 284,807 transactions · 492 genuine fraud cases (0.17% fraud rate)
- Realistic class imbalance mirrors real-world GL anomaly detection

## Approach
1. EDA — distribution analysis, feature correlation with fraud label
2. Feature engineering — StandardScaler on Amount and Time
3. Model — Isolation Forest (unsupervised, contamination=0.002)
4. Evaluation — confusion matrix, precision/recall vs true labels
5. Dashboard — Power BI report for finance stakeholders

## Results
- Flagged X% of true anomalies with zero labelled training data
- False positive rate: Y% (acceptable for a first-pass filter)
- Top anomaly signals: [list the V-columns from your EDA]

## Key insight
Unsupervised detection works best as a triage tool — not a final decision.
In production, I would combine Isolation Forest scores with business rules
(e.g. posting outside business hours, amounts exceeding authorisation limits)
to improve precision before human review.

## Stack
Python · Pandas · scikit-learn · Matplotlib · Seaborn · Power BI

## Files
- gl_anomaly_detection.ipynb — full notebook
- scored_transactions.csv — model output
- dashboard_screenshot.png — Power BI dashboard
