# sales-insight-project----data-analytics
my first project in which i took a sales database of a computer hardware company and did some analytics using mysql workbench and then made a easy to read sales data visualisation using power BI 





**steps included in the project**
-data discovery
-simple data analysis using some mysql queries
-data cleaning and ETL in power BI which included removing duplicate records , clean anamolies etc
-build a power bi dashboard
-feedback from friends and made some changes ahead of this feedback
-publish a report
-dashboard for access through mobile application






some of the sql queries i used for some simple data analysis

--to show all customer records
select * from customers;

--show total number of customers
select count(*) from customers;

--show transactions for chennai market (market code for chennai is mark001)
select * from transactions where market_code='mark001';

--show distrinct product codes that were sold in chennai
select distinct product_code from transactions where market_code='mark001';

--show transactions where currency is us dollars
select * from transactions where currency="usd"

--show transactions in 2020 join by date table
select transactions.*, date.* from transactions inner join date on transactions.order_date=date.date where date.year=2020;

--show total revenue in year 2020,
select (transactions.sales_amount) from transactions inner join date on transactions.order_date=date.date where date.year=2020 and transactions.currency="inr\r" or transactions.currency="usd\r";

--show total revenue in year 2020, january month,
select sum(transactions.sales_amount) from transactions inner join date on transactions.order_date=date.date where date.year=2020 and and date.month_name="january" and (transactions.currency="inr\r" or transactions.currency="usd\r");

---show total revenue in year 2020 in chennai
select sum(transactions.sales_amount) from transactions inner join date on transactions.order_date=date.date where date.year=2020 and transactions.market_code="mark001";
