Course: Database Development with PL/SQL (INSY 8311)

Student: ISHIMWE Fabrice

Student ID: 27111

Assignment: Individual Assignment I - Window Functions Mastery Project

Submission Date: September 28, 2025

Repository: plsql-window-functions-ISHIMWE-Fabrice

## Business Problem

StyleMart management faces several operational challenges:

- Identify **top-selling products** per category to optimize inventory and marketing.
- Monitor **monthly revenue trends** and cumulative growth.
- Track **month-over-month purchase growth** to understand customer behavior.
- Segment customers into **quartiles based on total spending** for loyalty programs.
- Calculate **3-month moving averages of average order value** to smooth revenue fluctuations.

## Database Schema

**Tables:**

- **Categories:** `category_id`, `category_name`, `description`  
- **Products:** `product_id`, `product_name`, `category_id`, `price`, `stock_quantity`, `date_added`  
- **Customers:** `customer_id`, `full_name`, `email`, `phone`, `join_date`, `city`  
- **Orders:** `order_id`, `customer_id`, `order_date`, `total_amount`, `status`  
- **Order_Items:** `order_item_id`, `order_id`, `product_id`, `quantity`, `price`  
- **Payments:** `payment_id`, `order_id`, `amount`, `method`, `status`  


**Relationships:**

- Products → Categories (M:1)  
- Orders → Customers (M:1)  
- Order_Items → Orders (M:1)  
- Order_Items → Products (M:1)  
- Payments → Orders (1:1)


## SQL Queries and Analyses

### 1. Top Products per Category
Used window functions: `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `PERCENT_RANK()`.  
Purpose: Identify top-performing products per category and understand their relative sales performance.

### 2. Running Monthly Revenue
Used: `SUM() OVER()`.  
Purpose: Track cumulative revenue month by month for trend analysis.

### 3. Month-over-Month Purchase Growth
Used: `LAG()`.  
Purpose: Compare monthly order counts to detect growth spikes or slowdowns.

### 4. Customer Segmentation by Spending
Used: `NTILE()`, `CUME_DIST()`.  
Purpose: Divide customers into quartiles based on total spending for loyalty and marketing strategies.

### 5. 3-Month Moving Average of Average Order Value
Used: `AVG() OVER(ROWS BETWEEN 2 PRECEDING AND CURRENT ROW)`.  
Purpose: Smooth short-term fluctuations to monitor trends in customer spending.


## Results Analysis

- **Descriptive Analysis:** Identified top products, monthly revenue trends, and average order values.  
- **Diagnostic Analysis:** Detected sales spikes or slowdowns and linked them to specific products or customer segments.  
- **Prescriptive Analysis:** Recommended promotional strategies, customer loyalty initiatives, and inventory optimization based on insights from rankings, quartiles, and moving averages.

## Sample Data

- **8 categories, products, customers, orders, order items, and payments** each were inserted for testing SQL queries.  
- Data represents realistic retail scenarios, including different cities, product categories, and purchase patterns.


## References

1. MySQL 8.0 Documentation Window Functions 
2. TutorialsPoint SQL Window Functions
3. GeeksforGeeks SQL Analytic Functions
4. Course Lecture Notes
5. W3Schools SQL Window Functions Tutorial
6. Ben-Gan, I., & Machanic, A. (2020). T-SQL Window Functions: The Definitive Guide. Redgate Books.
7. Melton, J., & Simon, A. R. (2002). SQL:1999 – Understanding Relational Language Components. Morgan Kaufmann.
8. Vassiliadis, P., Simitsis, A., & Skiadopoulos, S. (2010). Concepts and Techniques for Data Warehousing in Retail. Journal of Data Warehousing, 15(3), 23–39.
9. Connolly, T., & Begg, C. (2015). Database Systems: A Practical Approach to Design, Implementation, and Management (6th ed.). Pearson.
10. SQL Tutorial. (2025). MySQL Window Functions: Ranking, Aggregates, and Moving Averages. Retrieved from https://www.mysqltutorial.org/mysql-window-functions/
