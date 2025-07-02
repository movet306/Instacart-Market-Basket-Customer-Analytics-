# 🛒 Instacart Market Basket & Customer Analytics  
*An End-to-End SQL & Python Case Study*  

---

## 1. Project Introduction 🎯

This repository delivers a complete analytics case study on Instacart’s e-commerce order data, covering product, customer, and behavioral analytics from end to end.  
**All data cleaning steps are fully documented in the included Jupyter notebook, so you can follow every stage of the data preparation process.**

> **Project conducted, analyzed, and documented by [Mert Ovet](https://linkedin.com/in/mertovet)**
>
> All data cleaning, feature engineering, segmentation logic, SQL metrics, business questions, and analytic methodology were designed and implemented by myself, ensuring full control over every parameter, analytical decision, and project milestone.
---

## 2. Dataset & Data Pipeline

- **Source:** [Instacart Market Basket Analysis | Kaggle](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis?resource=download)  
- **Raw Data:** ~3 million orders, 200K+ users, 50K+ products, 20 departments, 130 aisles
- **Files:** `orders.csv`, `order_products__prior.csv`, `order_products__train.csv`, `products.csv`, `departments.csv`, `aisles.csv`
- **Data Cleaning:**  
  - See all cleaning stages in [`Instacart Market Basket Data Cleaning.ipynb`](./Instacart%20Market%20Basket%20Data%20Cleaning%20(1).ipynb)
  - Inspected and cleaned missing values, anomalies, datatypes, and duplicates
  - Exported cleaned tables as CSV for SQL analytics

---

## 3. Tools & Technologies 🛠️

- **Python (Jupyter Notebook):**  
  - Data exploration & cleaning  
  - Data cleaning notebook: [`Instacart Market Basket Data Cleaning.ipynb`](./Instacart%20Market%20Basket%20Data%20Cleaning%20(1).ipynb)
- **SQL Server Management Studio (SSMS):**  
  - Data loading & advanced SQL analysis
- **Visualization:**  
  - SQL output screenshots

---

## 4. Data Preparation Workflow 📦

1. **Data Cleaning in Jupyter Notebook**
   - All data quality checks, filtering, and exporting are detailed step-by-step in the notebook
   - [Open the notebook here](./Instacart%20Market%20Basket%20Data%20Cleaning%20(1).ipynb) to follow each cleaning stage

2. **Database Loading in SQL**
   - Created database & loaded cleaned CSVs into SSMS
   - Checked relationships and validated schema
  
## 5. Analysis Workflow 🧭

The following sections mirror the analytic flow from raw data to business insight:

1. **Top Products Sold**  
2. **Department & Aisle Performance**  
3. **Order Volume Patterns (Day / Hour)**  
4. **Product Reorder Rate**  
5. **Customer Frequency Segmentation**  
6. **Basket Size & CLV Proxy**  
7. **Product Affinity Analysis (Pairs/Trios)**  
8. **Churn Risk Analysis**  
9. **Cohort Retention Analysis**

Each section includes:
- Business question  
- SQL screenshot & sample output  
- Insight & recommendation

  ## 6.Top Products Sold
**Business Question:** Which products sell most frequently?
![image](https://github.com/user-attachments/assets/e82076e9-0b67-4a78-b1c0-6fa63296e0a0) ![image](https://github.com/user-attachments/assets/66dd566d-d865-4d8e-b948-125005658777)

In this analysis, I identified the top 10 best-selling products by joining the orders data with product details and counting how many times each product appeared in customer carts. The results show that bananas, both regular and organic, dominate sales, followed closely by other fresh fruits like strawberries and avocados. Organic products are especially popular among shoppers, making up most of the top sellers. This pattern highlights a strong customer preference for fresh and organic produce, suggesting these categories are key drivers of revenue and should be prioritized in inventory and marketing strategies.

## 7.Category/Department Analysis
**Business Question:** Which departments and aisles generate the highest sales volume? Are there any standout categories that outperform the rest?

![image](https://github.com/user-attachments/assets/74609144-00ad-46f2-b946-9fa0da244cb7) ![image](https://github.com/user-attachments/assets/203da987-c7a5-4416-8049-4065fd2363ea)

Looking at the department sales breakdown, it's clear that "dairy eggs" is the leading category by a wide margin, with nearly twice as many sales as the next department, "snacks." Other high-performing categories include "beverages," "frozen," and "pantry," all showing strong consumer demand. Meanwhile, departments like "alcohol," "pets," "other," and especially "bulk" make up only a small fraction of total sales, suggesting either a lower product variety or less frequent purchases in those areas. Overall, the data reflects typical grocery shopping patterns, with core staples like dairy, snacks, and beverages dominating the basket.

## 8.  Best-Selling Aisles: Sales Distribution by Aisle
**Business Question:** Which aisles drive the most sales across the entire store, and how is customer demand distributed among different product aisles?
**Business Rationale:** Understanding sales performance at the aisle level helps uncover shopping patterns that may not be visible at the department level. This insight supports more targeted product placement, merchandising decisions, and tailored marketing campaigns, ultimately driving revenue growth.

![image](https://github.com/user-attachments/assets/1b7dc24d-c8f6-470f-b64f-f4f085bbaa28)

![image](https://github.com/user-attachments/assets/6f911724-0be2-40fa-a525-3517c8f6062f)

When we break down sales by aisle, it’s clear that customer demand is highly concentrated in certain categories. Fresh fruits and fresh vegetables dominate the top spots, with 144,263 and 137,171 total sales respectively—far outpacing other aisles. This reinforces the importance of fresh produce as a core traffic driver in grocery retail.
Beyond produce, packaged vegetables & fruits, yogurt, and packaged cheese also show strong performance, reflecting the popularity of both fresh and convenient ready-to-eat options. Beverage aisles like water seltzer and sparkling water, as well as staples like milk and bread, also rank among the top categories.
Overall, these insights highlight that successful assortment strategies should prioritize high-velocity aisles—particularly fresh foods and everyday essentials—while also identifying potential growth opportunities in underperforming segments. Retailers can use this level of analysis to optimize in-store layouts, promotional planning, and inventory decisions based on real customer demand.

## 9. Weekly Order Patterns – Order Volume by Day of Week
**Business Question:** Which days of the week see the highest order activity? Are there notable weekly patterns that can help guide staffing and promotional planning?
![image](https://github.com/user-attachments/assets/72cdf226-efae-431b-8125-02bc7a8ab2f5)

![image](https://github.com/user-attachments/assets/efc772bf-4e6e-4256-9a96-88c9618039db)

Order activity is clearly highest on days 0 and 1 (typically Sunday and Monday, depending on dataset encoding), which together account for nearly 35% of all orders. The rest of the week sees a gradual decrease, with the lowest activity on days 3 and 4. This weekly pattern indicates strong consumer preference for weekend grocery shopping, aligning with common retail trends. Instacart can use these insights to optimize staffing, inventory, and marketing efforts to maximize efficiency and customer satisfaction during peak days.

## 10. Order Volume by Hour of Day
**Business Question:** What times of day are Instacart customers most active? When does order volume peak, and how might this inform operational or marketing decisions?
![image](https://github.com/user-attachments/assets/1e2d90cb-d070-4cac-a52a-36f25cc1c935)

![image](https://github.com/user-attachments/assets/9af276e6-8d78-461c-8178-5c188798b848)

Looking at the data, we see that customer activity starts very low during the night—almost nobody is shopping on Instacart between midnight and 6 a.m. Starting at 7 a.m., order volume picks up rapidly and then jumps dramatically throughout the morning. The busiest times are between 9 a.m. and 4 p.m., with the absolute peak order volume occurring from 10 a.m. to 3 p.m.—each hour in this window consistently makes up over 8% of total daily orders. After 5 p.m., activity drops off steadily, with very few orders placed in the late evening and overnight. This insight tells Instacart when to focus their delivery resources, schedule staff, and launch time-sensitive promotions for maximum impact.

## 11. Repeat Purchase Rate (Reorder Rate) by Product
**Business Question:** Which products have the highest repeat purchase rates? What does this reveal about customer loyalty and product stickiness on Instacart?
![image](https://github.com/user-attachments/assets/0f484238-ef9e-4f8d-b8ad-ef7e34897827)

![image](https://github.com/user-attachments/assets/c686b466-9a78-4235-8f01-13aec29e4487)

The query identifies products with the highest proportion of repeat purchases. We calculate the reorder rate by dividing the number of times a product was reordered by the total number of orders for that product. Only products with more than 100 orders are considered to ensure statistical significance. The results show that “Organic Low Fat Milk” and “Banana” are among the most frequently repurchased items, indicating these products are customer favorites and essential staples in shopping baskets.

Looking at the results, we see that products like Organic Low Fat Milk and Bananas are not only popular in terms of order volume but also have a very high reorder rate, above 88%. This means customers are consistently coming back for these items, highlighting their importance as core products in the store’s offering and reflecting strong brand loyalty or habitual purchasing behavior.

## 12. Customer Segmentation: Defining Meaningful Customer Groups Based on Order Frequency
**Business Question:** How can we segment Instacart customers into meaningful groups based on their order frequency to better understand customer behavior, identify loyal users, and tailor marketing strategies?

**Approach & Rationale:** Instead of using arbitrary thresholds, I explored the actual order distribution across all users. By analyzing the frequency of orders per customer, I aimed to identify “natural clusters” and anchor points such as the median and mean order counts. This ensures our segmentation reflects the business reality and not just subjective assumptions.
**Methodology:** I first generated a frequency table showing how many users placed each possible number of orders. Then, I calculated the average (mean) and median number of orders per customer to objectively define what constitutes “occasional” and “loyal” behavior. Segment boundaries were then set using a combination of these statistics and visual inspection of the order frequency distribution.

![image](https://github.com/user-attachments/assets/39eb7e7a-ece5-46c6-913a-dd3e41758a5d)

![image](https://github.com/user-attachments/assets/ea57b899-f9fe-4857-a92b-6da94d8c1d18)

![image](https://github.com/user-attachments/assets/cf73f839-f7f9-40e1-b2ea-722d11503576)

![image](https://github.com/user-attachments/assets/4e574745-414f-41d7-8739-5ad20ed17353)

**Segment Definition:** Based on my analysis, I defined the segments as follows:
**One-Time Buyer:** 1 order
**Occasional Buyer:** 2 to 9 orders
**Regular Buyer:** 10 to 16 orders (between median and mean)
**Loyal Customer:** 17 or more orders
![image](https://github.com/user-attachments/assets/58a87779-2b09-408a-aeb8-f3f246147cc1)

![image](https://github.com/user-attachments/assets/5001dd90-3128-4fe2-a556-8c439d5f0918)

Looking at the segmentation results, we see that the Occasional Buyer segment makes up the largest group, with 95,481 users. This indicates that a significant portion of Instacart’s customer base shops infrequently, possibly making purchases only when needed or during special occasions.

The Loyal Customer segment, with 65,296 users, represents a highly valuable cohort for the business. These customers consistently return and are likely to contribute a substantial share of total sales, making them key targets for retention and loyalty programs.

Finally, the Regular Buyer group, at 45,432 users, sits between the other two segments. They shop more than occasional buyers but haven’t reached the loyalty threshold. This group presents an opportunity: with the right incentives or personalized offers, some of these regular buyers could be nurtured into loyal customers, further boosting customer lifetime value.

Overall, this segmentation provides a clear foundation for differentiated marketing strategies: engaging occasional buyers, nurturing regular buyers, and rewarding loyal customers.
 This segmentation is crucial for driving targeted retention campaigns: efforts to convert Occasional Buyers into Loyal Customers can directly impact long-term revenue and customer lifetime value (CLV). Increasing loyalty should be a top strategic focus.

## 12. Average Basket Size & Value by Customer Segment ##
**Business Question:** How does the average basket size (number of products per order) differ between Loyal Customers and Occasional Buyers?
**Why this matters:** Understanding basket size by segment helps Instacart target up/cross-sell efforts, optimize promotions, and measure the effectiveness of loyalty programs. Employers love to see segmentation used for actionable KPIs.

![image](https://github.com/user-attachments/assets/a4e6cc82-ff96-49b6-ac14-d1227491e6f0)

![image](https://github.com/user-attachments/assets/2cd71283-4308-4d61-8c4a-8b05838b6b27)

The analysis shows that Loyal Customers have the highest average basket size, purchasing 11 items per order, compared to 10 items per order for both Regular and Occasional Buyers. This seemingly small difference is actually significant at scale, as it suggests that loyal customers not only shop more frequently, but also tend to buy more per transaction.
This insight highlights the value of nurturing loyalty: as customers become more engaged with Instacart, their overall contribution to revenue increases both through higher frequency and larger basket sizes. For marketing and business strategy, it underscores the importance of targeted campaigns and loyalty programs designed to both retain and further grow the value of this segment.
For Regular and Occasional Buyers, the similar basket sizes suggest that frequency—not basket size—is the main differentiator. To drive incremental revenue from these groups, the focus should be on increasing purchase frequency rather than simply encouraging bigger baskets.

## 13. Customer Lifetime Value (CLV) Proxy by Segment
**Business Question:** How does estimated customer value differ by segment? Can we use average basket size and frequency to estimate which segments are most valuable to the business?
**Approach:**  Since we do not have actual monetary values, I will use a proxy for CLV:
**CLV ≈ Average Basket Size × Average Orders per User (by segment)**

![image](https://github.com/user-attachments/assets/d7fbcbc0-29b2-4094-9295-5d5ce21fde03)

![image](https://github.com/user-attachments/assets/c2334321-fb18-4dd0-a2be-5c48dc6e7c60)

![image](https://github.com/user-attachments/assets/1d6efac3-fa8f-4fe8-84d6-1fbec619c834)

Analyzing the average customer behaviors across segments reveals a sharp difference in the potential value each segment brings to Instacart.
Occasional Buyers place just over 6 orders on average, with a typical basket size of 10 items, resulting in an estimated Proxy CLV of about 61. Regular Buyers roughly double that impact, making over 12 purchases with a slightly larger basket size, and achieving a Proxy CLV of nearly 134. The real difference emerges with Loyal Customers—these shoppers average nearly 35 orders per user and consistently build larger baskets, driving a Proxy CLV of approximately 389.
This tiered pattern illustrates the exponential value of customer loyalty: as customers move from “Occasional” to “Regular” and ultimately “Loyal,” their total contribution increases more than sixfold. The insight here is clear—retention strategies and loyalty programs that successfully convert Occasional or Regular Buyers into Loyal Customers will generate a disproportionate lift in long-term value for Instacart.

**Key Takeaway:**
 Loyalty is the single biggest driver of customer value in the Instacart ecosystem. While Occasional Buyers make up the largest group, investing in customer experience and retention to grow the “Loyal Customer” segment will maximize revenue and long-term growth.

## 13. Product Affinity / Market Basket Analysis
**Business Question:** Which pairs of products are most frequently purchased together, and what cross-sell or bundling opportunities can we identify from these affinities?
Here I’ll use a self-join on the order-product detail table to find product pairs that appear in the same basket.
![image](https://github.com/user-attachments/assets/a7b69533-f0b5-46ec-b002-abaf97a2f483)

![image](https://github.com/user-attachments/assets/d7af994c-763b-4601-94de-983aa1e061d4)

This analysis clearly shows Bag of Organic Bananas is at the heart of most top product pairings, usually with other fresh, organic produce like strawberries, avocados, and spinach. For Instacart, this means bananas aren’t just a staple, but a cross-sell trigger. If a shopper adds bananas, recommend these common pairings in real time to increase basket size. There’s also room to experiment with produce bundles or targeted offers (“Frequently Bought Together”) to further boost order value. Overall, these patterns reveal where Instacart can personalize the shopping journey and drive growth—by leveraging natural product affinities right at the moment customers are ready to buy.

## 14. Churn Analysis
**Business Question:** How can we identify churned customers—those at risk of not returning—based on their order patterns, even when exact order dates are not available?
### 1.Customer Segmentation(CTE):
![image](https://github.com/user-attachments/assets/9022f407-9a25-484b-bc68-385b57d448d9)

In this step, I used a Common Table Expression (CTE) named user_segments to assign each user to a customer segment based on their total number of orders. This CTE enables us to reference these segments in subsequent queries for further analysis, such as churn calculation.

### 2. Calculate Cumulative Days Since First Order (CTE)
![image](https://github.com/user-attachments/assets/d766ef4a-cd70-4b43-b4ce-d790780fbadc)

Using a window function, I calculated the running total of days for each user. This shows exactly how much time has passed at every purchase event.

### 3. Identify Each User’s Last Order Day (CTE)
![image](https://github.com/user-attachments/assets/5b5eba63-4624-452a-97b1-aea19419ae54)

This step pinpoints the ‘last activity’ date for each user, which is essential for measuring churn risk.

### 4. Define the Latest Day in the Dataset (CTE)
![image](https://github.com/user-attachments/assets/a5224456-5ede-4cbe-8103-53d2b0fe7648)

### 5. Assign Churn Risk Segment to Each User (CTE)
![image](https://github.com/user-attachments/assets/85712cf8-17ae-4113-8367-c551455638ff)
Each user is categorized by churn risk based on how long it has been since their last order. This allows us to prioritize outreach and retention actions.

### 6. Aggregate Results by Segment and Churn Risk
![image](https://github.com/user-attachments/assets/2cc58f0e-86db-470d-8e98-e6a7636fad49)

This result shows, for each segment, how many users are “Active,” “Low Risk,” “Medium Risk,” or “High Risk,” and what percentage of the segment they represent.

![image](https://github.com/user-attachments/assets/9ed5010b-87d8-430a-8311-1303cff9f916)

The data makes it clear: Instacart is facing a significant retention issue, with even its Loyal Customer segment showing nearly 80% at high churn risk and only a small minority still active. The inactivity among Regular and Occasional Buyers is even more dramatic, pointing to a widespread engagement challenge.

To address this, Instacart should immediately prioritize retention, starting with high-value loyal users. Personalized reactivation campaigns—offering exclusive incentives or loyalty perks—should be launched without delay. At the same time, the company needs to dig deeper to understand what’s driving disengagement, reviewing both customer feedback and recent operational changes. Ongoing churn risk monitoring is essential, allowing Instacart to quickly identify and respond to early warning signs before they turn into lost revenue. In today’s environment, proactive and targeted retention is critical for protecting long-term growth.

## 14. Market Basket (Cross-Sell) Analysis
**Business Question:** Beyond pairs, what are the strongest multi-product combinations in baskets, and how can we leverage these insights for cross-selling?
**Rationale:** Uncovering frequent combinations of 3 or more products in a single order helps identify bundling opportunities, effective cross-sell recommendations, and in-store/online merchandising strategies. Knowing which product trios or quartets appear together most often can reveal natural “bundles” that customers already buy.

![image](https://github.com/user-attachments/assets/062522a3-76ec-41e3-b887-37872d94aa13)

To move beyond simple product pairs and unlock deeper cross-selling opportunities, I identified the top combinations of three products most frequently purchased together in the same basket.

Because analyzing all orders in a large dataset would be extremely slow and computationally expensive, I focused on a 10,000-order sample.

I used a triple self-join on the order-product detail table, then grouped and ranked product trios by their frequency of occurrence.

![image](https://github.com/user-attachments/assets/1d79c7f6-2562-4619-83d0-e1581d42fd1d)

The results show a strong pattern: fresh produce and organic items dominate the most frequent product trios.

“Bag of Organic Bananas” appears repeatedly, often paired with items like “Organic Strawberries,” “Organic Baby Spinach,” and “Organic Hass Avocado.”

This suggests that customers who prioritize organic products have clear shopping habits, frequently purchasing these combinations in a single trip.
For the business, these insights are powerful. By bundling these top product trios, Instacart can design attractive cross-sell promotions—such as “Fresh Organic Starter Packs”—or feature these sets in personalized recommendations.

Additionally, highlighting these combinations on the product detail pages can drive higher basket sizes and improve overall customer experience, tapping into natural purchase behaviors already present in the data.

## 15. Cohort Retention Analysis
**Business Question:** What does the cohort retention curve reveal about when Instacart customers are most likely to churn, and how can these insights drive more effective retention strategies?
### Step 1: Assign Users to a Cohort (First Purchase Month)
**Goal:**
 Group each user into a cohort based on the month of their first order.
 Because we don't have a real order_date, so I reconstruct a simulated timeline using days_since_prior_order table.

![image](https://github.com/user-attachments/assets/c27e129d-487d-434a-8d0e-d299afde2ca5)

Here, each user is assigned to a cohort corresponding to the period of their first-ever order.
The variable cohort_day serves as a normalized starting point for retention calculations.

### Step 2: Track Each User’s Orders in Subsequent Months
**Goal:**
 Track how many users from each cohort return to place additional orders in each month after their cohort start.
 
 ![image](https://github.com/user-attachments/assets/bc8a01f4-219d-4033-8574-25e78b28d20d)

 I calculated the number of days and months since each user's cohort start, aligning every user’s timeline to a common scale for monthly retention analysis

 ### Step 3: Calculate the Size of Each Cohort
**Goal:**
 Determine the initial size of each cohort for use as the denominator in retention calculations.

 ![image](https://github.com/user-attachments/assets/bf0a71e0-604b-4a59-a320-ab71c5aec8b9)

 This step identifies how many unique users started in each cohort period, providing a baseline for all subsequent retention metrics.

### Step 4. Compute Cohort-by-Month Retention Percentages
**Goal:**
 For every cohort and each subsequent month, calculate the retention rate as a percentage of the original cohort.
 ![image](https://github.com/user-attachments/assets/1787e8e8-2b2b-4709-a7a5-755e3a561697)

At this stage, we know for each cohort and each month how many users are still active and what percentage they represent of their original group.

### Step 5. Average Retention Rate Across All Cohorts
**Goal:**
 Summarize the overall customer retention curve by averaging the retention percentages of all cohorts for each month.
 
 ![image](https://github.com/user-attachments/assets/7591e9dc-e4d6-40ae-a975-342c34822aa7)

 The final output is a single, high-level retention curve that shows the typical customer lifecycle on Instacart. This makes it easy to identify when most users drop off and how many remain loyal over time.

 ![image](https://github.com/user-attachments/assets/0c405052-2332-4c94-a666-3ea5ce549fee)

The resulting retention analysis revealed that, as is common in e-commerce, user engagement drops sharply after the initial transaction: only about 14% to 23% of customers make a repeat purchase in the months following their first order. However, the retention curve stabilizes relatively quickly, with around 15–20% of users remaining active for up to three years, which demonstrates the presence of a loyal customer segment.
This insight highlights two critical opportunities for Instacart’s growth strategy. First, it is essential to focus on early engagement—by investing in onboarding, reactivation campaigns, and targeted incentives during the first months, Instacart can increase the proportion of new users who return for additional orders. Second, understanding and learning from the behaviors of long-term loyal customers can help shape future retention and loyalty initiatives, ensuring that successful tactics are scaled across the broader user base.
By continuously monitoring these retention metrics and experimenting with early lifecycle engagement strategies, Instacart can both reduce churn and expand its core group of repeat customers, ultimately driving higher lifetime value and sustainable growth.

## 16. Key Insights

The analytics reveal that Instacart’s business is anchored by a narrow set of high-velocity products and recurring customer behaviors:

- **Fresh produce and organic products are Instacart’s main growth engine.** Bananas (both organic and regular) alone make up the top-selling items, consistently appearing in the highest volume orders and forming the centerpiece of most product affinity pairs and trios.

- **A small set of departments and aisles drives the majority of orders.** Over half of all purchases come from just three categories—“Dairy & Eggs”, “Snacks”, and “Fresh Fruits & Vegetables”—while aisles like “Fresh Fruits” and “Fresh Vegetables” record sales volumes far above any others.

- **Order activity is highly patterned:** The majority of weekly sales happen on Sundays and Mondays, with order volume peaking between 10 AM and 3 PM. These recurring peaks reveal predictable shopping rhythms, providing a playbook for optimizing inventory, fulfillment, and campaign timing.

- **Customer value is defined by frequency, not just basket size.** While average basket size only increases marginally by segment, Loyal Customers place nearly 35 orders per user—over six times more than Occasional Buyers. As a result, Loyal Customers’ proxy CLV (~389) dwarfs that of Occasional Buyers (~61).

- **Churn risk is a core business challenge.** Nearly 80% of even the most loyal customers are flagged as high risk for churn, and engagement across all segments falls sharply after the first order. Yet, a core of loyal users maintains steady retention up to three years, confirming that early drop-off and ongoing disengagement are distinct issues.

- **Market basket analysis shows clear, actionable affinities:** The most frequent product pairings and trios overwhelmingly involve organic bananas, strawberries, spinach, and avocados—confirming that health-focused customers repeatedly purchase these items together.

- **Cohort analysis quantifies a sharp drop-off after first purchase** (retention plunges to 14–23% within the first few months), but also reveals a stable loyal segment: around 15–20% of users remain active up to three years after onboarding.

---

## 17. Strategic Recommendations

Each action item is directly grounded in the findings above, ensuring Instacart’s strategy is data-driven and outcome-focused:

1. **Double Down on Fresh & Organic Staples:**  
   The outsized dominance of bananas, berries, and organic vegetables in both volume and repeat purchase suggests these categories should remain at the core of inventory, digital promotions, and homepage merchandising. For example, organic bananas feature in nearly every top affinity set—making them the logical anchor for marketing and bundling.

2. **Tailor Campaigns to Shopping Rhythms:**  
   With over a third of weekly orders placed on Sundays and Mondays, and activity peaking between 10 AM and 3 PM, align fulfillment staffing, delivery slots, and push campaigns to match these high-traffic periods. Time-limited offers on key days can further amplify sales.

3. **Prioritize Retention—Especially Right After First Order:**  
   Since most users churn shortly after their first purchase, invest in onboarding journeys, reactivation messages, and time-sensitive discounts during a customer’s first month. For example, push targeted offers to new customers within days of their initial order to drive repeat purchase while engagement is still high.

4. **Grow the Loyal Segment—Not Just Basket Size:**  
   Proxy CLV analysis confirms that increasing purchase frequency—moving users from Occasional to Regular, and Regular to Loyal—delivers the biggest lift in value. Personalized email sequences and loyalty rewards (such as “every 5th order is free delivery”) should focus on nudging users up the loyalty curve.

5. **Exploit Cross-Sell with Specific, Data-Backed Bundles:**  
   Bundle “Frequently Bought Together” combos directly from the most common affinity sets: for example, “Organic Bananas + Strawberries + Baby Spinach” packs, which repeatedly show up in the top three-product baskets. In-app suggestions should be based on real affinity data, not guesswork.

6. **Target Churn Risk with Proactive, Segment-Specific Outreach:**  
   Monitor customers whose recency and frequency metrics indicate disengagement—especially among previously loyal users. Trigger reactivation offers, personalized messaging, or surveys when “days since last order” exceeds risk thresholds identified in the churn analysis.

7. **Test and Expand Underperforming Categories:**  
   Since a handful of departments and aisles underperform, pilot targeted campaigns (e.g., “Pantry Essentials Week”) or experiment with product assortment and pricing in these segments to drive incremental volume.

By executing these tailored, evidence-based strategies, Instacart can systematically increase customer value, retention, and market share—while building a defensible, data-driven edge in the competitive grocery delivery space.

---
---

## Project Owner

**Mert Ovet**  
[LinkedIn: linkedin.com/in/mertovet](https://linkedin.com/in/mertovet)

For collaboration, feedback, or business inquiries, please connect via LinkedIn.

---







 














