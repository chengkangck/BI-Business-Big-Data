# BI-Business-Big-Data
## 1. Project introduction
Build BI business big data analysis platform, analyze business with actual e-commerce, run through **data generation, data warehouse, ETL, data analysis, visual analysis and business BI report**.

Based on MySQL database, use Kettle and FineBI to realize data visualization. The project uses MySQL as a data analysis storage and query engine, Kettle as a data processing script execution tool, and FineBI to realize data visualization. quickly realize **data analysis** and **visual development** in the future.
The final effect of the project is as follows:
![image](https://github.com/chengkangck/BI-Business-Big-Data/blob/main/images/E-commerce_order_analysis-1.png)



### 1.1 Data source

### 1.2 Project tasks

#### (1) **DataGrip connect to MySQL**, Create itcast_shop database and import data, Create itcast_shop_bi data warehouse

#### (2) **Kettle realizes ETL to data warehouse**

#### (3) MySQL analysis and development: Daily order total/total number analysis, Analysis of the total number of users who placed orders, Hot commodity top10, The number of products on the shelves per hour per day, The number of orders per hour per day, Total order amount/number of orders per day with different payment methods...Summarize data to build a **data warehouse**.

#### (4) FineBI realizes data visualization

![image](https://github.com/chengkangck/BI-Business-Big-Data/blob/main/images/BIArchitecture.png)


## 2. MySQL data analysis and development

### 2.1 Table structure overview
![image](https://github.com/chengkangck/BI-Business-Big-Data/blob/main/images/table%20structure.PNG)

### 2.2 Kettle realizes ETL to data warehouse
There is no data in itcast_shop_bi, it is an empty database. And all our subsequent data analysis will be carried out in this database. The first thing we do is to extract all the tables in the "itcast_shop" database to the "itcast_shop_bi" database. To extract and load data into "itcast_shop_bi", we first need to create a corresponding table in "itcast_shop_bi".

#### 2.2.1 Data extraction business analysis
We are already familiar with the above 6 tables. Not all data in these 6 tables are synchronized to the data warehouse intact at one time, but there are some processing details. Consider the following business scenarios:
- Order analysis needs to be performed every day, for example: how many orders are there in total on April 18, 2020, and what is the total amount of orders.
- User analysis is required every day, for example: how many users registered on April 18, 2020.
- The rate of change of commodity classification and region is very small, because classification and region are almost constant throughout the year.
- The relative frequency of changes in commodity data is relatively high, because commodity information may be updated every day.


