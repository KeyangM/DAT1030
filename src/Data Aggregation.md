# Data Aggregation

1) Create 2 tables. The first table shows the average critic score for Sports games. Store this information in a column called “sports_critic_score”. The second table shows the average critic score for Shooter games. Store this information in a column called “shooter_critic_score”.

```sql
SELECT AVG(Critic_Score) AS sports_critic_score
FROM sales
WHERE Genre LIKE "%Sports%";
```

```sql
SELECT AVG(Critic_Score) AS shooter_critic_score
FROM sales
WHERE Genre LIKE "%Shooter%";
```

2) Create 3 statistics tables (average, min, max) for the global_sales for: all games, Sports games, Shooter games. For each table, label the columns as: “average_global_sales”, “min_global_sales”, and “max_global_sales”.

```sql
SELECT AVG(Global_Sales) AS average_global_sales,
			MIN(Global_Sales) AS min_global_sales,
			MAX(Global_Sales) AS max_global_sales
FROM sales;
```

```sql
SELECT AVG(Global_Sales) AS average_global_sales,
			MIN(Global_Sales) AS min_global_sales,
			MAX(Global_Sales) AS max_global_sales
FROM sales
WHERE Genre LIKE "%Sports%";
```

```sql
SELECT AVG(Global_Sales) AS average_global_sales,
			MIN(Global_Sales) AS min_global_sales,
			MAX(Global_Sales) AS max_global_sales
FROM sales
WHERE Genre LIKE "%Shooter%";
```

3) Create 2 tables containing the global_sales and the count of games with that global_sales for: Sports games and Shooter games. For each table, label the columns as: “global_sales” and “count”.

```sql
SELECT Global_Sales AS global_sales,
			COUNT(Names) AS count
FROM sales
WHERE Genre LIKE "%Sports%";
```

```sql
SELECT Global_Sales AS global_sales,
			COUNT(Names) AS count
FROM sales
WHERE Genre LIKE "%Shooter%";
```