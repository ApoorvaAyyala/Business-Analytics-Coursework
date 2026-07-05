# Business-Analytics-Coursework
As a part of Mtech Coursework, I have performed the following analysis during 4 months of the lab practicals we had
## I. 📊 Telco Customer Churn Prediction & Analysis

[Download Customer Churn Prediction.xlsx](https://github.com/ApoorvaAyyala/Business-Analytics-Coursework/blob/main/Customer%20Churn%20Prediction.xlsx)

An end-to-end data analysis and machine learning project focused on identifying the driving factors behind telecom customer churn and validating a predictive risk model. This repository contains the data transformations, evaluation metrics, and core business findings derived from historical subscriber lifecycles.

---

### 📂 Project Structure

The underlying data and model workflows are structured into four primary analytic stages:

* **`Telco_Churn` (Raw Baseline Data)**: Contains ground-truth subscriber demographics, geographic attributes, account characteristics (Tenure, Contract, Monthly Charges), Customer Lifetime Value (CLTV), and categorical qualitative reasons for cancellation (`Churn Reason`).
* **`Model_Data` (ML Staging & Evaluation)**: Holds the mapped feature encodings (`Gender_Value`, `Contract_Value`, `Internet_Value`), calculated probabilities (`Churn_Risk_Score`), and binary model decisions (`Predicted_Churn`).
* **`Scatter Plot` Data**: An isolated feature set mapping the raw mathematical relationship between **Tenure Months** and empirical **Churn Value**.
* **`Column Chart` Data**: A subset tracking the specific behavior and concentration of **Monthly Charges** across churn cohorts.

---

### ⚙️ Methodology & Processing Pipeline

#### 1. Feature Engineering
Categorical variables critical to subscriber profiles were vectorized into numeric spaces to prepare them for risk-modeling:
* `Contract` $\rightarrow$ `Contract_Value`
* `Internet Service` $\rightarrow$ `Internet_Value`
* `Gender` $\rightarrow$ `Gender_Value`

#### 2. Model Execution & Performance
A risk-scoring model calculated a continuous probability (`Churn_Risk_Score`) for each account. Subscribers crossing the optimized threshold were classified with a predicted churn marker (`Predicted_Churn = 1.0`).

The predictive model achieved an evaluation accuracy of **64.48%** across the entire population ($N = 7,043$).

##### Confusion Matrix Matrix Breakdown:
* **True Negatives (Correctly predicted to Stay)**: 4,166
* **False Positives (Incorrectly flagged as Churn)**: 1,008
* **False Negatives (Missed Churn events)**: 1,494
* **True Positives (Correctly flagged as Churn)**: 375

---

### 🎯 Key Business Findings & Conclusions

#### 🚨 Core Drivers of Attrition
Aggregating the explicit feedback fields within the dataset reveals that competitor market aggressive offerings and poor customer service represent the primary drivers of subscriber loss:

| Rank | Churn Reason | Account Count | Risk Category |
| :---: | :--- | :---: | :--- |
| **1** | Attitude of support person | 192 | Customer Service Quality |
| **2** | Competitor offered higher download speeds | 189 | Product Feature/Competitor |
| **3** | Competitor offered more data | 162 | Product Feature/Competitor |
| **4** | Don't know | 154 | Unmapped |
| **5** | Competitor made better offer | 140 | Pricing Strategy/Competitor |

#### 💡 Primary Conclusions
* **The Critical "First 2 Months" Onboarding Window**: Analysis of the tenure distributions confirms a significant density of customer churn during months **1 and 2**. If a subscriber passes this initial introductory threshold, their probability of long-term retention increases drastically.
* **High Monthly Financial Friction**: Higher standard `Monthly Charges` heavily correlate with shortened customer lifecycles. High-tier subscribers on rolling month-to-month contracts exhibit the highest systemic elasticity to competitive poaching.
* **Service Interaction Points are Revenue Leaks**: Frontline interaction is a major vulnerability. More subscribers explicitly left due to the negative **"Attitude of support person"** than due to competitor pricing or promotional discounts.

---

### 🚀 Strategic Recommendations

1. **Mandatory Support Staff Retraining**: Implement structural empathy and efficiency-driven training programs for technical support representatives to control the primary explicit driver of operational churn.
2. **Aggressive 60-Day Customer Onboarding**: Deploy automated, targeted loyalty incentives, check-ins, or usage tutorials during the **first 60 days** of a contract to safely navigate the high-risk onboarding cliff.
3. **Competitive Data Tier Optimization**: Perform a thorough review of high-speed data structures to match or beat competitor download thresholds, neutralizing premium tier poaching.

## II.📦 Daily Demand Forecasting Model

[Download Demand Forecasting.xlsx](https://github.com/ApoorvaAyyala/Business-Analytics-Coursework/blob/main/Demand%20Forecasting.xlsx)

This project establishes a statistical framework for predicting logistical demand workflows by mapping internal order characteristics and external sector orders against total incoming daily volumes. The predictive architecture utilizes multiple linear regression to forecast daily capacity needs.

The entire dataset and regression pipeline are contained within the file **"Demand Forecasting.xlsx"**.

---

### 📂 Project & Dataset Structure

The analysis workspace in **"Demand Forecasting.xlsx"** is split into four core functional sheets:

* **`Daily Demand Forecasting Orders`**: The baseline raw transactional database. Tracks 60 operational day cycles across calendar contexts, item urgency, order item breakdowns, and specific corporate sector requests.
* **`Data Moldel`**: The core execution sheet containing true historical totals side-by-side with modeled predictions, paired with granular mathematical validation metrics (`Absolute Error`, `Error Square`).
* **`Analysis`**: The statistical engine tracking the complete Multiple Linear Regression summary outputs, variance indicators (ANOVA), and variable significance metrics generated via Excel Data Analysis ToolPak.
* **`Interpretation`**: High-level documentation detailing operational constraints, core metrics tracked, and final structural performance results.

---

### 📊 Variables & Mathematical Framework

#### Input Features (Independent Variables)
1. **Temporal Context**: `Week of the month`, `Day of the week` (Monday to Friday tracking)
2. **Priority Tiers**: `Non-urgent orders`, `Urgent orders` 
3. **Item Sub-classifications**: `Order type A`, `Order type B`, `Order type C`
4. **B2B Sector Volume Requests**: `Fiscal sector orders`, `Orders from the traffic controller sector`
5. **Financial Demands**: `Banking orders (1)`, `Banking orders (2)`, `Banking orders (3)`

#### Output Variable (Dependent Variable)
* **`Target (Total orders)`**: Sum total of overall daily operational order volumes.

---

### ⚙️ Model Evaluation & Performance

A Multiple Linear Regression engine was deployed over $N = 60$ historical daily observations. 

#### Regression Statistics
* **Multiple R**: 1.0000
* **R-Square ($R^2$)**: 1.0000  
* **Adjusted R-Square**: 1.0000  
* **Standard Error**: 0.0000

#### Mathematical Insight
The perfect mathematical fit ($R^2 = 1.0$) is driven by the structural composition of the dataset features. Regression coefficient analysis demonstrates that the dependent variable `Target (Total orders)` is a perfect deterministic function composed directly of the subset items:
$$\text{Target (Total orders)} = \text{Order type A} + \text{Order type B} + \text{Order type C}$$

Because individual sub-classes explicitly sum up to the target variable, the model yields a flawless predictive performance profile with zero residual variance ($SS_{\text{residual}} = 0.0$).

---

### 🎯 Strategic Conclusions

* **High Operational Reliability**: The model acts as a flawless validation tool for incoming inventory totals. Predictions map with near-zero error margins, ensuring total clarity when auditing logistics workflows.
* **Deterministic Scaling**: Because total order volume scales directly with the distribution of specific sub-categories (Types A, B, and C), strategic planning should prioritize early-stage monitoring of these sub-classes to balance processing warehouse allocations.
* **Predictive Performance**: Overall, the historical validation tracks completely clean, proving highly effective for calculating future distribution requirements if early subclass patterns are known.

