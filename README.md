# Skincare Ecommerce Analytics Dataset
An SQL and Power BI analysis of sales performance, customer behavior, product performance, reviews, and returns

**Table Of Content**
- Project Overview
- Business Problem
- Data Description
- Data Preparation and Cleaning
- Feature Engineering
- Tools Used
- SQL Analysis
- Key Insights
- Business Recommendation
- Power BI Dashboard
- Conclusion

## Project Overview
This project analyzes an e-commerce skincare dataset to evaluate sales performance, customer purchasing behavior, product performance, reviews, and product returns. SQL was used for data cleaning, transformation, and analysis, while Power BI was used to create an interactive dashboard and communicate key insights.

### Business Problem

**Sales Performance**
- What is the total revenue, orders, AOV, and units sold
- Revenue trend over time
- Highest and lowest revenue months

**Product Performance**
- What are the top products by revenue, orders, units, and AOV
- Highest return-rate products and categories
- Revenue contribution and relationship between revenue and volume
    
**Customer Analysis**
- New vs. returning customers
- Top customers, average revenue, and orders per customer
- Customer segments and RFM behavior 

**Reviews & Returns**
- Overall return rate and top products/categories by returns
- Average ratings and relationship between ratings and returns
- Revenue from products with high return rates 

**Customer Lifetime Value**
- What is the average revenue per customer
- High-CLV customers and CLV by segment
- How much revenue was contributed by RFM segment

  ### Dataset Description

  **Data Preparation & Cleaning**
  
Data was inspected for missing values, duplicate records, inconsistent data types, and invalid values. Relationships were established between the relevant tables using primary and foreign keys.

**Data Modelling/ Relationship**

The data model uses a relational structure where customer, order, product, review, and return tables are connected through their respective keys.

![](https://github.com/oyekolaqudirat-cmd/Skincare-Ecommerce-Analytics-Dataset/blob/main/Skincare%20Analysis%20Data%20Modelling.png)

#### Feature Engineering

Several calculated columns were created to support the analysis.

**Customer Features**: 
- Customer revenue
- Total orders
- Average order value
- First order date
- Last order date
- Recency days
- Customer lifespan
- Customer status
- Purchase frequency
- Customer segment
- RFM segment 

These features allowed customer purchasing behaviour and value to be analysed more effectively. 

**Product Features**:
- Units sold
- Product revenue
- Average selling price
- Product orders
- Average rating
- Review count
- Return quantity
- Return rate
- Product cost
- Product profit
- Profit margin
  
**Order Features**: 
- Order year
- Order month
- Order month number
- Quarter, Week number
- Day of month
- Day name

These fields support time-based sales analysis and allow months to be correctly ordered chronologically in Power BI. 

**Order Item Features**: 
- Item revenue
- Discount amount
- Item cost
- Item profit 

**Review Feature**: 

Reviews were categorized into: High, Medium, Low 
A positive-review indicator was also created, together with year, month, quarter, and day-name fields. 

**Return Features**

Return reasons were grouped into: Fulfillment Issue, Product Issue, Customer Preference 
Return year, month, month number, and quarter were also created

**Tools used**:
- SQL Server – data cleaning, transformation and analysis
- Power BI – visualization and dashboard development

### SQL Analysis

**Sales Performance Analysis**

The sales analysis examined:
- Total revenue
- Total orders
- Number of purchasing customers
- Average order value
- Total units sold
- Revenue trends over time
- Highest and lowest revenue months

Revenue was analysed by year and month, allowing monthly performance to be compared over time.

 **Product Performance Analysis**
 
Product performance was evaluated using:
- Revenue
- Total orders
- Units sold
- Product AOV
- Return rate
- Product category
- Revenue contribution
- Revenue versus sales volume 

The analysis also created a Product Performance Score based on four dimensions:
Revenue, Orders, Units sold, Average rating.  Products received points when they performed above the relevant average or 
achieved a rating of at least 4. The resulting points were combined into a performance score. 

**Customer Analysis**

Customers were classified as:
- New
- Returning
 
Their proportions were then calculated on how may times they made purchase to understand the customer base.

**Customer Segmentation**: 

Customers were divided according to revenue.
The number of customers, total revenue, and average revenue were then compared across these segments.

| Segment | Revenue |
|-----|-----|
| Low | > 2000 |
| Medium | 2000-3999 |
| High |>= 4000 |

**RFM Analysis**

RFM analysis was used to evaluate customers based on:
- Recency — how recently they purchased
- Frequency — how often they purchased
- Monetary — how much they spent 

Customers were scored using NTILE(5) and then classified into RFM segments. 
The resulting segments were: High Value, At Risk, Loyal Customer, Potential Customer, Low Value. 
The analysis then compared the number of customers, total revenue, average revenue, and revenue contribution of each segment. 

**Key Finding**:  The RFM analysis identified:
- 53 High Value customers, generating 237,562 in revenue.
- 98 At Risk customers, generating 285,551 in revenue.
  
The At Risk segment therefore represented an important revenue group despite its lower recency.

**Returns and Reviews Analysis**

The returns analysis examined: Return rate by product, Return rate by category, Overall return rate, Products with the highest number of returns, Revenue generated by products with high return rates 
A separate view was also created to compare product ratings and return rates. 

**Review Finding**

The analysis notes that product ratings began at 3 or above, meaning no products in the analyzed data had ratings below 3.

**Customer Lifetime Value Analysis**

Customer Lifetime Value analysis examined revenue generated relative to the customer's lifespan.
The analysis calculated:
Average Revenue per Day = Customer Revenue ÷ Customer Lifespan
Customers with high CLV were also examined alongside their RFM segments. 
The analysis also measured what percentage of total revenue came from each RFM segment.

**High Value Customer Purchasing Behaviour**

The purchasing behaviour of high-value customers was analysed using: Purchase frequency, Total orders, AOV, Recency, Quantity purchased.

**Key Finding**

High-value customers recorded:
- 255 total orders 
- 5.09 purchase frequency 
- 951.72 AOV 
- 44,711 units purchased
  
The analysis indicates that their purchasing activity was driven more by purchase frequency than by larger individual order values

### Key Insights

**Customer Insights**

- The customer base consists of both new and returning customers.
- RFM analysis identified distinct customer groups with different purchasing behaviours.
- The At Risk segment generated 285,551, making it an important revenue group to monitor.
- High Value customers generated 237,562 in revenue.
- High-value customers demonstrated relatively strong purchasing activity but had a lower AOV compared with other segments. 

**Product Insights**

- Product performance can be evaluated across revenue, orders, units sold, and ratings.
- The product scoring model provides a way to identify products performing above or below the relevant averages. 
- Product return rates were analysed alongside revenue and ratings. 

**Returns & Reviews**

- Return behaviour varies across products and categories.
- Return reasons were grouped into operational/fulfillment issues, product issues, and customer preference. 
- No product had an average rating below 3 in the analysed data.

### Business Recommendation

**Based on the analysis**:

**Customer Retention**
- Develop targeted retention campaigns for At Risk customers, given their substantial revenue contribution. 
- Encourage repeat purchases among customers with low purchasing frequency. 
- Develop strategies to retain high-value customers. 

**Product Management**
- Monitor products with high return rates. 
- Investigate the reasons behind product-related returns. 
- Prioritize products that perform strongly across revenue, orders, volume, and ratings. 
- Investigate products that perform below the relevant benchmarks. 

**Sales Strategy**
- Monitor monthly revenue trends to identify periods of strong and weak performance.
- Use customer segmentation to create more targeted marketing strategies.
- Monitor AOV alongside purchase frequency to understand how customers generate revenue.

**Power BI Dashboard**

The SQL analysis can be presented in Power BI through several dashboard pages.

**Executive Overview**

**KPIs**
- Total Revenue
- Total Order
- Total Customers
- Quantity Sold
- AOV
  
**Visuals**
![](https://github.com/oyekolaqudirat-cmd/Skincare-Ecommerce-Analytics-Dataset/blob/main/Exexutive%20Overview%20Skincare%20Dashboard.png)

**Product Performance**

**KPIs**
- Quantity Sold
- Total Revenue
- Total Order
- Return Rate

**Visuals**
![](https://github.com/oyekolaqudirat-cmd/Skincare-Ecommerce-Analytics-Dataset/blob/main/Product%20Performance%20Skincare%20Dashboard.png)
  
**Customer Segmentation**

**KPIs**
- Total Customers 
- Returning Customers 
- High Value Customers 
- At Risk Customers

**Visuals**
![]()

**Review and Return Analysis**

**KPIs**
- Total Reviews 
- Average Rating 
- Total Returns
- Return Rate

**Visuals**
![]()

**Conclusion**

This project analysed a skincare e-commerce business across sales, products, customers, reviews, returns, and customer lifetime value.
SQL Server was used to build the relational structure, clean and transform the data, engineer analytical features, perform customer segmentation, calculate RFM metrics, and investigate business performance.
The analysis identified important customer groups, including High Value and At Risk customers, and examined product performance using revenue, orders, units sold, ratings, and returns. The resulting analysis provides a foundation for an interactive Power BI dashboard that communicates the findings and supports data-driven business decision.

**SQL Queries**

```SQL
--Creating Data Base
CREATE DATABASE Skincare_Analytics

--Creating relationships between the tables/Data Modelling
ALTER TABLE orders
ADD CONSTRAINT FK_cust_id
FOREIGN KEY (customer_id) REFERENCES customers (customer_id)

ALTER TABLE order_items
ADD CONSTRAINT FK_orderid
FOREIGN KEY (order_id) REFERENCES orders (order_id)

ALTER TABLE returns
ADD CONSTRAINT FK_returnid
FOREIGN KEY (product_id) REFERENCES products (product_id)

ALTER TABLE returns
ADD CONSTRAINT FK_ordersid
FOREIGN KEY (order_id) REFERENCES orders (order_id)

ALTER TABLE reviews
ADD CONSTRAINT FK_custid_reviews
FOREIGN KEY (customer_id) REFERENCES customers (customer_id)

ALTER TABLE reviews
ADD CONSTRAINT FK_product_reviews
FOREIGN KEY (product_id) REFERENCES products (product_id)


--Data Cleaning/ Checking for null values 
SELECT 
   SUM(CASE WHEN customer_name IS NULL THEN 1 ELSE 0 END) AS Missing_name,
   SUM(CASE WHEN city IS NULL THEN 1 ELSE 0 END) AS Missing_city,
   SUM(CASE WHEN state IS NULL THEN 1 ELSE 0 END) AS Missing_state,
   SUM(CASE WHEN gender IS NULL THEN 1 ELSE 0 END) AS Missing_gender,
   SUM(CASE WHEN age_group IS NULL THEN 1 ELSE 0 END) AS Missing_age,
   SUM(CASE WHEN signup_date IS NULL THEN 1 ELSE 0 END) AS Missing_date,
   SUM(CASE WHEN acquisition_channel IS NULL THEN 1 ELSE 0 END) AS Missing_channel
FROM customers

SELECT
   SUM(CASE WHEN order_date IS NULL THEN 1 ELSE 0 END) AS Missing_orderdate,
   SUM(CASE WHEN order_status IS NULL THEN 1 ELSE 0 END) AS Missing_status,
   SUM(CASE WHEN payment_method IS NULL THEN 1 ELSE 0 END) AS Missing_method,
   SUM(CASE WHEN sales_channel IS NULL THEN 1 ELSE 0 END) AS Missing_channel,
   SUM(CASE WHEN gross_amount IS NULL THEN 1 ELSE 0 END) AS Missing_gamount,
   SUM(CASE WHEN discount_amount IS NULL THEN 1 ELSE 0 END) AS Missing_damount,
   SUM(CASE WHEN shipping_fee IS NULL THEN 1 ELSE 0 END) AS Missing_fee,
   SUM(CASE WHEN final_amount IS NULL THEN 1 ELSE 0 END) AS Missing_famount,
   SUM(CASE WHEN delivered_date IS NULL THEN 1 ELSE 0 END) AS Missing_ddate
FROM orders

SELECT 
   SUM(CASE WHEN quantity IS NULL THEN 1 ELSE 0 END) AS Missing_quantity,
   SUM(CASE WHEN unit_price IS NULL THEN 1 ELSE 0 END) AS Missing_uprice,
   SUM(CASE WHEN discount_pct IS NULL THEN 1 ELSE 0 END) AS Missing_dist,
   SUM(CASE WHEN item_total IS NULL THEN 1 ELSE 0 END) AS Missing_itemtotal
FROM order_items

SELECT 
   SUM(CASE WHEN return_date IS NULL THEN 1 ELSE 0 END) AS Missing_rdate,
   SUM(CASE WHEN return_reason IS NULL THEN 1 ELSE 0 END) AS Missing_reason,
   SUM(CASE WHEN refund_status IS NULL THEN 1 ELSE 0 END) AS Missing_refundstatus
FROM returns

SELECT 
   SUM(CASE WHEN rating IS NULL THEN 1 ELSE 0 END) AS Missing_rating,
   SUM(CASE WHEN review_date IS NULL THEN 1 ELSE 0 END) AS Missing_rdate
FROM reviews

SELECT
   SUM(CASE WHEN product_name IS NULL THEN 1 ELSE 0 END) AS Missing_pname,
   SUM(CASE WHEN category IS NULL THEN 1 ELSE 0 END) AS Missing_category,
   SUM(CASE WHEN concern IS NULL THEN 1 ELSE 0 END) AS Missing_concern,
   SUM(CASE WHEN skin_type IS NULL THEN 1 ELSE 0 END) AS Missing_stype,
   SUM(CASE WHEN key_ingredient IS NULL THEN 1 ELSE 0 END) AS Missing_ingredient,
   SUM(CASE WHEN size IS NULL THEN 1 ELSE 0 END) AS Missing_size,
   SUM(CASE WHEN mrp IS NULL THEN 1 ELSE 0 END) AS Missing_mrp,
   SUM(CASE WHEN cost_price IS NULL THEN 1 ELSE 0 END) AS Missing_cprice,
   SUM(CASE WHEN stock_qty IS NULL THEN 1 ELSE 0 END) AS Missing_sqty,
   SUM(CASE WHEN launch_date IS NULL THEN 1 ELSE 0 END) AS Missing_ldate
FROM products

--Feature Engineering
--Creating columns for the customers table
--Total Revenue per customers
ALTER TABLE customers
ADD customer_revenue BIGINT

--Creating the order amount without th shipping fee
ALTER TABLE orders
ADD order_amount INT

UPDATE orders
SET order_amount = gross_amount - discount_amount

--Calculating the customers revenue column with shipping fee
UPDATE c
SET c.customer_revenue = sub.total_revenue
FROM customers AS c
INNER JOIN (
    SELECT customer_id,
           SUM(final_amount) AS total_revenue
    FROM orders
    GROUP BY customer_id
) AS sub
ON c.customer_id = sub.customer_id

--Total Orders Per Customers
--Creating Column
ALTER TABLE customers
ADD total_order INT

--Updating the column
UPDATE cs
SET cs.total_order = sub.total_o
FROM customers AS cs
INNER JOIN (
      SELECT customer_id, COUNT(DISTINCT order_id) AS total_o
      FROM orders
      GROUP BY customer_id
   ) AS sub
 ON cs.customer_id = sub.customer_id

 --Creating the average order value
ALTER TABLE customers
ADD average_order_value DECIMAL(10, 2)

UPDATE customers
SET average_order_value = customer_revenue / total_order

--Creating the first order date 
ALTER TABLE customers
ADD first_order_date DATE

--Updating the column 
UPDATE cs
SET cs.first_order_date  = cub.first_order
FROM customers AS cs
INNER JOIN (
             SELECT customer_id, MIN(order_date) AS first_order
             FROM orders
             GROUP BY customer_id) AS cub
 ON cs.customer_id = cub.customer_id

 --Craeting the last order column 
ALTER TABLE customers
ADD last_order_date DATE

--Updating the column 
UPDATE cs
SET cs.last_order_date  = cub.LAst_order
FROM customers AS cs
INNER JOIN (
             SELECT customer_id, MAX(order_date) AS last_order
             FROM orders
             GROUP BY customer_id) AS cub
 ON cs.customer_id = cub.customer_id

--Creating recency days
ALTER TABLE customers
ADD recency_days INT

UPDATE cs
SET recency_days = DATEDIFF(day, last_order_date, reference_date)
FROM customers AS cs
CROSS JOIN (SELECT 
              MAX(last_order_date) AS reference_date
            FROM customers
            ) AS cb

--Customer lifespan days
ALTER TABLE customers
ADD customer_lifespan_days INT

UPDATE customers
SET customer_lifespan_days = DATEDIFF(day, first_order_date, last_order_date)

--Creating the customer's status
ALTER TABLE customers
ADD customer_status VARCHAR(30)

UPDATE customers
SET customer_status = CASE WHEN total_order = 1 THEN 'New' 
                           WHEN total_order > 1 THEN 'Returning'
                           END 

--Creating the Purchase Frequency of each customer
ALTER TABLE customers
ADD purchase_frequency DECIMAL(10, 2)

UPDATE customers
SET purchase_frequency = CASE WHEN customer_lifespan_days = 0 THEN 0 
                         ELSE CAST(total_order AS DECIMAL (10, 2)) /customer_lifespan_days                         
                         END
                                     
--Creating column for products table
--Creating total quantity column
ALTER TABLE products
ADD units_sold INT
            
UPDATE ps
SET ps.units_sold  = pd.quantity_sold
FROM products AS ps         
INNER JOIN  (SELECT product_id, 
               SUM(quantity) AS quantity_sold
             FROM order_items
             GROUP BY product_id) AS pd
ON ps.product_id = pd.product_id

--Revenue Per Product(Gross amount without discount and shipping fee)
ALTER TABLE products
ADD product_revenue INT

UPDATE ps
SET ps.product_revenue = ot.Revenue
FROM products AS ps
INNER JOIN (SELECT product_id, 
              SUM(item_total) AS Revenue
            FROM order_items
            GROUP BY product_id) AS ot
ON ps.product_id = ot.product_id

--Average Selling Price
ALTER TABLE products
ADD average_selling_price DECIMAL(10, 2)

UPDATE products
SET average_selling_price = product_revenue / units_sold

--Total Orders
ALTER TABLE products
ADD product_orders INT

UPDATE ps
SET ps.product_orders = od.orders
FROM products AS ps
INNER JOIN  (SELECT product_id, count(*) AS orders
             FROM order_items
             GROUP BY product_id) AS od
ON ps.product_id = od.product_id

--Average Rating per product
ALTER TABLE products
ADD average_rating DECIMAL(10, 1)

UPDATE ps
SET ps.average_rating = rt.Ratings
FROM products AS ps
INNER JOIN (SELECT product_id, AVG(rating) AS Ratings
            FROM reviews
            GROUP BY product_id) AS rt
ON ps.product_id = rt.product_id

--Review count for each products
ALTER TABLE products
ADD review_count INT

UPDATE ps
SET ps.review_count = rt.RC
FROM products AS ps
INNER JOIN (SELECT product_id, COUNT(*) AS RC
            FROM reviews
            GROUP BY product_id) AS rt
ON ps.product_id = rt.product_id

--Return Quantity per products and return rate of each product
ALTER TABLE products
ADD return_quantity INT

UPDATE ps
SET ps.return_quantity = td.returned
FROM products AS ps
INNER JOIN (SELECT product_id, 
               COUNT(*) AS returned
            FROM returns
            GROUP BY product_id) AS td
ON ps.product_id = td.product_id

--Return Rate
ALTER TABLE products
ADD return_rate DECIMAL(10, 2)

UPDATE products
SET return_rate = CAST(return_quantity AS DECIMAL (10, 2)) / units_sold * 100

--Cost per product
ALTER TABLE products
ADD product_cost INT

UPDATE products
SET product_cost = cost_price * units_sold

--Profit per product
ALTER TABLE products
ADD product_profit INT

UPDATE products
SET product_profit = product_revenue - product_cost 

--Profit margin 
ALTER TABLE products
ADD profit_margin DECIMAL(4, 4)

UPDATE products
SET profit_margin = CASE WHEN product_revenue = 0 THEN 0
                    ELSE CAST(product_profit AS DECIMAL (10, 4)) / product_revenue
                    END

--Feature Enginnering for Orders Table
--Order Year
ALTER TABLE orders
ADD order_year INT

UPDATE orders
SET order_year = YEAR(order_date)

 --Order Month
ALTER TABLE orders
ADD order_month VARCHAR(35)

UPDATE orders
SET order_month = FORMAT(order_date, 'MMMM')

--Order Month Number
ALTER TABLE orders
ADD order_month_no INT

UPDATE orders
SET order_month_no = MONTH(order_date)

--Order Quarter
ALTER TABLE orders
ADD order_quarter INT

UPDATE orders
SET order_quarter = DATEPART(Quarter, order_date)

--Order Week 
ALTER TABLE orders
ADD order_week_no INT

UPDATE orders
SET order_week_no = DATEPART(WEEK, order_date)

--Extract the Order Day of the month 
ALTER TABLE orders
ADD order_day INT

UPDATE orders
SET order_day = DATEPART(DAY, order_date)

--Extract the Week Day of the month 
ALTER TABLE orders
ADD order_dayname VARCHAR(30)

UPDATE orders
SET order_dayname = DATENAME(WEEKDAY, order_date)


---Feature Enginnering for the order items table
--item_revenue
ALTER TABLE order_items
ADD item_revenue INT

UPDATE order_items
SET item_revenue  = quantity * unit_price

--Cost Discount Amount
ALTER TABLE order_items
ADD discount_amount INT

UPDATE order_items
SET discount_amount = item_revenue - item_total

--Cost of each order item
ALTER TABLE order_items
ADD item_cost INT

UPDATE oi
SET oi.item_cost = pd.CP
FROM order_items AS oi
INNER JOIN (SELECT p.product_id, order_item_id,
              SUM(quantity * cost_price) AS CP
            FROM order_items o
             JOIN products p
              ON o.product_id = p.product_id
            GROUP BY order_item_id, p.product_id) AS pd
ON oi.product_id = pd.product_id

----Order item profit
ALTER TABLE order_items
ADD item_profit INT

UPDATE order_items
SET item_profit = item_total - item_cost

--Feature Engineering on the reviews table
--Rating Category
ALTER TABLE reviews
ADD rating_category VARCHAR(30)

UPDATE reviews
SET rating_category = CASE
                          WHEN rating >= 4 THEN 'High'
                          WHEN rating = 3 THEN 'Medium'
                          ELSE 'Low'
                          END

--Positive Review
ALTER TABLE reviews
ADD postive_review VARCHAR(30)

UPDATE reviews
SET postive_review = CASE
                        WHEN rating >= 4 THEN 'Yes'
                        ELSE 'No'
                     End
--DATE COLUMN Feature Engineering
--Review year
ALTER TABLE reviews
ADD review_year INT

UPDATE reviews
SET review_year = YEAR(review_date)

--Review Month 
ALTER TABLE reviews
ADD review_month_no INT

UPDATE reviews
SET review_month_no = DATEPART(MONTH, review_date)

--Review Month Number
ALTER TABLE reviews
ADD review_month VARCHAR(30)

UPDATE reviews
SET review_month = FORMAT(review_date, 'MMMM')

--Review Quarter
ALTER TABLE reviews
ADD review_quarter INT

UPDATE reviews
SET review_quarter = DATEPART(Quarter, review_date)

--Review Day Name
ALTER TABLE reviews
ADD review_dayname VARCHAR(30)

UPDATE reviews
SET review_dayname = DATENAME(WEEKDAY, review_date)

--Returns Table Feature Engineering
ALTER TABLE returns
ADD return_category VARCHAR(30)

UPDATE returns
SET return_category = CASE 
                         WHEN return_reason = 'Late delivery' Then 'Fulfillment Issue'
                         WHEN return_reason = 'Wrong item received' Then 'Fulfillment Issue'
                         WHEN return_reason = 'Damaged packaging' THEN 'Product Issue'
                         WHEN return_reason = 'Skin irritation' THEN 'Product Issue'
                         ELSE 'Customer Preference'
                         END

--Return year, month, month number, Quarter
--Return Year
ALTER TABLE returns
ADD return_year INT

UPDATE returns
SET return_year = YEAR(return_date)

--Return Month Name                      
ALTER TABLE returns
ADD return_month VARCHAR(30)

UPDATE returns
SET return_month = FORMAT(return_date, 'MMMM')

--Return Month Number                       
ALTER TABLE returns
ADD return_month_no INT

UPDATE returns
SET return_month_no = DATEPART(Month, return_date)

--Return Quarter
ALTER TABLE returns
ADD return_quarter INT

UPDATE returns
SET return_quarter = DATEPART(Quarter, return_date)

--ANALYSIS
--Revenue Analysis
--Total Revenue
SELECT 
  SUM(order_amount) AS Total_revenue
FROM orders
--How many orders were placed
SELECT COUNT(*) AS Total_order
FROM orders
--How many customers made purchases(Without Shipping Fee)
SELECT 
  COUNT(*)
FROM customers
WHERE total_order >= 1
--what is the average order value
SELECT 
  SUM(order_amount) / COUNT(*) AS AOV
FROM orders
--How many products/units was sold
SELECT 
  SUM(units_sold) AS total_sold
FROM products
--How has the revenue changed over time
SELECT order_year, order_month_no, order_month,  
     SUM(final_amount) AS Revenue
FROM orders
GROUP BY order_year, order_month_no, order_month
ORDER BY order_year, order_month_no 
--What month generated the highest and lowest revenue
WITH Monthly_revenue AS (
            SELECT order_year, order_month, 
                 SUM(final_amount) AS Revenue,
                 RANK () OVER(ORDER BY SUM(final_amount) ASC) AS Lowest,
                 RANK () OVER(ORDER BY SUM(final_amount) DESC) AS Highest
            FROM orders
            GROUP BY order_year, order_month)
SELECT order_year, order_month, Revenue,
      CASE WHEN Lowest = 1 THEN 'Lowest_Revenue'
           WHEN Highest = 1 THEN 'Highest_Revenue'
           END AS Revenue_Rank
FROM Monthly_revenue
WHERE Lowest = 1 OR Highest = 1


--- Product Performance Analysis
--Creating product Revenue without discount and shipping fee
ALTER TABLE products
ADD revenue_without_discount INT 

UPDATE ps
SET ps.revenue_without_discount = ptd.Total_revenue
FROM products AS ps
INNER JOIN ( SELECT ps.product_id, 
                  SUM(order_amount) AS Total_revenue
                FROM products ps
                JOIN order_items oit
                   ON ps.product_id = oit.product_id
                JOIN orders ors
                   ON oit.order_id = ors.order_id
                GROUP BY ps.product_id) AS ptd
 ON ps.product_id = ptd.product_id            


--Total Revenue per products(Without discount and shipping fee)
SELECT product_name, 
   SUM(revenue_without_discount) AS Total_revenue
FROM products
GROUP BY product_name
ORDER BY Total_revenue DESC

--Creating Total Orders column on the product table
ALTER TABLE products
ADD total_orders INT

UPDATE ps
SET ps.total_orders = iot.TOS
FROM products AS ps
INNER JOIN (SELECT ps.product_id, COUNT(DISTINCT ors.order_id) AS TOS
            FROM products ps
            JOIN order_items oit
               ON ps.product_id = oit.product_id
            JOIN orders ors
               ON oit.order_id = ors.order_id
            GROUP BY ps.product_id) AS iot
ON ps.product_id = iot.product_id

--Product with the highest order
SELECT TOP 10 product_name, 
  SUM(total_orders) AS Total_order
FROM products
GROUP BY product_name
ORDER BY product_name DESC

--Products with the highest sold unit/quantity
SELECT product_name, 
  SUM(units_sold) AS Quantity_Sold
FROM products
GROUP BY product_name
ORDER BY Quantity_Sold DESC

--Products with the highest average order value
SELECT product_name, 
  SUM(revenue_without_discount) / SUM(total_orders) AS product_AOV
FROM products ps
GROUP BY product_name
ORDER BY product_AOV DESC

--Products with the highest return rate
SELECT product_name, 
   SUM(return_rate) AS return_rates
FROM products
GROUP BY product_name
ORDER BY return_rates DESC

---What product category perform best
SELECT category, 
  SUM(order_amount) AS Revenue,
  SUM(units_sold) AS Unit_sold,
  COUNT(DISTINCT ors.order_id) AS total_order,
  AVG(average_rating) AS Avg_rating
FROM products ps
JOIN order_items oit
   ON ps.product_id = oit.product_id
JOIN orders ors
   ON oit.order_id = ors.order_id
GROUP BY category
ORDER BY Revenue DESC

--Which Products contributes the largest share of revenue
SELECT product_name, 
  SUM(order_amount) AS Total_revenue,
  SUM(order_amount* 100 ) / (SELECT 
                          SUM(order_amount)
                       FROM orders) AS Percentage_revenue
FROM products ps
JOIN order_items oit
   ON ps.product_id = oit.product_id
JOIN orders ors
   ON oit.order_id = ors.order_id
GROUP BY product_name
ORDER BY Total_revenue DESC

--Are high revenue product also high volume products
SELECT product_name, 
  SUM(order_amount) AS Revenue,
  SUM(units_sold) AS Unit_sold
FROM products ps
JOIN order_items oit
   ON ps.product_id = oit.product_id
JOIN orders ors
   ON oit.order_id = ors.order_id
GROUP BY product_name 
ORDER BY Revenue DESC


--Product Performance Analysis
--To know what products the business should priortize and the ones that are underperforming.
WITH Product_score AS(    
    SELECT product_name,
    --Revenue
    CASE 
     WHEN SUM(product_revenue) > (SELECT 
                                    AVG(product_revenue) AS Avg_revenue
                                  FROM products) THEN 1
      ELSE 0
     END AS Revenue_point,
    --Order
     CASE
        WHEN SUM(total_orders) > (SELECT 
                                   AVG(total_orders) AS Avg_order
                                   FROM products) THEN 1
      ELSE 0
     END AS order_point,
    --Unit Sold
     CASE
        WHEN SUM(units_sold) > (SELECT AVG(units_sold) 
                                 FROM products) THEN 1
        ELSE 0
     END AS unit_point,
     --Rating
      CASE 
        WHEN AVG(average_rating) >= 4 THEN 1
       ELSE 0
      END AS Rating_score
    FROM products
    GROUP BY product_name)
SELECT *,
 Revenue_point +
 order_point +
 unit_point+
 Rating_score AS Performance_Score
FROM Product_score

--Customer Analysis
--How many customers are one time vs returning nad their percentage
SELECT customer_status, COUNT(*) AS CS, 
COUNT(*) * 100 / NULLIF((SELECT COUNT(*)
                         FROM customers), 0)
                         AS Status_percent
FROM customers
GROUP BY customer_status

--Customers with the most revenue
SELECT TOP 10 customer_id, customer_name, 
   SUM(customer_revenue) AS Revenue
FROM customers
GROUP BY customer_id, customer_name
ORDER BY SUM(customer_revenue) DESC

--Average Revenue Per customer
SELECT  
    SUM(customer_revenue)/ COUNT(DISTINCT customer_id) AS Avg_rev_per_customer
FROM customers

--Average order per customer
SELECT 
  SUM(total_order) / COUNT(DISTINCT customer_id) AS Avg_order_per_customer
FROM customers

--High Value Customers
WITH Customer_value AS(
  SELECT customer_id, 
    --Revenue
     CASE 
       WHEN SUM(customer_revenue) > (SELECT
                                      AVG(customer_revenue)
                                     FROM customers) THEN 1
      ELSE 0
     END AS Rev_above_average,
     --Orders
     CASE 
       WHEN SUM(total_order) > (SELECT
                                 AVG(total_order)
                                FROM customers) THEN 1
      ELSE 0
     END AS order_above_average
    FROM customers
    GROUP BY customer_id)
SELECT *,
 CASE 
    WHEN Rev_above_average = 1 AND order_above_average = 1 THEN 'High Value Customer'
   ELSE 'Not High'
 END AS Value
FROM Customer_value

--How does customer spending vary across segment
ALTER TABLE customers
ADD Segment VARCHAR(30)

UPDATE customers
SET Segment = CASE WHEN customer_revenue <= 2000 THEN 'Low'
                  WHEN customer_revenue < 4000 THEN 'Medium'
                  WHEN customer_revenue >= 4000 THEN 'High'
               ELSE 'No Value'
               END 


SELECT Segment, COUNT(DISTINCT customer_id) AS Customers,
SUM(customer_revenue) AS Total_revenue,
AVG(customer_revenue) AS Avg_revenue
FROM customers
GROUP BY Segment
ORDER BY Customers DESC

--RFM(Recency Frequency Monetary)
SELECT customer_id, 
total_order AS Frequency,
customer_revenue AS Monetary,
recency_days AS Recency
FROM customers

--RFM SCORES Using NTILE(5)
 WITH RFM AS(   
    SELECT customer_id, 
    recency_days AS Recency,
    total_order AS Frequency,
    customer_revenue AS Monetary
    FROM customers)
SELECT customer_id, Recency,
Frequency, Monetary, 
--Recency Score
NTILE(5) OVER(ORDER BY Recency DESC) AS Recency_Score,
--Frequency Score
NTILE(5) OVER(ORDER BY Frequency) AS Frequency_Score,
--Monetary Score
NTILE(5) OVER(ORDER BY Monetary) AS Monetary_Score
FROM RFM

--RFM Segment Column
--Creating RFM Segment column
ALTER TABLE customers
ADD RFM_Segment VARCHAR(40)

WITH RFM_score AS(
             SELECT customer_id,  
                NTILE(5) OVER(ORDER BY recency_days DESC) AS R,
                NTILE(5) OVER(ORDER BY total_order) AS F,
                NTILE(5) OVER(ORDER BY customer_revenue) AS M
            FROM customers ),
RFM_Segments AS(SELECT customer_id,
             CASE 
                  WHEN R >= 4 AND F >= 4 AND M >= 4 THEN 'High Value'
                  WHEN R <= 2 AND F >= 3 THEN 'At Risk'
                  WHEN F >= 4 AND R >= 3 THEN 'Loyal Customer'
                  WHEN R >= 4 AND F <= 3 THEN 'Potiential Customer'
               ELSE 'Low Value'
             END AS Segments
            FROM RFM_score) 
UPDATE cs
SET cs.RFM_Segment = rf.Segments
FROM customers AS cs
INNER JOIN RFM_Segments AS rf
  ON cs.customer_id = rf.customer_id

--Segment size and percentage 
SELECT RFM_Segment, 
  COUNT(RFM_Segment) AS Customers,
  COUNT(RFM_Segment) * 100/ (SELECT COUNT(*) 
                              FROM customers) AS Customer_percent
FROM customers
GROUP BY RFM_Segment  

--Comparing revenue across various segment
SELECT RFM_Segment, 
  COUNT(RFM_Segment) AS Customers,
  SUM(customer_revenue) AS Total_revenue,
  AVG(customer_revenue) AS Avg_revenue,
  SUM(customer_revenue) * 100 / (SUM(SUM(customer_revenue)) 
                                   OVER()) AS Revenue_percent
FROM customers
GROUP BY RFM_Segment 
ORDER BY Total_revenue DESC

--Identify high value and at risk customers
WITH RFM AS (
        SELECT customer_id,
            recency_days AS Recency,
          total_order AS Frequency,
          customer_revenue AS Monetary,
          RFM_Segment,
            NTILE(5) OVER(ORDER BY recency_days DESC) AS Recency_Score,
            NTILE(5) OVER(ORDER BY total_order) AS Frequency_Score,
            NTILE(5) OVER(ORDER BY customer_revenue) AS Monetary_Score
        FROM customers)
SELECT *
FROM RFM
WHERE RFM_Segment = 'High Value' OR RFM_Segment = 'At Risk'
ORDER BY RFM_Segment, Monetary DESC
--The RFM analysis identified 53 High Value customers, who generated a total revenue of 237,562. 
--The analysis also identified 98 At Risk customers, who generated 285,551,
--the highest revenue among the customer segments.

--This indicates that the At Risk segment represents an important revenue group despite their declining recency. 
--Their relatively high contribution to total revenue makes them a significant group to monitor and potentially 
--target with customer retention initiatives.

--RETURN AND REVIEW ANALYSIS
--Return Rate by product
SELECT product_name, 
COUNT(*) AS Returned_product,
 (COUNT(*)* 100.0 / (SELECT COUNT(DISTINCT order_id) 
              FROM orders))  AS Return_rate
FROM returns rts
JOIN products pd
 ON rts.product_id = pd.product_id
GROUP BY product_name
ORDER BY Return_rate DESC

--Return rate by category
SELECT category,
   COUNT(*) AS Returned_category,
   (COUNT(*)* 100.0 / (SELECT COUNT(DISTINCT order_id) 
              FROM orders))  AS Return_rate
FROM returns rts
JOIN products pd
 ON rts.product_id = pd.product_id
GROUP BY category
ORDER BY Return_rate DESC

--Overall Return rate
SELECT 
  (COUNT(*)* 100.0 / (SELECT COUNT(DISTINCT order_id) 
              FROM orders))  AS Return_rate
FROM returns rs

--Product with most return
SELECT product_name, 
COUNT(*) AS Returned_product
 FROM returns rts
JOIN products pd
 ON rts.product_id = pd.product_id
GROUP BY product_name

--Average Rating across products
SELECT product_name, average_rating
FROM products
--Avg ratings for all products start with 3 which is above average therefore no product with low ratings.

--Ratings and return rate
CREATE VIEW  RR_score AS
SELECT product_name, 
     AVG(average_rating) AS Avg_rating,  COUNT(return_id) AS TR,
    (COUNT(*)* 100.0 / (SELECT COUNT(DISTINCT order_id) 
              FROM orders))  AS Return_rate
FROM products ps
JOIN returns rs
  ON ps.product_id = rs.product_id
GROUP BY product_name

--Revenue from products with high return rate
WITH Product_returns AS (
        SELECT product_name, SUM(product_revenue) AS Revenue,
          (COUNT(*)* 100.0 / (SELECT COUNT(DISTINCT order_id) 
                              FROM orders))  AS Return_rate
        FROM products ps
        JOIN returns rs
          ON ps.product_id = rs.product_id
        GROUP BY product_name)
SELECT product_name, 
     Revenue, Return_rate
FROM Product_returns
WHERE Return_rate > (SELECT AVG(Return_rate)
                      FROM Product_returns)


--Customer Lifetime Value(CLV)
SELECT customer_id, customer_revenue, customer_lifespan_days,
   NULLIF(customer_revenue ,0) / 
    CASE WHEN customer_lifespan_days = 0 THEN 1 
      ELSE customer_lifespan_days 
    END AS Avg_revenue_per_day
FROM customers

--Customers with high CLV
SELECT RFM_Segment, customer_id, 
customer_revenue, customer_lifespan_days,
   customer_revenue / 
    CASE WHEN customer_lifespan_days = 0 THEN 1 
      ELSE customer_lifespan_days 
    END AS Avg_revenue_per_day
FROM customers
WHERE RFM_Segment = 'High Value'

--Compare customers lifetime value across various segment 
WITH CLV_Segment AS(    
    SELECT Segment, customer_id, 
       customer_revenue, customer_lifespan_days,
       customer_revenue / 
        CASE WHEN customer_lifespan_days = 0 THEN 1 
          ELSE customer_lifespan_days 
        END AS Avg_revenue_per_day
    FROM customers)
SELECT customer_id, 
       customer_revenue, customer_lifespan_days, 
  CASE WHEN Segment = 'High' THEN Avg_revenue_per_day ELSE 0 END AS High_revenue_per_day,
  CASE WHEN Segment = 'Medium' THEN Avg_revenue_per_day ELSE 0 END AS Mid_revenue_per_day,
  CASE WHEN Segment = 'Low' THEN Avg_revenue_per_day ELSE 0 END AS low_revenue_per_day
FROM CLV_Segment
ORDER BY customer_revenue DESC

--What percentage of revenue comes from high value customer
SELECT RFM_Segment, SUM(customer_revenue),
   SUM(customer_revenue) * 100 / 
                      (SELECT SUM(customer_revenue)
                       FROM customers) AS Segment_percent
FROM customers
GROUP BY RFM_Segment


--Purchasing behavoiur of the high value customers
SELECT RFM_Segment, 
   SUM(purchase_frequency) AS Frequency,
   COUNT(DISTINCT od.order_id) AS Total_order,
   AVG(average_order_value) AS AOV,
   AVG(recency_days) AS Recency,
   SUM(units_sold) AS Quantity
FROM customers cs
 JOIN orders od
   ON cs.customer_id = od.customer_id
 JOIN order_items oit
   ON od.order_id = oit.order_id
JOIN products ps
   ON oit.product_id = ps.product_id
WHERE RFM_Segment = 'High Value'
GROUP BY RFM_Segment

--High-value customers demonstrated moderate purchasing activity, with 255 total orders and 
--a purchase frequency of 5.09, ranking third among the customer segments for both metrics. 
--However, they recorded the lowest average order value (AOV) of 951.72, indicating that 
--their relatively high purchasing activity was driven more by purchase frequency than by 
--larger individual orders. They also purchased a total of 44,711 units.
```



