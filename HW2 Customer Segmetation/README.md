# Customer Segmetation
### Objective : To segment customers into 4 groups

## 1.Load data
Loading the transaction data called "Supermarket Data.csv". It contains 950K rows and 22 columns.
  - rows identify each transaction
  - columns identify purchasing information ex. purchasing time, purchasing date, purchasing location, basket size, basket price, customer id

![loading_data](https://user-images.githubusercontent.com/56682174/147410930-98183b8d-e606-48e4-9f47-1502281e0ea1.png)


## 2.Prepare customer single view
In customer single view, I add several features whcich tend to relate with customer purchaing behaviour as following:
  1. cust_code : customer id
  2. totalSpend : total spending
  3. totalVisit : the number of visiting
  4. totalSKUs : the number of distinct items in basket
  5. LifeStage : customer age group
  6. TicketSize : average purchasing amount per visiting
  7. total_day : total days of the relationship
  8. recency : day since last purchasing
  9. Shop Weekday : purchasing weekday
  10. Shop Hour : purchasing time
  11. basketType : basket types ex. full shop, small shop, top up
  12. basketDOM : item types in basket ex. fresh, grocery,mixed

## 3. Cluster Customer
#### compare model performance
 as picture below, I selected sc and k-mean to cluster customer
![comparing](https://user-images.githubusercontent.com/56682174/147456132-c9d71177-26ba-4d24-afd0-b1dbb12f1ec6.png)

&nbsp;&nbsp;&nbsp;&nbsp; **1) SC Model** :  SC model segments customers into 4 groups, but the most customers are assigned into Cluster 0. <br>
**Hence, I decided to drop sc model.**

![sc model](https://user-images.githubusercontent.com/56682174/147456414-8e7dd827-b4c4-41a8-8638-084d8f62c4d3.png)


&nbsp;&nbsp;&nbsp;&nbsp; **2) K-Mean Model** : K-mean can segments customer into 4 gorups, and the number customers in each group are quite reasonable. <br>
**So, I decided to use K-mean model.**

![K-mean](https://user-images.githubusercontent.com/56682174/147458048-76c52afa-70fa-48c3-8a46-a34f1ca3ac79.png)

&nbsp;&nbsp;&nbsp;&nbsp; After using K-mean model to predict the customer clusters , I have to **add the predicted cluster (or label) for each customer into the last column of table.** (for finding feature importance in next step)<br>
***Tip! : don't forget to DROP uninvolved columns ex. customer id.***

![k-mean predict](https://user-images.githubusercontent.com/56682174/147460167-a0d4bc25-e3d0-4cf7-9467-54a303821d5e.png)


## 4. Interpret result
&nbsp;&nbsp;&nbsp;&nbsp; **1) Find feature Importance** 
- When each customer got label, **I did decision tree to see the key features for clustering.**
- The result of decision tree shows **3 features importance : recency, total_day, totalspend**

![decision tree](https://user-images.githubusercontent.com/56682174/147462060-97a2c9a7-66b6-4803-85dd-5d754e7e56b4.jpeg)

- I used **another libratry for checking feature imnportance.** The result also shows **3 features importance : recency, total_day, totalspend**

XXX  pic  XXXX

&nbsp;&nbsp;&nbsp;&nbsp; **2) Interpret customer group** 
- The graph shows the customer behaviour in each group. X-axis is total days of the relationship, Y-axis is recenvy and the size is totalSpend.
    - Class0 : Low Value  - High Recency - Short Relationship because their basket size are very small
    - Class1 : Medium Value - Low Recency - Medium Relationship
    - Class2 : Low Value - Medium Recency - Medium  Relationship
    - Class3 : High Value -Low Recency- Long Relationship customers because they shop for higher spend, are long time for membership and have low recency values (meaning they have been shopping recently)

![customer behaviour](https://user-images.githubusercontent.com/56682174/147462702-e311aae0-c4c4-4809-b820-229ff0a9441a.jpeg)

&nbsp;&nbsp;&nbsp;&nbsp; **3) Action for each customer group** 

**Class0 called "CASUAL"** : Low Value  - High Recency - Short Relationship
  - Run analysis on the cost vs revenue of offering promotions
  - Churn prediction (Lead scoring)

**Class1 called ""** : Medium Value - Low Recency - Medium Relationshipp
  - Up-selling and Cross-selling, for example:
      - Customer will receive Cash Coupon or discount x% when purchasing the participating products or when purchasing at x,xxx THB
      - Customer will receive Cash Coupon when top-up pre-paid gift card at xx,xxx THB
      - Customer will receive free sample or product when purchasing more the same catagory items such as free wooden storage when purchasing 4 twining tea boxs

**Class2 called ""** : Low Value - Medium Recency - Medium  Relationship
  - Daily promotion special 
  - Discount speacial products, BOGO

**Class3 called ""** : High Value -Low Recency- Long Relationship
  - Suggest Special new product
  - Send holiday gift ex. new product samples, gift card, discount coupon
