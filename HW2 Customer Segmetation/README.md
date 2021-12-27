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
  7. total day : total days of the relationship
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
**Hence, I decied to drop sc model.**

![sc model](https://user-images.githubusercontent.com/56682174/147456414-8e7dd827-b4c4-41a8-8638-084d8f62c4d3.png)


&nbsp;&nbsp;&nbsp;&nbsp; **1) K-Mean Model** : K-mean can segments customer into 4 gorups

![K-mean](https://user-images.githubusercontent.com/56682174/147458048-76c52afa-70fa-48c3-8a46-a34f1ca3ac79.png)


## 4. Interpret result
