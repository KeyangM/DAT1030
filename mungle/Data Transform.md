# Data Transform

1. 
    
    a) Create a new table for your analysis call “sales_genre”.
    
    b) Load the table “sales” into this table.
    
    c)  Select these columns: Genre, Global_Sales, Critic_Score.
    
    ```sql
    CREATE TABLE sales_genre
    (
    Genre string,
    Global_Sales float,
    Critic_Score float
    )
    
    INSERT OVERWRITE TABLE sales_genre
    SELECT Genre, Global_Sales, Critic_Score
    FROM sales
    ;
    ```
    

2)  Round the data found in the “Global_Sales” column.  (HINT:  the SQL function to round a number is ROUND(obs)

```sql
INSERT OVERWRITE TABLE sales_genre
SELECT Genre, 
	ROUND(Global_Sales) AS Global_Sales, 
	Critic_Score
FROM sales_genre;

```

3) Filter the data to only look at those items in the “Critic_Score” column that are greater than 0.

```sql
INSERT OVERWRITE TABLE sales_genre
SELECT *
FROM sales_genre
WHERE Critic_Score > 0
;

```

4) Order the data in the “Critic_Score” column from highest to lowest. (HINT:  Use the DESC query)

```sql
SELECT *
FROM sales_genre
ORDER BY Critic_Score DESC
;

```