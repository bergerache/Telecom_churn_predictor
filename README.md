# 🎯 Telecom Customer Churn Prediction

> **Machine learning solution to predict customer churn and enable proactive retention strategies**
---

## 🚀 Business Problem

Telecom operators face significant challenges with customer retention, as **customer acquisition costs are typically 5-25x higher** than retention costs. This project develops a machine learning solution to identify customers at risk of churning, enabling Interconnect to offer targeted promotional codes and special plans before customers leave.

### 💡 Why This Matters
- **Proactive retention strategies** through early churn identification
- **Optimize marketing spend** by targeting high-risk customers
- **Reduce revenue loss** from customer defection
- **Increase customer lifetime value** through data-driven interventions

---

## 📊 Dataset Overview

Multi-source dataset from Interconnect telecom operator including **7,043 customers**:

| **Data Source** | **Key Features** |
|---|---|
| 📋 **Contract Information** | Begin/end dates, contract types, billing preferences, payment methods |
| 👤 **Personal Data** | Demographics, senior citizen status, family information |
| 🌐 **Internet Services** | DSL/Fiber connections, security features, streaming services |
| 📞 **Phone Services** | Multiple line options and usage patterns |

### 🎯 **Target Variable**
- **26.5% churn rate** (1,869 churned customers out of 7,043)
- **Business-critical imbalance** requiring specialized handling

---

## 🔬 Methodology

### 🧹 **Data Preprocessing & Engineering**
- **Multi-source integration**: Merged 4 datasets using customer ID joins
- **Date processing**: Converted contract dates to identify active vs churned customers
- **Missing value treatment**: Filled gaps with business logic (new customers = 0 total charges)
- **Feature engineering**: Created `duration_days` from contract length for enhanced variability
- **Categorical encoding**: Mapped text values to numeric (Yes/No → 1/0, contract types → 0/1/2)

### 📈 **Exploratory Data Analysis**
Key business insights discovered:

| **Finding** | **Churn Impact** |
|---|---|
| 📝 **Electronic check payments** | Higher churn rates - potential payment friction |
| 📅 **Month-to-month contracts** | Significantly higher churn vs annual contracts |
| 💰 **Monthly charges** | Churned customers average ~$80 vs $65 for retained |
| 🌐 **Fiber optic service** | Highest churn ratio - service quality issues |
| ⏱️ **Contract duration** | Longer tenure strongly correlates with retention |

### 🤖 **Model Development**
Implemented comprehensive ML pipeline:

```python
# Models Tested
├── Dummy Classifier (Baseline)
├── Logistic Regression 
├── Random Forest
├── Gradient Boosting ⭐ (Best Performer)
└── AdaBoost
```

**Advanced Techniques:**
- **SMOTE oversampling** for class imbalance handling
- **MinMax scaling** for feature normalization  
- **GridSearchCV** for hyperparameter optimization
- **Cross-validation** with F1-score optimization

### 📊 **Model Evaluation Strategy**
**F1-score selected as primary metric** - balances precision and recall for business impact where both false positives (unnecessary interventions) and false negatives (missed churners) carry costs.

---

## 🎯 Key Results

### 🏆 **Best Model: Gradient Boosting**
- **F1-Score: 0.79** (2.8x better than baseline)
- **Overall Accuracy: 89%**
- **Precision: 82%** - High confidence in churn predictions
- **Recall: 76%** - Captures 3 out of 4 potential churners

### 📊 **Model Comparison**

| **Model** | **F1-Score** | **Accuracy** | **Business Value** |
|---|---|---|---|
| Dummy Classifier | 0.28 | 61% | Baseline |
| Logistic Regression | 0.66 | 77% | Good interpretability |
| Random Forest | 0.67 | 79% | Feature importance insights |
| **Gradient Boosting** | **0.79** | **89%** | **Optimal performance** |
| AdaBoost | 0.74 | 86% | Strong alternative |

### 🔍 **Key Predictive Factors**
1. **Contract Type** - Month-to-month customers at highest risk
2. **Payment Method** - Electronic check users show elevated churn
3. **Service Tenure** - Newer customers more likely to leave
4. **Monthly Charges** - Price sensitivity impacts retention
5. **Internet Service Type** - Fiber optic users require attention

---

## 💼 Business Impact

### 🎯 **Immediate Actionable Insights**
- **Target month-to-month customers** with loyalty programs
- **Improve electronic check payment experience** 
- **Focus retention efforts on fiber optic subscribers**
- **Implement graduated pricing** for high-charge customers
- **Enhance onboarding** for new subscribers (first 90 days critical)

### 📈 **Expected ROI**
- **76% recall rate** enables proactive intervention for majority of at-risk customers
- **82% precision** minimizes wasted marketing spend on false positives
- **Early intervention** potential saves acquisition costs for retained customers

---

## 🛠️ Technical Implementation

<div align="center">

**Core Technologies**
```
Python | Pandas | NumPy | Scikit-learn
Matplotlib | Seaborn | Jupyter Notebook
```

**Advanced Techniques**
```
SMOTE Oversampling | MinMax Scaling
Grid Search CV | Feature Engineering
Ensemble Methods | Statistical Analysis
```

</div>

---

## 📁 Project Structure

```
📦 Telecom_churn_predictor/
├── 📓 Telecom_churn_predictor.ipynb    # Complete analysis & methodology
├── 📊 data/
│   ├── contract.csv                    # Contract information
│   ├── personal.csv                    # Customer demographics  
│   ├── internet.csv                    # Internet service data
│   └── phone.csv                       # Phone service data
├── 📋 README.md                        # Project overview
└── 📄 requirements.txt                 # Environment dependencies
```

---

## 🚀 Quick Start

```bash
# Clone repository
git clone https://github.com/bergerache/Telecom_churn_predictor.git

# Install dependencies  
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn

# Launch analysis
jupyter notebook Telecom_churn_predictor.ipynb
```

---

## 🔮 Business Applications

| **Use Case** | **Implementation** |
|---|---|
| 🎯 **Targeted Campaigns** | Score customers monthly, prioritize top 20% risk |
| 📞 **Retention Calls** | Automated alerts for high-risk customer segments |
| 💰 **Pricing Strategy** | Adjust pricing based on churn probability scores |
| 🎁 **Promotional Offers** | Customize incentives by risk factors and preferences |

---

## 🏦 Banking & Fintech Applications

While this model was trained on telecom data, the methodology directly applies to financial services churn scenarios:

| Telecom Scenario | Banking Equivalent |
|------------------|-------------------|
| Customer cancels service | Account closure / Product attrition |
| Contract type impact | Fixed-term vs flexible savings |
| Payment method friction | Direct debit vs manual payment |
| Tenure analysis | Customer relationship length |
| Monthly charges sensitivity | Fee sensitivity / Price elasticity |
| Service usage patterns | Transaction frequency / Product utilisation |

### Direct Applications

- **Deposit Account Churn** — Predicting customers likely to close current/savings accounts
- **Credit Card Attrition** — Identifying cardholders at risk of cancellation
- **Mortgage Refinancing** — Flagging customers likely to switch lenders
- **Investment Platform** — Early warning for ISA/pension transfer risk

### Why This Transfers

The feature engineering approach (tenure analysis, usage patterns, contract terms) translates directly to banking KPIs:
- Account age → Customer tenure
- Monthly charges → Fee revenue per customer
- Contract type → Product type (fixed/flexible)
- Payment method → Direct debit adoption
- Multiple services → Product holding depth

---

## 📖 Detailed Analysis

**🔗 [View Complete Jupyter Notebook](https://nbviewer.org/github/bergerache/Telecom_churn_predictor/blob/main/Telecom_churn_predictor.ipynb)**

*Comprehensive methodology, EDA insights, model development, and business recommendations*

---

<div align="center">

**Built for data-driven customer retention**

*Transforming customer behavior analysis into strategic business value*

</div>

