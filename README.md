# Data-Lemur
# 🟢 Easy - Question 1 (Asked in Twitter Interview)

## 📊 SQL Query: Histogram of Tweets per User  

### 📝 Problem Statement  
Assume you're given a table Twitter tweet data, write a query to obtain a histogram of tweets posted per user in 2022. Output the tweet count per user as the bucket and the number of Twitter users who fall into that bucket.

In other words, group the users by the number of tweets they posted in 2022 and count the number of users in each group.


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
---------

# 🟢 Easy - Question 2  (Asked in LinkedIn Interview) 


## 📊 SQL Query: Finding the Best Data Science Candidates  
This question was **asked in a LinkedIn interview!** 🚀
### 📝 Problem Statement  
Given a table of candidates and their skills, you're tasked with finding the candidates best suited for an open Data Science job. You want to find candidates who are proficient in **Python**, **Tableau**, and **PostgreSQL**.

Write a query to list the candidates who possess all of the required skills for the job. Sort the output by candidate ID in ascending order.

**Assumption:**

There are no duplicates in the candidates table.
---

### 🗂 Table Schema  

| Column Name   | Type    |  
|--------------|--------|  
| candidate_id | integer |  
| skill        | varchar |  



### 📌 Example Input  

| candidate_id | skill      |  
|-------------|-----------|  
| 123         | Python    |  
| 123         | Tableau   |  
| 123         | PostgreSQL |  
| 234         | R         |  
| 234         | PowerBI   |  
| 234         | SQL Server |  
| 345         | Python    |  
| 345         | Tableau   |  



### 🎯 Expected Output  

| candidate_id |  
|-------------|  
| 123         |  

📌 **Explanation:**  
- Candidate **123** is included because they have all **three required skills**.  
- Candidate **345** is **not** included because they are missing PostgreSQL.  

---------------------------------------------------------------------------------------------------------------------
