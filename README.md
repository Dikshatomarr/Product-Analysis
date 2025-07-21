# Product Analytics Dashboard with Alteryx, Python, and Power BI

## Executive Summary
This end-to-end product analytics project aims to simulate a real-world scenario for an app similar to Jar or Slice. The goal is to analyze user behavior, transaction patterns, and revenue performance using an integrated modern data stack.

- Tools Used: Alteryx, Python, Power BI
- Business Goal: Understand user conversion, retention, and revenue generation across the user lifecycle.
- Output: Cleaned datasets, exploratory data analysis, and dynamic dashboards.

**Business Problem**:  
A FinTech startup offering savings and cashback features noticed user churn after signup and unclear patterns in transaction behavior. The business wanted to understand:

- Which stages in the funnel cause drop-offs?  
- Which marketing channels acquire the highest LTV users?  
- How do transaction trends vary over time and demographics?  
- What strategies can improve retention and lifetime value?

## 🔧 Project Architecture (Diagram)

```
Raw Data  
│  
├── 🧹 Alteryx: Data Cleaning (Event, Transaction, Users)  
│  
├── 📊 Python: EDA + Metrics  
│  
├── 📈 Power BI: Dashboard Building  
````

**Approach**:  
Performed data cleaning using **Alteryx**, conducted **EDA in Python** across 50K+ records, and built an interactive **Power BI dashboard** covering acquisition, product engagement, and revenue analysis.

**Key Impact**:
- Identified 2 funnel stages with high user drop-off  
- Revealed signup channels with the highest LTV contribution  
- Suggested personalized retention strategies for top-value user segments  


## 🛠️ Tech Stack

| Tool       | Purpose                             |
|------------|-------------------------------------|
| Alteryx    | Data cleaning & joining Excel files |
| Python     | EDA and data visualization          |
| Power BI   | Interactive dashboard creation      |
| Excel      | Source data input                   |


## 🎯 Objective

- Analyze user engagement across funnel stages  
- Measure impact of signup channels on LTV  
- Visualize transaction trends and revenue growth  
- Identify customer segments for retention strategies  
- Provide actionable insights to reduce drop-off and increase CLTV  


## 📊 Dataset Overview

Cleaned datasets derived from Alteryx workflows.

| Column              | Description                                      |
|---------------------|--------------------------------------------------|
| user_id             | Unique ID per user                               |
| signup_channel      | Channel user used to register                    |
| signup_date         | Date of registration                             |
| event_type          | Product actions (signup, view, cart, purchase)   |
| event_time          | Timestamp of each event                          |
| transaction_id      | Unique transaction reference                     |
| transaction_date    | Date of purchase                                 |
| amount              | Final transaction amount                         |


## ⚙️ Process Summary

### 1. Alteryx – Data Cleaning  
- Cleaned and joined 3+ Excel files from raw exports
- Standardized date formats and user IDs
- Removed nulls, duplicates, and inconsistent channel names
- Derived fields for time-based analysis (monthly, quarterly)
- Created flags like is_kyc_completed, is_successful, and device_web_flag
- Enriched event and transaction data by joining user info
- Handled missing referral sources by assigning "Unknown"
- Calculated days_since_signup to support cohort analysis

* **Raw files:** `events.csv`, `transactions.csv`, `users.csv`
* **Cleaned files:** `events_clean.xlsx`, `transactions_clean.xlsx`, `users_clean.xlsx`


### 2. Python – Exploratory Data Analysis (EDA)

Performed EDA using `pandas`, `matplotlib`, and `seaborn`.

#### Key Metrics:
- Total Users: 5,000  
- Events Logged: 265,000+  
- Transactions: ~21,000  
- Signup Channels: Organic, Referral, Paid Ads, Social

#### Funnel Analysis:
- **Top Drop-off Point**: From “KYC submitted” → “Payment Successful”  
- ~60% users do not reach checkout after engaging with a product

#### LTV Analysis:
- User LTV increased steadily from ₹13K (Feb 2024) to over ₹17K (Jan 2025), indicating stronger monetization over time
- Highest LTV: Jan 2025 (₹17,076); Lowest: Feb 2024 (₹13,073)
- September 2024 had both high user volume and LTV (₹16,883) — likely a result of successful campaigns
- Despite low signup volume in Jul 2025, LTV remained high (₹15,692), suggesting niche high-intent users-
- Overall trend points to improved retention and user quality in recent cohorts

#### Revenue Trends:
- Top signup months by total revenue were March 2025, January 2025, and February 2025, all crossing ₹18L+ in revenue.
- January 2025 users had the highest LTV per user (~₹17,077), indicating excellent monetization or retention.
- Lower performing signup cohorts in terms of both revenue and LTV were Feb, Dec, and Mar 2024—likely candidates for product, onboarding, or retention optimization.
- Overall, early 2025 cohorts outperform 2024 cohorts, showing improved customer quality and business growth.

### 3. Power BI – Dashboard Creation

**📈 Key Visuals:**:

- Users by Acquisition Channel – Understand where users come from.
- User Distribution by Device – See which platforms are used most.
- Revenue by Acquisition Channel – Identify high-value channels.
- Monthly Active Users (MAU) – Track user engagement over time.
- Transaction Success Rate – Spot friction in payment flow.
- Funnel Drop-off – See where users drop off in conversion.
- Revenue by Category – Analyze top-performing product categories.
- Transactions by Payment Method – Know user payment preferences.
- LTV Analysis – Measure lifetime value by signup cohort.


## 🔍 Key Insights

| Area                 | Finding                                                                 |
|----------------------|-------------------------------------------------------------------------|
| **Funnel Drop-off**  | Major drop-off observed from KYC to Payment stage – indicating user trust issues or payment friction. |
| **Channel Performance** | Organic and Referral channels show significantly higher LTV compared to Paid channels. |
| **Revenue Trends**   | Revenue peaks in January, April, and November; over 70% of revenue comes from repeat users. |
| **Time-Based Insights** | February and July show consistent dips in revenue – highlighting untapped growth opportunities. |
| **LTV Distribution** | Highly skewed user contribution – top 10% of users generate nearly 50% of total revenue. |


## ✅ Business Recommendations

- **Refine Funnel UX**  
  Simplify the KYC and payment experience; add social proof, security badges, or urgency triggers to reduce drop-off.

- **Amplify Referral Program**  
  Scale high-performing acquisition channels by increasing rewards and gamifying referrals.

- **Optimize Paid Campaigns**  
  Focus ad spend on high-intent segments and optimize creatives based on lifetime value, not just CTR or installs.

- **Seasonal Campaigning**  
  Launch targeted cashback or discount campaigns in February and July to smoothen revenue volatility.

- **Retention Playbook**  
  Use behavior-based segmentation to send nudges and personalized offers to top 20% high-value users.

- **Cross-Sell/Upsell Strategy**  
  Identify premium or high-margin categories and recommend them to loyal, repeat-purchase users.


## 📈 Business Impact

This analysis enabled:
- Reduction of drop-off by identifying weakest funnel stages  
- Smarter ad spend by focusing on high-LTV channels  
- Seasonal planning based on transaction trends  
- Clear recommendations for user retention and upselling

## Dashboard Preview

<img width="1284" height="709" alt="image" src="https://github.com/user-attachments/assets/69d37d96-5107-4565-8a54-14b419e8a19f" />

<img width="1270" height="714" alt="image" src="https://github.com/user-attachments/assets/7736f7cb-e076-4d5c-84d1-3f254ce8fa2b" />


