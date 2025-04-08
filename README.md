# PowerCo Project
BCG's client is PowerCo - a major gas and electricity utility that supplies to small and medium-sized enterprises.

## 🚀 Project Overview

**Business Context**:  
Customer churn is a significant challenge in subscription-based services like utilities. Retaining existing customers is often more cost-effective than acquiring new ones.

**Goal**:  
To analyze client and pricing data, engineer meaningful features, and build a machine learning model to predict churned customers. This helps the business focus on retention strategies.

---
## 🔍 Project Workflow

### 1. Exploratory Data Analysis (EDA)

In this phase, we:

- Analyzed the churn distribution: Found ~10% churn rate — relatively healthy.
- Explored relationships between churn and features like:
  - Sales Channel
  - Contract Type
  - Number of Products
  - Number of Years
  - Consumption and Power Usage
- Discovered that some sales channels had **0% churn**, while others had varied churn levels.
- Identified **skewed distributions** and **outliers** in numerical features using histograms and boxplots.
  
### 2. Feature Engineering

This step included:

- **Price Sensitivity Features**:
  - `avg_price_diff`: Average price change across peak, mid-peak, and off-peak.
  - `max_price_diff`: Maximum price difference across all months and periods.
- **Transformations**:
  - Converted `date` into month-based numerical features.
  - Converted booleans to binary.
  - Categorical features → One-hot encoding (dummies).
- **Skewness Treatment**:
  - Applied logarithmic transformation to skewed features (e.g., `consumption`, `forecast`, etc.)
- **Correlation Analysis**:
  - Identified multicollinearity and highlighted features that might be redundant.

### 3. Predictive Modeling

- Used **Random Forest Classifier** for prediction.
- Performed **Train-Test Split** to avoid overfitting and simulate real-world predictions.
- **Model Evaluation** based on:
  - **Accuracy**: Overall correct predictions.
  - **Precision**: Correct churn predictions among predicted churn.
  - **Recall**: Correct churn predictions among actual churn.

**Findings**:
- The model predicts non-churners well (high accuracy), but struggles to detect actual churners (low recall).
- Indicates a need for better feature engineering or balancing techniques (e.g., SMOTE).

---
## 📊 Key Insights

- `Net Margin` and `12-month Consumption` were among the most important features.
- Price sensitivity features did not contribute significantly to predicting churn in their current form.
- Skewed distributions and class imbalance affected model performance.

---

## 🛠 Tech Stack & Tools

- **Python 3.10+**
- **Jupyter Notebook**
- **Pandas & NumPy** – Data manipulation
- **Matplotlib & Seaborn** – Visualization
- **Scikit-learn** – Machine learning and evaluation
- **Log Transformation** – Skewness treatment
- **OneHotEncoder / pd.get_dummies** – Categorical encoding

---

