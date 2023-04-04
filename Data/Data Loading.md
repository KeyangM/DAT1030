# Data Loading

Data source: [https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings)

1. Load your csv file in HDInsight using the Azure Storage Tool. Put the data in a container called Sales

I’ve upload the csv file to Azure Storage Explorer.

![Untitled](Data%20Loading%208111c391b31b4cf1b351f048fb18e4aa/Untitled.png)

1. 
    
    A) Create a schema for your data from the raw data.
    
     I’ve tried to use free trial and pay-as-you-go account, but I’m unable to create the HDInsight Cluster with my Azure account. I would create the schema named “VideoGames”.
    
    ![Untitled](Data%20Loading%208111c391b31b4cf1b351f048fb18e4aa/Untitled%201.png)
    
    B) Using your schema, load the data from Azure Storage into Hive. Call the table, “sales”.
    
    ```sql
    CREATE EXTERNAL TABLE sales
    
    (
    Name string,
    Platform string,
    Year_of_Release int,
    Genre string,
    Publisher string,
    NA_Sales float,
    EU_Sales float,
    JP_Sales float,
    Other_Sales float,
    Global_Sales float,
    Critic_Score float,
    Critic_Count float,
    User_Score float,
    User_Count int, 
    Developer string,
    Rating string
    )
    
    ROW FORMAT DELIMITED FIELDS TERMINATED BY ‘,’
    LINES TERMINATED BY ‘\N’
    STORED AS TEXTFILE LOCATION ‘/VideoGames’
    TBLPROPERTIES(”skip.header.line.count”=”1”);
    ```
    
2. Validate that the schema is correct using the “table view” tab.
    
    ```sql
    SELECT * FROM survey LIMIT 10;
    ```
    
3. Inspect the data were loaded properly using the SQL query interface
    
    I’m unable to inspect because I was not able to successfully create HDInsight cluster.