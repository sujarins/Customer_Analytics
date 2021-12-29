# Campaign Response Model
### Objective : To build the customer response predictive model. All conversions have a cost, so we have to select the right offer to the right customer segment. 


## 1.Load data
Loading 2 csv file as following:
  1) Retail_Data_Response.csv &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  2) Retail_Data_Transactions.csv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img width="200" alt="Data_Response" src="https://user-images.githubusercontent.com/56682174/147687471-c6234419-a054-4074-94f4-586af38d4ad8.png">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img width="320" alt="Data_Transactions" src="https://user-images.githubusercontent.com/56682174/147687482-4207fe36-98ac-4232-a566-19fc9bddec8b.png">

<br><br>

## 2.Prepare data
### 2.1) Create campaign response features : we created two datasets
  1. RFM dataset
<img width="400" alt="RFM dataset" src="https://user-images.githubusercontent.com/56682174/147689846-b33515d1-c5fa-459f-b24f-ffa284809e19.png">
  2. CLV dataset
<img width="500" alt="CLV dataset" src="https://user-images.githubusercontent.com/56682174/147689864-02d734bf-0fbf-4703-82f6-9ebf34ff1469.png">

   - recency : days since the last purchase
   - frequency : the number of purchase
   - total_spend : the total amount of purchase
   - AOU : the total days of relationship
   - ticket_size : the average amount of purchase

### 2.2) Check response rate and merge data
  - check reponse rate : data is imbalanced
 <img width="250" alt="response rate graph" src="https://user-images.githubusercontent.com/56682174/147689136-35529149-0dd5-45b9-b140-0eb56d499dec.png">

  - merge response into two datasets both RFM and CLV

<img width="380" alt="merge data RFM" src="https://user-images.githubusercontent.com/56682174/147690360-44ad7e52-047a-4beb-84ce-2c4efe24ddbe.png">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img width="510" alt="merge data CLV" src="https://user-images.githubusercontent.com/56682174/147690332-c84ffe9d-1d9d-4028-b58e-dc039f9d70cc.png">

<br><br>

## 3. Fix imbalanced 
### 3.1) Split train and test
  - set two dataset RFM and CLV : test_size=0.3 and random_state=0 
TIP! : don't forget to drop customer id from your X dataset

### 3.2) Fix imbalanced with SMOTE
TIP! : SMOTE (Synthetic Minority Over-sampling Technique) works by selecting examples that are close in the feature space, drawing a line between the examples in the feature space and drawing a new sample at a point along that line. (https://machinelearningmastery.com, Jason Brownlee , 2020)

<br><br>

## 4. Fit Model
### 4.1) Logistic Regression
  - LR : the result of RFM dataset
<img width="300" alt="AUC LR SMOTE RFM" src="https://user-images.githubusercontent.com/56682174/147703584-be2a3edd-4f01-4c78-99a2-6efdded26854.png">

  - LR : the result of CLV dataset
<img width="400" alt="AUC LR SMOTE CLV" src="https://user-images.githubusercontent.com/56682174/147703604-7fb22b26-1f15-444f-87f0-5a1003d21e24.png">

  - LR : Grid Serch
<img width="507" alt="Grid Serch LR" src="https://user-images.githubusercontent.com/56682174/147703737-2c686539-1864-4ad9-8808-4c96fa3babe1.png">


### 4.2) XGBoost
  - XG : the result of RFM dataset
<img width="400" alt="XG RFM" src="https://user-images.githubusercontent.com/56682174/147703874-3edf9588-736d-46b6-9a39-41be62483a4e.png">

  - XG : the result of CLV dataset
<img width="400" alt="XG CLV" src="https://user-images.githubusercontent.com/56682174/147703869-4a0349e2-0072-4551-9037-80dfc80e7967.png">

  - XG : Grid Serch
<img width="500" alt="Grid Search XG" src="https://user-images.githubusercontent.com/56682174/147703887-416d6ac7-eff2-41c9-92a4-db33d2a190d0.png">







