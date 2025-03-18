# 📊 [SQL] E-Commerce Sale Performance Analysis

Author: Xuan Luong

Date: 2024  

Tools Used: SQL/Google BigQuery

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description](#-dataset-description)
3. [⚒ Main Process](#-main-process)  
4. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview

### Objective:
Conducted queries on Google Analytics public dataset using the BigQuery platform to analyze user behavior, providing valuable insights that enhance business strategies.

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
## 📂 Dataset Description

### 📌 Data Source
The dataset is based on the Google Analytics public dataset and contains data from an eCommerce website.
Project on Google Cloud Platform, the project ID is "bigquery-public-data.google_analytics_sample.ga_sessions"

[Table Schema](https://support.google.com/analytics/answer/3437719?hl=en)


---
## ⚒ Main Process

As mentioned above, I will write 08 queries in Bigquery to answer those questions

### Query 01: Calculate total visit, pageview, transaction for January, February and March 2017 order by month
* SQL code
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/8e6e94cb-a8f3-4c70-9097-0d7e889884ac" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/52994a7e-ff41-4e7c-88b7-bd3955561eaa" />


> ✔️ **Insight**:
> The data indicates positive growth in traffic and transactional performance
>
> - Increase in Visits: There is an upward trend in visits from January (64.7K) to March (69.9K), showing a growing interest or traffic to the eCommerce site over the three months.
>
> - High Pageviews: The pageviews significantly exceed visits in all months, indicating that users are engaging with multiple pages per visit. For example, in February, there were 233.4K pageviews, suggesting users may be browsing multiple products.
>
> - However, The conversion rate (transactions to visits) is relatively low, indicating a potential area for improvement. 
For instance, in March, there were 993 transactions from 69.9K visits, which equates to about 1.4% conversion.
=> There may be barriers preventing users from completing purchases.
>



### Query 02: Bounce rate per traffic source in July 2017
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/52b69fc2-b52f-4fcd-bb2a-bc2e60e08da1" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/ad9fa54d-7b4e-4011-abba-7d7dec8bad33" />


> ✔️ **Insight**:
> 
>**Traffic Sources:**
> - Google leads with 38,400 visits, indicating strong SEO or ad effectiveness.
> - Direct traffic is also considerable at 19,891 visits, reflecting brand loyalty.
> 
>**Bounce Rates**
> - Sources like m.facebook.com and youtube.com have relatively high bounce rates (64.28% and 66.73%, respectively), indicating potential issues with user engagement or mismatch in expectations.
> ➡️ Strategies like improved landing pages or targeted messaging could reduce bounce rates.
> - In contrast, the lowest bounce rate occurs with dfa (41.06%), suggesting that users from this source are more engaged.
> 
> **Minor Traffic Sources with low bounce rate:**
> - Sources such as dfa (124 visits), sites.google.com (230 visits), and facebook.com (191 visits) bring in lower traffic.
> - However, understanding their engagement (bounce rate) can help evaluate their effectiveness.
>
> ⭐ These insights can help refine marketing strategies and improve site engagement.



### Query 3: Revenue by traffic source by week, by month in June 2017
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/d823b5f6-dd0f-48b8-8c65-2e449f140ff0" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/e8098c84-6de1-4329-97af-6d8a85ed0414" />


> ✔️ **Insight**:
>
> **Monthly Revenue**:  
>   - **Direct Traffic**: The highest revenue comes from the **direct** source across multiple weeks, with a total of approximately **97,333.62** in June.  
>   - **Google Traffic**: The revenue associated with **Google** is notably lower in comparison, peaking at **18,757.18** in June but varying across weeks.
>   - Revenue from **DFA (Digital Advertising)** appears limited at **9,217.17**, indicating potential opportunities or challenges in converting this traffic into revenue.  
>
>**Weekly Revenue**:  
>   - **Week 24** generated significant revenue for both **direct traffic** and **Google**, indicating effective engagement or promotional activities.  
>   - **Direct traffic** maintained strong performance throughout multiple weeks, suggesting stable interest or returning customers.    
>   - The consistency in **direct traffic** revenue across different weeks suggests an established customer base, which could be leveraged for further promotional strategies.  


### Query 04: Average number of pageviews by purchaser type (purchasers vs non-purchasers) in June, and July 2017.
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/8f2f2a0a-6a6a-40f1-8a8d-6b00fe95deff" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/a8524f45-1580-4cbd-a6aa-ce6f301dc7e0" />


> ✔️ **Insight**:
>
> The higher pageviews from non-purchasers suggest they are exploring various options but may not be converting into purchases.
> This could indicate a need to improve the purchasing experience or to understand barriers preventing conversion.



### Query 05:  Average number of transactions per user that purchased in July 2017
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/10bb79a9-1cd5-424e-91a7-849706efed11" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/468afbd7-1e44-4bd0-92ad-b7ca931542ae" />

> ✔️ **Insight**:
>
> - The average of over four transactions suggests a relatively high level of customer loyalty or repeated purchasing behavior among those users. It indicates that once users decide to purchase, they are likely to continue buying.
> - Businesses could leverage this insight to develop retention strategies, focusing on the factors that encourage repeat purchases, such as personalized marketing, loyalty programs, or targeted promotions.


### Query 06: Average amount of money spent per session. Only include purchaser data in July 2017
* SQL code
  
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/bd907173-5e01-4c82-bcf0-41ac5b5c3097" />

* Query results
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/bfe6061e-0b13-47c7-80b9-6fa999fd1c4a" />


> ✔️ **Insight**:
> The figure suggests that purchasers are not only visiting the site but also converting their visits into substantial monetary value. This level of spending can indicate effective pricing strategies and product offerings.
> 


### Query 07: Other products purchased by customers who purchased the product "YouTube Men's Vintage Henley" in July 2017. The output should show the product name and the quantity ordered
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/932ac116-9d6b-4827-8984-635db2ecd81d" />

* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/48c55a8b-91d3-44fd-91da-16c970947ea7" />


> ✔️ **Insight**:
> - The most purchased product alongside the "YouTube Men's Vintage Henley" is the Google Sunglasses, with a total quantity of 20 sold. This indicates strong interest in this item among purchasers.
> - A diverse range of products was purchased, including clothing items like Google Women's Vintage Hero Tee Black (7) and Google Women's Short Sleeve Hero Tee Red Heather (4), suggesting that customers are interested in apparel beyond just the initial purchase.
> - Customers buying the "YouTube Men's Vintage Henley" appear to prefer products related to clothing and accessories, indicating a fashion-oriented customer base. This knowledge can help tailor future marketing efforts.


### Query 08: Calculate cohort map from product view to "addtocart" to "purchase" in Jan, Feb, and March 2017. The output should be calculated in product level.
* SQL code

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/43362203-646f-45a3-9b3f-c7da8b4bffb7" />
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/1d7bf9a9-1cdd-42ab-ab63-56f864180316" />


* Query results

<img width="700" alt="Image" src="https://github.com/user-attachments/assets/d76650dc-1115-4f95-ae8b-86400e486dec" />

> ✔️ **Insight**:
> - The add-to-cart rate increased steadily from 28.47% in January to 37.29% in March, showing improved engagement or effectiveness of the add-to-cart prompts over time.
> - The purchase rate also increased from 8.31% to 12.64%, indicating growing conversion effectiveness across the months.
> - Higher add-to-cart rates correlate with higher purchase rates, particularly visible between January and March. This suggests that improvements made in the user experience for adding items to the cart are likely translating into higher overall sales.
> - February saw a slight decline in product views compared to January, but the conversion rates (add-to-cart and purchase) improved, suggesting that quality of traffic improved, or users were more motivated to buy.
> 
> ➡️ A successful strategy or marketing campaign may have contributed to the increases in engagement and conversions, particularly from January through March. Identifying these strategies could inform future campaigns.

---
## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights and findings above, I would recommend the Senior Leaders to consider the following:   

### 📌 Key Takeaways:  

✔️ 1. **Revenue Performance**:  
   - **Direct traffic** consistently drove the highest revenue, highlighting the importance of retaining this customer base.  
   - There is an opportunity to enhance revenue from **Google traffic**, which shows lower revenue figures.  

✔️ 2. **Customer Engagement**:  
   - Both **purchasers and non-purchasers** exhibit varying engagement levels, with non-purchasers browsing more pages on average. This indicates potential barriers to conversion that could be addressed.  
   - **Purchase behavior** shows that customers who buy are likely to make multiple transactions, suggesting a solid foundation for loyalty programs and retention strategies.  

✔️ 3. **Product Insights**:  
   - Products viewed alongside popular items (e.g., "YouTube Men's Vintage Henley") reveal preferences that can be leveraged for cross-selling and marketing strategies.  
   - High-performing products can inform inventory management and promotional tactics.  

✔️ 4. **Cohort Analysis**:  
   - The **add-to-cart** and **purchase rates** improved from January to March 2017, demonstrating effective user engagement strategies and indicating strong growth in conversion rates.  
   - The correlation between increased add-to-cart rates and purchase rates points to a successful optimization of the shopping experience.  

✔️ 5. **Marketing Strategies**:  
   - Effective marketing strategies can capitalize on existing customer bases while also targeting non-purchasers through tailored campaigns to convert their engagement into purchases.  
   - The data suggests that promotional tactics or product visibility adjustments could boost sales significantly.  

### 🏆 Conclusion  

The analyses reveal a well-defined landscape of customer behavior and purchasing trends across different channels and products. The strong engagement from direct traffic and the increasing conversion rates from product views to purchases suggest that the organization has a solid customer base willing to spend. However, there are opportunities for growth among non-purchasers and in harnessing search traffic more effectively.  

To optimize future performance, the focus should be on enhancing the user experience for both returning and potential customers through targeted marketing strategies, improved product visibility, and promotion of high-demand products. A continuous evaluation of customer engagement metrics will be essential to adapt to changing consumer behavior and preferences, paving the way for sustainable growth and increased revenue.  

