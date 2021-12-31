# Voice of Customer
### Objective : to uncover customer comments and segment into groups

## 1. Data Loading
- Loading data : Wongnai Reviews - Small.csv
 <img width="400" alt="loading data" src="https://user-images.githubusercontent.com/56682174/147811460-3803708c-2ab3-43c8-a799-c2cf5eec2b3c.png">

<br><br>

## 2. Document embedding and dimension reduction
- embed sentences using Universal Sentence Encoder (USE) - got 512 components
- then reduce array dimensions using UMAP - to 30 components
<br><br>


## 3. Document clustering using K-Means
### 3.1) Find the suitable value for K
***From the elbow plot , the suitable K is 4***

<img width="400" alt="elbow plot" src="https://user-images.githubusercontent.com/56682174/147811875-3fff406b-6b11-4b7f-b08a-a4ab7e782113.png">

### 3.2) Run K-Means
Run K-mean and merge label into table

<img width="400" alt="Kmean" src="https://user-images.githubusercontent.com/56682174/147812025-46557967-bc80-4f55-999a-59fb33d21e69.png">


### 3.3) Remove unwanted characters/words and add more words to a custom dictionary
- Remove : special_characters,digit, emoticons, white space, symbols & pictographs, {'ร้าน','กิน','ทาน','ผม','สวัสดี','กก','เรา','ฉัน','ร้า'}
- Add new words : {"สตารบัก","ปลาร้า",'ไม่อร่อย'}

<br><br>

## 4. Data Interpreting
Top keywords of each cluster
<img width="950" alt="top words" src="https://user-images.githubusercontent.com/56682174/147812318-8f847504-4a4d-415a-8b3c-1bee336d2ee7.png">

From top word table, we can identify customer in each group as following:
- ***Cluster ID 0 : Bubble tea***<br>
You can see a lot of “ชา” words, they love to try and share experience.

- ***Cluster ID 1: Wonderful Cafe***<br>
They love a cute cafe, which is wonderful decoration and has a lot of cosy chairs to sit and chill out. on the other hand, they didn’t mention about a tasty dish.

- ***Cluster ID 2: Local Thai Restaurant***<br>
This group pays attention on a delicious Thai dish and price. They don’t mind a restaurant location.

- ***Cluster ID 3: Delicious Family Restaurant***<br>
This group also pays attention on a delicious dish but they don’t mind about price. Most customers are family so the restaurants should quite big.
