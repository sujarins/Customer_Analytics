# Product Recommendation 
### Objective : to uncover associations between items

## 1.Prepare Data
- Loading the collected data, which is collect during class by google forms
- convert letter to numerical data 
![convet collected data](https://user-images.githubusercontent.com/56682174/147476812-2f29dd65-f0cf-4f10-b0f6-79bc4f166a03.png)
 

## 2.Find frequent itemsets
### 2.1) By Apriori Algorithm
Setting min_threshold=1, Lift >= 1.1 and confidence >= 0.7


### 4.2) Interpret characteristic for each customer group
The graph shows the customer behaviour in each group. X-axis is total days of the relationship, Y-axis is recency and the size of bubble is totalSpend.
   - Class0 : Low Value  - High Recency - Short Relationship because their basket size are very small
   - Class1 : Medium Value - Low Recency - Medium Relationship
   - Class2 : Low Value - Medium Recency - Medium  Relationship
   - Class3 : High Value -Low Recency- Long Relationship customers because they shop for higher spend, are long time for membership and have low recency values (meaning they have been shopping recently)

![customer behaviour](https://user-images.githubusercontent.com/56682174/147462702-e311aae0-c4c4-4809-b820-229ff0a9441a.jpeg)


### 4.3) Action Plan for each customer group
**Class0 called "SEED"** : Low Value  - High Recency - Short Relationship
  - Run analysis on the cost vs revenue of offering promotions
  - Churn prediction (Lead scoring)

**Class2 called "SPROUT"** : Low Value - Medium Recency - Medium  Relationship
  - Daily promotion special 
  - Discount speacial products, BOGO

**Class1 called "YOUNG"** : Medium Value - Low Recency - Medium Relationshipp
  - Up-selling and Cross-selling, for example:
      - Customer will receive Cash Coupon or Discount/Cashback x% when purchasing the participating products or when purchasing at x,xxx THB
      - Customer will receive Cash Coupon when Top-Up Pre-Paid gift card at xx,xxx THB
      - Customer will receive free sample or product when purchasing more the same catagory items such as free wooden storage when purchasing 4 twining tea boxs

**Class3 called "RIPE"** : High Value -Low Recency- Long Relationship
  - Send holiday gift and birthday gift ex. new product samples, gift card, discount coupon
  - Offer additional privilege Cash Coupon or Discount/Cashback x% more than the other groups ex. class1 got 3% but class3 got 5% <br> <br>


![customer segmentation](https://user-images.githubusercontent.com/56682174/147474917-fa5b2002-4362-49e8-83d2-9b217fb6139b.png)
