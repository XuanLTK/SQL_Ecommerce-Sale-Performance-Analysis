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

## 
**Background & Overview ** 

### Objective:
Query eCommerce dataset to answer business inquiries.
Used Google BigQuery platform to conduct queries on Google Analytics public dataset.

### Outcome: 
Provided insights on user behavior to enhance business strategies.

### 👤 Who is this project for?
✔️ Senior management, including CEOs and marketing leaders  

###  ❓Business Questions:
Senior management, including CEOs and marketing leaders, are looking to leverage data and insights to gain a comprehensive understanding of the current business landscape, optimize performance, and improve customer experiences, thereby increasing productivity and business effectiveness.
To access the insights, the questions above have been broken down into more specific inquiries as follows:
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
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/8e6e94cb-a8f3-4c70-9097-0d7e889884ac" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/52994a7e-ff41-4e7c-88b7-bd3955561eaa" />

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/7a5bf7bc-4fda-49b3-8629-3ff506a61178" />


> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.


### Query 02: Bounce rate per traffic source in July 2017
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/52b69fc2-b52f-4fcd-bb2a-bc2e60e08da1" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/ad9fa54d-7b4e-4011-abba-7d7dec8bad33" />


> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.



### Query 3: Revenue by traffic source by week, by month in June 2017
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/d823b5f6-dd0f-48b8-8c65-2e449f140ff0" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/e8098c84-6de1-4329-97af-6d8a85ed0414" />


> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.


### Query 04: Average number of product pageviews by purchaser type (purchasers vs non-purchasers) in June, July 2017
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/8f2f2a0a-6a6a-40f1-8a8d-6b00fe95deff" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/a8524f45-1580-4cbd-a6aa-ce6f301dc7e0" />


> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.



### Query 05: Average number of transactions per user that made a purchase in July 2017
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/10bb79a9-1cd5-424e-91a7-849706efed11" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/468afbd7-1e44-4bd0-92ad-b7ca931542ae" />

> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.


### Query 06: Average amount of money spent per session. Only include purchaser data in July 2017
* SQL code
  
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/bd907173-5e01-4c82-bcf0-41ac5b5c3097" />

* Query results
* 
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/bfe6061e-0b13-47c7-80b9-6fa999fd1c4a" />


> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.


### Query 07: Other products purchased by customers who purchased product "YouTube Men's Vintage Henley" in July 2017. Output should show product name and the quantity was ordered.
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/932ac116-9d6b-4827-8984-635db2ecd81d" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/48c55a8b-91d3-44fd-91da-16c970947ea7" />


> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.


### Query 08: Calculate cohort map from pageview to addtocart to purchase in last 3 month.
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/43362203-646f-45a3-9b3f-c7da8b4bffb7" />
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/1d7bf9a9-1cdd-42ab-ab63-56f864180316" />


* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/d76650dc-1115-4f95-ae8b-86400e486dec" />

> ✔️ **Insight**:
> 
> Useful information that users should know, even when skimming content.

---
## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights and findings above, we would recommend the Senior Leaders to consider the following:  

📌 Key Takeaways:  
✔️ Recommendation 1:  
✔️ Recommendation 2:  
✔️ Recommendation 3: 

## V. Conclusion
By exploring the eCommerce dataset, I have gained valuable information about:
* **Overall Business Performance:** Management seeks to gain clarity on key performance indicators (KPIs), such as revenue, transaction volume, and traffic, to evaluate the company's overall health.
* **Sales and Marketing Effectiveness**: They aim to analyze the performance of different marketing channels, understand which traffic sources yield quality customers, and pinpoint areas for optimization in sales and marketing processes.

* **Improving Conversion Rates:** Beyond simply seeing if customers make purchases, they are eager to discover ways to improve user experience and increase the conversion rate from visitors to buyers.

* **User Experience Insights:** Understanding customer behavior, including differences between purchasers and non-purchasers, and tracking the journey from product view to purchase are critical for creating targeted marketing campaigns and enhancing the shopping experience.

* **Growth Strategies:** With these analyses, management can develop or adjust overall business strategies to support sustainable growth and enhance customer satisfaction.

