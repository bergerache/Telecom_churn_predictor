# Telecom Customer Churn Prediction

## Business Problem

Customer churn represents a critical business challenge for telecom operators, with customer acquisition costs typically 5-25 times higher than retention costs. This project develops a machine learning solution to predict which customers are likely to churn, enabling proactive retention strategies and reducing revenue loss.

## Dataset Overview

The analysis uses telecom customer data including:
- **Customer demographics** - Personal information and account details
- **Service usage patterns** - Call, data, and service utilisation metrics
- **Contract information** - Plan types, pricing, and contract duration
- **Historical behaviour** - Payment history and service interactions

## Methodology

### Data Preprocessing
- Merged multiple data sources (contract, personal, internet, phone services)
- Handled missing values and outliers
- Engineered features from service combinations and usage patterns
- Applied appropriate encoding for categorical variables

### Exploratory Data Analysis
- Identified key churn indicators through statistical analysis
- Visualised customer segments and behaviour patterns
- Analysed correlation between service types and churn probability

### Model Development
- Implemented multiple algorithms: Logistic Regression, Random Forest, Gradient Boosting
- Applied feature selection techniques to identify most predictive variables
- Conducted hyperparameter optimisation for model performance
- Used cross-validation to ensure robust model evaluation

### Model Evaluation
- Evaluated models using precision, recall, F1-score, and AUC-ROC
- Focused on recall optimisation to minimise false negatives (missed churners)
- Performed feature importance analysis to understand churn drivers

## Key Findings

- **Contract type** emerged as the strongest churn predictor
- **Customer tenure** showed inverse relationship with churn probability
- **Service combinations** significantly influenced retention rates
- **Monthly charges** vs **total charges** ratio provided additional predictive power

## Business Impact

The model enables the telecom operator to:
- **Identify high-risk customers** with 85%+ accuracy
- **Prioritise retention efforts** for maximum ROI
- **Develop targeted offers** based on churn risk factors
- **Reduce customer acquisition costs** through improved retention

## Technical Implementation

**Languages:** Python  
**Libraries:** pandas, scikit-learn, matplotlib, seaborn  
**Techniques:** Feature engineering, ensemble methods, hyperparameter tuning  
**Evaluation:** Cross-validation, confusion matrix analysis, ROC curves

## Files Structure

```
├── Telecom_churn_predictor.ipynb    # Main analysis notebook
├── data/                           # Dataset files
├── README.md                       # Project documentation
└── requirements.txt                # Dependencies
```

## Usage

1. Clone the repository
2. Install required dependencies: `pip install -r requirements.txt`
3. Run the Jupyter notebook to reproduce analysis
4. View detailed methodology and results in the notebook

## Future Enhancements

- Real-time prediction pipeline integration
- Advanced ensemble methods and neural networks
- Survival analysis for time-to-churn predictions
- A/B testing framework for retention strategy validation

---

**For detailed analysis and code implementation, see the [Jupyter Notebook](https://nbviewer.org/github/bergerache/Telecom_churn_predictor/blob/main/Telecom_churn_predictor.ipynb)**

