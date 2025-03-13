# 📊 [SQL] E-Commerce Sale Performance Analysis

Author: Xuan Luong

Date: 2024  

Tools Used: SQL/Google BigQuery

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)
3. [⚒️ Main Process](#--main-process)
4. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

### Objective:
Query eCommerce dataset to answer business inquiries.
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
<img width="800" alt="Image" src="https://github.com/user-attachments/assets/8e6e94cb-a8f3-4c70-9097-0d7e889884ac" />

* Query results

<img width="800" alt="Image" src="https://github.com/user-attachments/assets/52994a7e-ff41-4e7c-88b7-bd3955561eaa" />

<img width="800" alt="Image" src="https://github.com/user-attachments/assets/7a5bf7bc-4fda-49b3-8629-3ff506a61178" />

### Query 02: Bounce rate per traffic source in July 2017
* SQL code

![image]()

* Query results

![image]()

### Query 3: Revenue by traffic source by week, by month in June 2017
* SQL code

![image]()

* Query results

![image]()

### Query 04: Average number of product pageviews by purchaser type (purchasers vs non-purchasers) in June, July 2017
* SQL code

<img width="800" alt="Image" src="https://github.com/user-attachments/assets/8f2f2a0a-6a6a-40f1-8a8d-6b00fe95deff" />

* Query results

<img width="800" alt="Image" src="https://github.com/user-attachments/assets/a8524f45-1580-4cbd-a6aa-ce6f301dc7e0" />

### Query 05: Average number of transactions per user that made a purchase in July 2017
* SQL code

![image]()

* Query results

![image]()

### Query 06: Average amount of money spent per session. Only include purchaser data in July 2017
* SQL code

![image]()

* Query results

![image]()

### Query 07: Other products purchased by customers who purchased product "YouTube Men's Vintage Henley" in July 2017. Output should show product name and the quantity was ordered.
* SQL code

![image]()

* Query results

![image]()

### Query 08: Calculate cohort map from pageview to addtocart to purchase in last 3 month.
* SQL code
![image]()

* Query results
![image]()


---
## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following:  

📌 Key Takeaways:  
✔️ Recommendation 1  
✔️ Recommendation 2  
✔️ Recommendation 3

## V. Conclusion
* In conclusion, my exploration of the eCommerce dataset 
* By exploring eCommerce dataset, I have gained valuable information about total visits, pageview, transactions, bounce rate, and revenue per traffic source,.... which could inform future business decisions.
* To deep dive into the insights and key trends, the next step will visualize the data with some software like Power BI,Tableau,...
* **Overall**, this project has demonstrated the power of using SQL and big data tools like Google BigQuery to gain insights into large datasets.
