# Data-Lemur
## 📊 SQL Query: Histogram of Tweets per User  

### 📝 Problem Statement  
Assume you're given a table `tweets` containing Twitter tweet data. Write a query to obtain a **histogram of tweets per user in 2022**.  

The output should contain:  
- The number of tweets per user (as **tweet bucket**).  
- The count of users who fall into that bucket.  

### 🗂 Table Schema  

| Column Name | Type     |  
|-------------|----------|  
| tweet_id    | integer  |  
| user_id     | integer  |  
| msg         | string   |  
| tweet_date  | timestamp|  

### 📌 Example Input  

| tweet_id | user_id | msg | tweet_date |  
|----------|--------|------------------------------------------------------|-------------------|  
| 214252   | 111    | Am considering taking Tesla private at $420. Funding secured. | 12/30/2021 00:00:00 |  
| 739252   | 111    | Despite the constant negative press covfefe | 01/01/2022 00:00:00 |  
| 846402   | 111    | Following @NickSinghTech on Twitter changed my life! | 02/14/2022 00:00:00 |  
| 241425   | 254    | If the salary is so competitive why won’t you tell me what it is? | 03/01/2022 00:00:00 |  
| 231574   | 148    | I no longer have a manager. I can't be managed | 03/23/2022 00:00:00 |  

### 🎯 Expected Output  

| tweet_bucket | users_num |  
|-------------|----------|  
| 1           | 2        |  
| 2           | 1        |  

### 💡 SQL Query  

```sql
WITH tweet_counts AS (
    SELECT user_id, COUNT(*) AS tweet_bucket
    FROM tweets
    WHERE tweet_date BETWEEN '2022-01-01' AND '2022-12-31'
    GROUP BY user_id
)
SELECT tweet_bucket, COUNT(user_id) AS users_num
FROM tweet_counts
GROUP BY tweet_bucket
ORDER BY tweet_bucket;
