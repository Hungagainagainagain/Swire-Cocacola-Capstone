# Swire Coca-Cola: Predicting Cart Abandonment on MyCoke360  

## Project Overview  
This project was completed in collaboration with **Sudeeptha Sivarajan,Hung Duong, Finlay Dunn, and Shawal Fidal** using **real business data from Swire Coca-Cola**.  
Our goal was to use data analytics and machine learning to **predict cart abandonment behavior** on Swire’s **MyCoke360** B2B ordering platform.  

---

## Understanding Cart Abandonment  
Cart abandonment occurs when customers add items to their online cart but fail to complete their purchase before the order window closes.  

For Swire Coca-Cola, this issue represents a major challenge on the MyCoke360 platform, where:  
- A significant portion of carts that begin with “Add to Cart” events never result in completed orders.  
- This leads to lost sales opportunities, operational inefficiencies, and lower customer satisfaction.  

Our project focused on identifying these at-risk customers **within the first 30% of the order window**, allowing for early interventions such as reminders, incentives, or personalized outreach.  

---

## Key Results  
We trained multiple supervised learning models, including Logistic Regression and XGBoost, to predict the likelihood of cart abandonment.  

Our final model, built using XGBoost, achieved:  
- **Accuracy:** 81.8%  
- **Recall:** 71.2%  

We prioritized **recall** since the business impact of missing a potential abandoner is greater than mistakenly targeting a customer who would have completed the purchase anyway.  
This model allows Swire Coca-Cola to capture most abandonment cases early and target them effectively to recover potential revenue.  

---

## Future Recommendations  
Based on our findings, we recommend that Swire Coca-Cola:  
1. **Intervene early** — trigger automated reminders at 30% of each order window.  
2. **Focus on high-risk customer types** such as restaurants, hotels, and stores.  
3. **Improve checkout flow** — reduce friction between Add-to-Cart and payment completion.  
4. **Optimize distribution modes** — address high abandonment in “Tell Sell” operations.  
5. **Incentivize faster shipping options** — customers with shorter delivery windows are less likely to abandon.  
6. **Continue model retraining** as new Google Analytics data becomes available to adapt to changing behavior.  

---

## File Guidance  

This repository documents our full workflow from data exploration to modeling and presentation.  
Below is a short guide to help navigate each file and its purpose.

### 1. Exploratory Data Analysis (EDA)
Each team member conducted individual EDA to understand different aspects of the data.  
These analyses were later merged into our consolidated files:  
- `Sql&SodaFinal.ipynb` – Combined EDA notebook with visualizations and insights.  
- `Sql&SodaFinal.html` – HTML export for easy viewing.  

These files explore customer types, order frequency, abandonment rates, and relationships between order behavior and GA4 events.

---

### 2. Data Engineering
We created a **master table** to unify all sources and generate customer-level order windows.  
This included dynamically adjusting for each customer’s **changing order frequency** and **cutoff time** to define their purchasing window.  

The output of this process is stored in:  
- `new_master.csv` – The cleaned, structured dataset with exploded window-level orders for each customer.

---

### 3. Modeling
We integrated modeling work from all team members into a final, unified notebook.  

The following files represent different stages and iterations of model development:  
- `Finlay-Modeling.ipynb`  
- `Modelling_Final.ipynb`  
- `sudeeptha-Copy1.ipynb`  
- `hung_modeling.ipynb`  

After extensive synthesis, we consolidated these approaches into:  
- `modeling_new_logic copy 2.ipynb` – The final modeling notebook where the **XGBoost model** was trained and optimized.  
This file contains our finalized feature set, parameter tuning, and model evaluation metrics.  

---

### 4. Presentation
Our business presentation summarizing findings, visuals, and recommendations can be viewed here:  
- [`Swire Coca Cola.pdf`](Swire%20Coca%20Cola.pdf)

This presentation outlines the business problem, analytical process, key insights, model performance, and actionable strategies for Swire’s decision-makers.

---

## Summary
Through this collaboration, we successfully demonstrated how predictive analytics can identify customers at risk of cart abandonment and provide meaningful recommendations to recover lost revenue and improve user engagement on MyCoke360.  

The project combines **real business data**, **data engineering**, **machine learning modeling**, and **business storytelling** to deliver actionable insights for Swire Coca-Cola’s digital sales operations.

---

## Repository Structure  


