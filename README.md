# Supply_Chain_Analysis

## Overview
This project involves analyzing a supply chain dataset to extract insights into shipping performance, customer segmentation, and profitability. The process includes data preprocessing, feature engineering, exploratory data analysis (EDA), and visualization. The goal is to identify key factors affecting supply chain efficiency and profitability.

---

## Table of Contents
1. [Dataset Description](#dataset-description)
2. [Project Workflow](#project-workflow)
3. [Feature Engineering](#feature-engineering)
4. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
5. [Machine Learning Models](#machine-learning-models)
6. [Key Findings](#key-findings)
7. [Technologies Used](#technologies-used)
8. [How to Run](#how-to-run)

---

## Dataset Description
The dataset used in this project is `DataCoSupplyChainDataset.xlsx`, which contains **180,519 rows** and **53 columns**. It includes information on:
- Shipping details: `Days for shipping (real)`, `Days for shipment (scheduled)`, `Delivery Status`, `Late_delivery_risk`.
- Customer demographics: `Customer Segment`, `Customer Country`, `Order Country`.
- Product details: `Product Price`, `Product Category Id`, `Order Item Discount`.
- Order details: `Order Profit Per Order`, `Order Item Quantity`.

### Key Variables:
- **Target Variable**: `Late_delivery_risk` (binary classification: 0 or 1).
- **Features**: Shipping days, product price, discount, profit ratio, customer segment, shipping mode.

---

## Project Workflow

### Step 1: Data Loading
- Imported the dataset using pandas (`read_excel`).
- Displayed the first few rows to understand the structure.

### Step 2: Data Cleaning
- Checked for missing values and inconsistencies.
- Dropped irrelevant columns such as product image URLs and redundant identifiers.
- Imputed missing values with appropriate strategies (e.g., mean for numerical fields).

### Step 3: Exploratory Data Analysis (EDA)
Performed visualizations and statistical analysis to understand:
- Distribution of shipping days (`Days for shipping (real)` vs. `Days for shipment (scheduled)`).
- Correlation between discounts and profit margins.
- Impact of customer segments on late delivery risk.

---

## Feature Engineering

### New Features Created:
1. **Log Transformation**:
   - Applied log transformation to skewed variables like `Order Item Discount` and `Order Item Product Price`.

2. **Power Transformation**:
   - Transformed variables such as `Order Item Profit Ratio` using power transformations to normalize distributions.

3. **Categorical Encoding**:
   - One-hot encoded categorical variables like `Shipping Mode` and `Order Status`.

4. **Interaction Features**:
   - Created interaction terms between shipping days and delivery status.

5. **Standardization**:
   - Standardized numerical features to bring them onto a similar scale.

---

## Exploratory Data Analysis (EDA)

### Key Visualizations:
1. **Shipping Days Analysis**:
   - Compared real vs scheduled shipping days using histograms.
   - Identified patterns in late deliveries.

2. **Profitability Analysis**:
   - Scatter plots showing the relationship between discounts and profit ratios.
   - Bar charts of average profit per customer segment.

3. **Delivery Risk Analysis**:
   - Examined the distribution of late delivery risks across different shipping modes.

---

## Machine Learning Models

### Algorithms Explored:
1. **Logistic Regression**:
   - Used for binary classification of late delivery risk.
   - Achieved baseline accuracy after hyperparameter tuning.

2. **Random Forest Classifier**:
   - Performed feature selection and handled imbalanced data well.
   - Achieved higher accuracy compared to Logistic Regression.

3. **Gradient Boosting (XGBoost)**:
   - Provided the best performance in terms of precision and recall.
   - Tuned hyperparameters such as learning rate and max depth for optimal results.

### Model Evaluation Metrics:
- Accuracy
- Precision
- Recall
- F1 Score
- AUC-ROC Curve

### Best Performing Model:
The XGBoost classifier outperformed other models with the highest F1 score and AUC values.

---

## Key Findings

1. **Shipping Delays**:
   - Longer real shipping days significantly increase late delivery risks.
   - Standard Class shipping mode has a higher probability of delays compared to Same Day or First Class modes.

2. **Customer Segmentation**:
   - Corporate customers are more profitable but have a higher likelihood of late deliveries.
   - Home Office customers exhibit the lowest average profits.

3. **Profitability Insights**:
   - Discounts negatively impact profit margins.
   - Certain product categories consistently yield higher profits irrespective of discounts.

4. **Feature Importance** (from Random Forest/XGBoost):
   - Top features influencing delivery risk include real shipping days, scheduled shipping days, product price, and order item discount.

---

## Technologies Used

The following Python libraries were used in this project:

- **pandas**: For data manipulation and cleaning.
- **matplotlib/seaborn**: For data visualization.
- **scikit-learn**: For machine learning models and evaluation metrics.
- **XGBoost**: For gradient boosting classifier.
- **NumPy**: For numerical computations.

---

## How to Run

### Prerequisites
Ensure you have Python installed along with the required libraries listed in `requirements.txt`.

## Commands to Setup Project on Local Machine

1. **Clone the repository:**
   ```bash
   git clone https://github.com/dyavadi8769/Supply_Chain_Demand_Forecasting_System.git
   cd Supply_Chain_Demand_Forecasting_System
2.  **Create a virtual environment and activate it:**
    ```bash
    conda create -p env python==3.11 -y
    conda activate env/ 
3.  **Install the Required Dependecies:**
    ```bash
    pip install -r requirements.txt

# Contributing
Contributions to this project are welcome. Please fork the repository and submit a pull request.

# Author:

```bash
Author: Sai Kiran Reddy Dyavadi
Role  : Data Scientist
Email : dyavadi324@gmail.com
```
