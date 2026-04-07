# Loan Default Prediction using Decision Trees & Random Forest

## 1. Business Context

Peer-to-peer lending platforms like LendingClub connect borrowers with investors. 
The fundamental risk lies in identifying borrowers who are unlikely to repay loans.

This project approaches the problem from an investor’s perspective:
> How can we predict loan default risk before capital is allocated?

---

## 2. Objective

To build classification models that predict whether a borrower will **fail to fully repay a loan**, enabling better risk-informed lending decisions.

---


## 3. Dataset

- Source: Public LendingClub dataset (2007–2010)

This project uses publicly available lending data commonly used for financial risk modeling exercises.

**Note:**  
The dataset is not included in this repository due to size and distribution constraints.  
However, the structure and features used are fully described within the notebook.

### Key Features:
- Credit score (FICO)
- Interest rate
- Debt-to-income ratio (DTI)
- Credit history length
- Loan purpose (categorical)

## 4. Exploratory Insights

Several structural patterns emerge from the data:

- **FICO vs Interest Rate**  
  Higher credit scores correlate with lower interest rates → risk-based pricing behavior
<img width="598" height="289" alt="image" src="https://github.com/user-attachments/assets/86948514-9254-41cc-a475-3eb6f872fe56" />

- **Loan Purpose Distribution**  
  Debt consolidation dominates loan demand, followed by credit card usage

- **Default Behavior**  
  Default rates appear relatively consistent across loan purposes, suggesting risk is not strongly segmented by purpose alone

---

## 5. Data Preparation

- Converted categorical variable (`purpose`) using one-hot encoding
- Created feature matrix and target variable
- Split dataset into training (70%) and testing (30%)

---

## 6. Modeling Approach

### Model 1: Decision Tree
- Baseline classification model
- Captures non-linear relationships

### Model 2: Random Forest
- Ensemble method to improve generalization
- Reduced variance compared to single tree

---

## 7. Model Performance

### Decision Tree Results:
- Accuracy: 73%
- Strong performance on non-default class
- Weak recall on default class (~22%)

### Key Observation:
The model struggles to correctly identify defaulters.

This indicates:
- **Class imbalance problem**
- Model bias toward majority (non-default) class

---

## 8. Critical Insight (What Most Projects Miss)

Despite acceptable overall accuracy, the model underperforms where it matters most:

> Failing to detect high-risk borrowers undermines its real-world utility.

This highlights a common issue in financial modeling:
- Accuracy ≠ Business Value

---

## 9. Recommendations

To improve predictive performance:

- Apply class balancing techniques (SMOTE, class weights)
- Optimize hyperparameters (depth, estimators)
- Evaluate using recall, precision, and ROC-AUC—not accuracy alone
- Consider cost-sensitive modeling (false negatives are expensive)

---

## 10. Tools & Technologies

- Python (Pandas, NumPy)
- Scikit-learn
- Seaborn & Matplotlib
- Google Colab

---

## 11. Project Assets

- 📄 Full Analysis (PDF): reports/loan-default-analysis.pdf
- 📓 Notebook: notebooks/loan_default_prediction.ipynb

---

## 12. Key Takeaway

This project demonstrates not just model building, but **critical evaluation of model usefulness in real-world financial decision-making**.
