# 📊 [SQL] E-Commerce Sale Analysis

Author: Xuan Luong

Date: 2024  

Tools Used: SQL/Google BigQuery

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

### Objective:
Query eCommerce dataset to answer business inquiries.

### Actions: 
Used Google BigQuery platform to conduct queries on Google Analytics public dataset.

### Outcome: 
Provided insights on user behavior to enhance business strategies.

### 👤 Who is this project for?
✔️ Data analysts & business analysts  
✔️ Decision-makers & stakeholders  

###  ❓Business Questions:  
1. Calculate total visits, pageview, transactions for Jan, Feb, and March 2017 order by month
2. Bounce rate per traffic source in July 2017
3. Revenue by traffic source by week, by month in June 2017
4. Average number of pageviews by purchaser type (purchasers vs non-purchasers) in June, and July 2017.
5. Average number of transactions per user that purchased in July 2017
6. Average amount of money spent per session. Only include purchaser data in July 2017
7. Other products purchased by customers who purchased the product "YouTube Men's Vintage Henley" in July 2017. The output should show the product name and the quantity ordered.
8. Calculate cohort map from product view to "addtocart" to "purchase" in Jan, Feb, and March 2017 
  — for example, 100% product view then 40% add_to_cart and 10% purchase.
  Add_to_cart_rate = number product add to cart/number product view. 
  Purchase_rate = number product purchase/number product view.
  The output should be calculated in product level.

---
## 📂 Dataset Description & Data Structure  

### 📌 Data Source
The dataset is based on the Google Analytics public dataset and contains data from an eCommerce website.
Project on Google Cloud Platform, the project ID is "bigquery-public-data.google_analytics_sample.ga_sessions"
[Table Schema](https://support.google.com/analytics/answer/3437719?hl=en)


## Dataset Access
The eCommerce dataset is stored in a public Google BigQuery dataset. To access the dataset, follow these steps:
* Log in to your Google Cloud Platform account and create a new project.
* Navigate to the BigQuery console and select your newly created project.
* In the navigation panel, select "Add Data" and then "Search a project".
* Enter the project ID **"bigquery-public-data.google_analytics_sample.ga_sessions"** and click "Enter".
* Click on the **"ga_sessions_"** table to open it.

---
## ⚒️ Main Process
In this project, I will write 08 query in Bigquery base on Google Analytics dataset

### Query 01: Calculate total visit, pageview, transaction and revenue for January, February and March 2017 order by month
* SQL code

![image](https://user-images.githubusercontent.com/101726623/235141283-3f640e8c-237f-4100-b734-f0383a999560.png)

* Query results

![image](https://user-images.githubusercontent.com/101726623/235141359-1648197b-6339-42ca-b2a2-3dce9f39283b.png)

### Query 02: Bounce rate per traffic source in July 2017
* SQL code

![image](https://user-images.githubusercontent.com/101726623/235142111-5df9bb05-f29c-49e5-a1d8-3f7187667874.png)

* Query results

![image](https://user-images.githubusercontent.com/101726623/235142182-87c47ea0-4cae-41b8-8204-f17d774914d3.png)

### Query 3: Revenue by traffic source by week, by month in June 2017
* SQL code

![image](https://user-images.githubusercontent.com/101726623/235142542-556901cf-2087-4c72-94d4-0372546ad77d.png)

* Query results

![image](https://user-images.githubusercontent.com/101726623/235142590-e0fec692-794c-4247-a659-433ce605c158.png)

### Query 04: Average number of product pageviews by purchaser type (purchasers vs non-purchasers) in June, July 2017
* SQL code

![image](https://user-images.githubusercontent.com/101726623/235143185-85e4ffbe-1030-4f70-99c6-1571facdf3d8.png)

* Query results

![image](https://user-images.githubusercontent.com/101726623/235143315-8d87f354-351b-4218-ac77-bf8c0f9e716b.png)

### Query 05: Average number of transactions per user that made a purchase in July 2017
* SQL code

![image](https://user-images.githubusercontent.com/101726623/235143576-0a816953-e12d-4d47-ab8b-0a851e82a65c.png)

* Query results

![image](https://user-images.githubusercontent.com/101726623/235143708-06c7b447-5c1e-44bb-89ae-c5fed537bd92.png)

### Query 06: Average amount of money spent per session. Only include purchaser data in July 2017
* SQL code

![image](https://user-images.githubusercontent.com/101726623/235144017-2e40f75c-4374-4d2b-94cb-a36c591a80c2.png)

* Query results

![image](https://user-images.githubusercontent.com/101726623/235144083-3499b416-0388-46ea-850f-30006e1b4ede.png)

### Query 07: Other products purchased by customers who purchased product "YouTube Men's Vintage Henley" in July 2017. Output should show product name and the quantity was ordered.
* SQL code

![image](https://user-images.githubusercontent.com/101726623/235146761-aeb66e07-8f91-4c6f-a4c2-c3fb8d64708a.png)

* Query results

![image](https://user-images.githubusercontent.com/101726623/235146847-e367b16c-38f0-484e-8c89-85dfa1b69499.png)

### Query 08: Calculate cohort map from pageview to addtocart to purchase in last 3 month.
* SQL code

```
with get_1month_cohort as (SELECT  
  CASE WHEN 1 = 1 THEN "201701" END AS month,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "2" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_product_view,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "3" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_addtocart,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "6" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_purchase,
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_201701*` ,
UNNEST(hits) as hits,
UNNEST(hits.product) as product),

get_2month_cohort as (SELECT  
  CASE WHEN 1 = 1 THEN "201702" END AS month,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "2" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_product_view,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "3" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_addtocart,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "6" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_purchase,
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_201702*` ,
UNNEST(hits) as hits,
UNNEST(hits.product) as product),

get_3month_cohort as (SELECT  
  CASE WHEN 1 = 1 THEN "201703" END AS month,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "2" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_product_view,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "3" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_addtocart,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "6" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_purchase,
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_201703*` ,
UNNEST(hits) as hits,
UNNEST(hits.product) as product)

select 
month,
num_product_view,
num_addtocart,
num_purchase,
ROUND(num_addtocart/num_product_view*100,2) as add_to_cart_rate,
ROUND(num_purchase/num_product_view*100,2) as purchase_rate
from 
(SELECT * FROM get_1month_cohort
UNION ALL 
SELECT * FROM get_2month_cohort
UNION ALL
SELECT * FROM get_3month_cohort)
ORDER BY month;
```
* Query results

![image](https://user-images.githubusercontent.com/101726623/235148311-a2d83174-9bf3-43e3-aed1-47030af40b3b.png)

---
## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following:  

📌 Key Takeaways:  
✔️ Recommendation 1  
✔️ Recommendation 2  
✔️ Recommendation 3

## V. Conclusion
* In conclusion, my exploration of the eCommerce dataset using SQL on Google BigQuery based on the Google Analytics dataset has revealed several interesting insights.
* By exploring eCommerce dataset, I have gained valuable information about total visits, pageview, transactions, bounce rate, and revenue per traffic source,.... which could inform future business decisions.
* To deep dive into the insights and key trends, the next step will visualize the data with some software like Power BI,Tableau,...
* **Overall**, this project has demonstrated the power of using SQL and big data tools like Google BigQuery to gain insights into large datasets.
