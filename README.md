# Swire Coca-Cola: Predicting Cart Abandonment on MyCoke360

## Overview  
This project focuses on predicting cart abandonment behavior on MyCoke360, Swire Coca-Cola’s B2B ordering platform.  
Many customers add products to their carts but fail to complete the purchase before the order window closes.  

The goal of this project is to develop a machine learning model that predicts which customers are likely to abandon their carts within the first 30% of their GA4 (Google Analytics) event window, allowing the business to intervene early and reduce lost revenue.  

---

## Business Problem  
MyCoke360 faces a significant cart abandonment challenge:  
- 14.6% of carts that start with an Add-to-Cart event are never purchased.  
- This results in approximately $2.87 million in potential lost revenue per order cycle.  
- Certain customer segments and operational modes experience higher abandonment, such as Restaurants, Hotels, and the “Tell Sell” distribution channel.  

The goal is to identify these at-risk carts early and design targeted interventions such as reminders, incentives, or improved user experience flow.  

---

## Objectives  
- Build a supervised learning model to predict cart abandonment within the first 30% of the order window.  
- Improve Swire’s ability to target interventions for high-risk customers.  
- Quantify potential financial recovery under different success rates.  
- Provide actionable insights for business and operational improvement.  

---

## Data and Methodology  

### 1. Data Sources  
We combined multiple data tables to create unique customer-level order windows:  
- Orders  
- Sales  
- Visit Plans  
- Cutoff Times  
- Google Analytics (GA4)  

### 2. Label Definition  
A customer is labeled as “abandoned” if they added to cart but did not place an order within their order window.  

### 3. Feature Engineering  
- Built rolling customer windows (anchor-based).  
- Computed cart-to-purchase ratios and timing features.  
- Aggregated GA events per window.  
- Aligned all timestamps in customer-local time zones.  

---

## Exploratory Data Analysis (EDA)  

Key insights:  
- Overall Abandonment Rate: 14.6%  
- Highest by Customer Type: Restaurants, Stores, Hotels (~15–17%)  
- Distribution Mode: “Tell Sell” shows ~30% abandonment  
- Shipping Condition: Longer 72-hour delivery windows → ~22% abandonment; shorter 24–48-hour → ~10–15%.  

These findings suggested that customer type, shipping speed, and channel are strong predictors for the modeling phase.  

---

## Modeling Approach  

Two XGBoost models were trained and compared:  

| Model | Accuracy | Recall | Focus |
|:------|:---------:|:------:|:------|
| Baseline (Balanced) | 89.2% | 43.2% | High precision, misses many abandoners |
| Recall-Tuned | 81.8% | 71.2% | Captures more abandoners early for proactive outreach |

We prioritized recall because the cost of missing a potential abandoner is much higher than mistakenly targeting an active customer.  

---

## Key GA4 Events  
Frequent events linked to abandonment:  
- update_cart  
- button_click  
- ContinueShopping_Cart_Clicked  
- user_engagement  
- SelectAll_Cart_Unchecked  

Events linked to successful conversions:  
- add_payment_info  
- begin_checkout  
- SelectAll_Cart_Checked  

---

## Recommendations  

1. Target early interventions at the 30% mark of the GA event window.  
2. Focus marketing and reminders on Restaurant, Store, and Hotel customers.  
3. Reduce friction in the checkout process (simplify Add-to-Cart → Purchase flow).  
4. Address Tell Sell performance — optimize communication and ordering process.  
5. Shorten or incentivize faster shipping to reduce long-window abandonment.  

---

## Financial Impact Simulation  

| Intervention Success Rate | Carts Saved | Revenue Recovered |
|:--------------------------:|:------------:|:------------------:|
| 5%  | 101  | $102,037 |
| 15% | 304  | $306,113 |
| 25% | 507  | $510,189 |
| 50% | 1,015 | $1,020,378 |
| 75% | 1,523 | $1,530,567 |

A modest 25% success rate could recover over $500K in potential revenue.  

---

## Future Scope  
- Apply customer segmentation to tailor reminders and promotions.  
- Continuously retrain models with new GA4 behavioral data.  
- Integrate real-time prediction APIs into MyCoke360’s CRM system.  
- Develop dashboards to monitor abandonment in near real-time.  

---

## Repository Structure  


