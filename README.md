# Fundamentals of SQL - Quiz


???

# Aggregations 



?: Question 1    



In which sequence would you execute the following statements in order to establish a connection to a SQLite database from Python, query it, and return the results:  

1. Use the cursor object's `.execute()` method to query the database  
2. Use `sqlite3`'s `connect()` function to establish a connection to the database    
3. Use the cursor object's `.fetchall()` method to return the results   
4. Import the `sqlite3` package   
5. Use the connection's `.cursor()` method to create a cursor object    


( ) 4-2-5-3-1  
( ) 1-3-4-2-5  
(X) 4-2-5-1-3  
( ) 3-1-4-2-5 



?: Question 2 


Following is a preview of the `cutomers` table: 

|   user_id | city      | state   |
|-----------|-----------|---------|
|         1 | New York  | NY      |
|         2 | Boston    | MA      |
|         3 | Cambridge | MA      |
|         4 | New York  | NY      |
|         5 | New York  | NY      |


Match the code to the relevant output: 


```sql
# 1
SELECT * 
FROM customers
WHERE state = 'MA';

# 2
SELECT * 
FROM customers;

# 3
SELECT user_id, city 
FROM customers;
```

**A** 

|   user_id | city      |
|-----------|-----------|
|         1 | New York  |
|         2 | Boston    |
|         3 | Cambridge |
|         4 | New York  |
|         5 | New York  |

**B** 

|   user_id | city      | state   |
|-----------|-----------|---------|
|         2 | Boston    | MA      |
|         3 | Cambridge | MA      | 

**C** 

|   user_id | city      | state   |
|-----------|-----------|---------|
|         1 | New York  | NY      |
|         2 | Boston    | MA      |
|         3 | Cambridge | MA      |
|         4 | New York  | NY      |
|         5 | New York  | NY      |


( ) 1-A | 2-C | 3-B  
( ) 1-B | 2-A | 3-C  
(X) 1-B | 2-C | 3-A  
( ) 1-A | 2-C | 3-B  


?: Question 3  


Using the table shown above (`customers`), what would the following SQL query output: 

```sql
SELECT state, COUNT(user_id)
FROM customers; 
```

( ) The `state` and `user_id` columns     
( ) An error - You cannot apply `COUNT()` to the `user_id` column     
( ) The count of `user_id`s for each `state`    
(X) An error - You cannot use `COUNT()` without a `GROUP BY`  




?: Question 4  


Following is a preview of the `orders` table: 

|   order_id |   user_id |   order_amount |
|------------|-----------|----------------|
|       1022 |         4 |            100 |
|       1023 |         1 |            120 |
|       1024 |         3 |            200 |
|       1025 |         2 |            150 |
|       1026 |         2 |             50 |
|       1027 |         1 |            200 |
|       1028 |         1 |             70 |
|       1029 |         2 |             90 |  


Match the code to the relevant output: 

```sql
# 1
SELECT user_id, MIN(order_amount) AS amount 
FROM customers
GROUP BY user_id
ORDER BY amount;

# 2
SELECT user_id, MAX(order_amount) AS amount 
FROM customers
GROUP BY user_id
ORDER BY user_id DESC;
``` 

**A**

|   user_id |         amount |
|-----------|----------------|
|         4 |            100 |
|         3 |            200 |
|         2 |            150 |
|         1 |            200 |  

**B**

|   user_id |         amount |
|-----------|----------------|
|         2 |             50 |
|         1 |             70 |
|         4 |            100 |
|         3 |            200 |   



( ) 2-B | 1 - An error. `ORDER BY` doesn't specify ascensing or descending order       
( ) 1-A | 2-B   
(X) 1-B | 2-A 



?: Question 5  


Fill in the blanks such that the following code returns `user_id`s and sum of all `order_amount`s placed by customers in the `'NY'` state, whose `total_amount` is greater than 200: 



```sql
SELECT user_id, SUM(order_amount) AS total_amount 
FROM customers
___ state = 'NY'
GROUP BY user_id
___ total_amount > 200;
```


( ) `HAVING` and `WHERE`   
( ) `BETWEEN` and `WHERE`   
( ) `HAVING` and `IS`    
(X) `WHERE` and `HAVING` 


???
