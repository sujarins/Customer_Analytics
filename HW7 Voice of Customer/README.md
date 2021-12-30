# Product Recommendation 
### Objective : to uncover associations between items

## 1.Prepare Data
- Loading the collected data, which is collect during class by google forms .<br>
&nbsp;&nbsp;&nbsp;&nbsp; the question : "Have you ever bought xxx?" <br>
&nbsp;&nbsp;&nbsp;&nbsp;    answer    :  only "YES" or "NO"
    
    
- convert letter to numerical data 
![convet collected data](https://user-images.githubusercontent.com/56682174/147476812-2f29dd65-f0cf-4f10-b0f6-79bc4f166a03.png)
- check the most popular items <br>
&nbsp;&nbsp;&nbsp;&nbsp; <img width="200" alt="count items" src="https://user-images.githubusercontent.com/56682174/147598357-98b8687f-1e30-422c-87b7-625f2921cc8e.png">


## 2.Find frequent itemsets
### 2.1) By Apriori Algorithm
Setting min_threshold=1, Lift >= 1.1 and confidence >= 0.7

#### the recommended itemset from Apriori Algorithm
<img width="700" alt="Apriori" src="https://user-images.githubusercontent.com/56682174/147598552-070af1e5-8230-4952-b77a-c9ae4358913e.png">


### 2.2) By Cosine
Setting link>=0.8

#### the recommended itemset from Cosine

<img width="500" alt="cosine" src="https://user-images.githubusercontent.com/56682174/147598736-2b00b7b1-3edc-4960-b412-ee61fd30e304.png">
