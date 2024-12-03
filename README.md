# MIST4610 Group Project #2 - eCommerce Platform
## Team Name 
Group 9

## Team Members 
1. Lance Moxley @lcm85000
2. Neil Meza @neilmeza
3. Ronit Subramanian @ronsub101
4. Suhayb Ahmed

## Scenario Description:
The database we’ve designed is a comprehensive solution tailored for managing and optimizing the operations of an E-commerce platform. At its core, it organizes critical data—such as customer profiles, products, orders, and payments—into structured, interconnected entities. This structure ensures seamless integration between different facets of the business, enabling efficient workflows and better decision-making. In the real world, this type of database is essential for E-commerce entrepreneurs for several reasons:

**Enhanced Customer Experience:** It allows businesses to personalize customer interactions, track preferences, and reward loyalty, fostering stronger relationships.

**Operational Efficiency:** Automating inventory management, order processing, and payment tracking reduces manual work and errors.

**Scalability and Insights:** The structured data supports advanced analytics, helping entrepreneurs identify trends, optimize pricing, and forecast demand.

**Data-Driven Decisions:** It enables entrepreneurs to gain actionable insights through queries and visualizations, which can improve strategies and profitability.

By leveraging this database, entrepreneurs can focus more on growth while the system handles the heavy lifting of data management.


## Data Model 
**Explanation of the Data Model:**

This data model represents a relational structure for an e-commerce management system. It supports the storage and organization of various entities, including customers, orders, products, reviews, inventory, payments, shipments, suppliers, and categories. Below is a breakdown of how the data is organized and the relationships between entities:

**1. Customer and Order Relationship:**
The Customer entity contains information about individual customers, such as name, email, and loyalty points.
Each customer can place multiple orders, represented by the Order entity. This relationship is captured through the customerID in the Order table.

**2. Order and OrderItem Relationship:**
Orders are linked to individual products via the OrderItem entity. Each order can have multiple products, and this relationship is captured by the orderID and productID in OrderItem.
The OrderItem entity also stores details about the quantity of products ordered, subtotal, and unit price.

**3. Product and Category Relationship:**
The Product entity stores details about items available for purchase, such as name, price, stock quantity, and discount rates.
Products are categorized using the Category entity, allowing a hierarchical structure of categories with a parent-child relationship (parentCategoryID).

**4. Product and Inventory Relationship:**
Inventory levels for each product are tracked using the Inventory entity. This includes information about restock dates, quantity added, and cost price.
The Supplier entity is linked to the inventory, storing details about the suppliers who provide the products.

**5. Order and Payment Relationship:**
Payments for orders are recorded in the Payment entity. This includes details such as payment method, amount, status, and the associated order (orderID).
Each order can have one corresponding payment record.

**6. Order and Shipment Relationship:**
The Shipment entity tracks the shipping details for each order, including shipment date, tracking number, carrier, and estimated delivery date.
Each order can have one associated shipment record.

**7. Customer and Review Relationship:**
Customers can leave reviews for products they have purchased, which is captured by the Review entity.
Reviews include a rating, comment, and the date of the review, linking products and customers.

**What the Data Model Supports:**

- **Customer Management:** Tracks customer details and loyalty points.
- **Order Processing:** Captures order details, associated items, and total amounts.
- **Product Management:** Stores product information, pricing, and categories.
- **Inventory and Supplier Management:** Tracks stock levels, restock dates, and supplier details.
- **Payment and Shipment Tracking:** Records payment information and shipping details for orders.
- **Customer Feedback:** Stores product reviews and ratings from customers.

**What the Data Model _Does Not_ Support:**

- **Advanced Marketing Features:** No structure for promotions, campaigns, or loyalty programs beyond loyalty points.
- **Detailed Service-Level Inventory:** Does not track detailed inventories like batch numbers or expiration dates for specific stock items.
- **Order Returns or Refunds:** No entity to handle order returns or refunds.
- **Multi-Vendor Marketplaces:** Does not support multiple vendors selling the same product.
- **Customer Interaction Records:** No mechanism to track customer inquiries or support requests.

![GROUP PROJECT 2 PNG](https://github.com/user-attachments/assets/d575bb14-3660-4900-8374-1e961adf472f)



## Data Dictionary 
### Customer Table
![image](https://github.com/user-attachments/assets/4dce55d3-4c16-46af-a438-2e6ff3149c42)

### Product Table
![image](https://github.com/user-attachments/assets/dadad371-0fad-445a-92e9-7c5e71dec333)

### Order Table
![image](https://github.com/user-attachments/assets/84d4a04d-4e65-4c58-8560-7e8bfc4c02ad)

### OrderItem Table
![image](https://github.com/user-attachments/assets/9e672031-5045-43da-bb14-0fdcc816527e)

### Category Table
![image](https://github.com/user-attachments/assets/8f61d7bc-7ce2-49f2-af9a-ad656b31f5bd)

### Payment Table
![image](https://github.com/user-attachments/assets/7bfa8e2d-5350-4f5e-96bf-83d8b56ebf12)

### Shipment Table
![image](https://github.com/user-attachments/assets/602cf1cb-79f7-4165-94b8-8ee72253b4f5)

### Supplier Table
![image](https://github.com/user-attachments/assets/4308f5fd-0a47-43dc-90f6-ed77e59d6a13)

### Inventory Table
![image](https://github.com/user-attachments/assets/d1c84cf0-de4c-469b-a9f3-de35ad327470)


## Queries 
### Query #1: Retrieve top 5 customers by total spending, including order details and average spending per order.
![image](https://github.com/user-attachments/assets/63fcf7ac-a470-4d3b-83f1-1e78ab96dc7f)

![00b405d7-400f-4c71-8f26-e88d63355ace](https://github.com/user-attachments/assets/5041b08d-5584-43b4-ad1d-2e6c4b7ba7b2)

**Q1 Managerial Perspective:** This query provides valuable insights into the behavior and value of high-spending customers. By identifying the top customers based on total spending, managers can focus on retaining these loyal and profitable individuals through targeted marketing campaigns, personalized offers, or loyalty program enhancements. Additionally, metrics like average order value and largest order help refine strategies to encourage higher spending per transaction. 


### Query #2: Find the top 3 products by total revenue, with details on supplier, category, and inventory availability.
![image](https://github.com/user-attachments/assets/f0b7d7c6-8bdd-4b26-bb0f-4f0c60e5ca92)

![2a151c4d-0975-48b0-b1f2-c6d3718bcd8a](https://github.com/user-attachments/assets/98fcddbf-52fe-46d7-bdf2-a94b7630eece)

**Q2 Managerial Perspective:** This query highlights the most profitable products and their associated suppliers, categories, and stock levels. This information enables managers to prioritize inventory planning, supplier relationships, and product promotion strategies. Products with high revenue but low stock may indicate a need for restocking or renegotiating supply contracts. Additionally, the inclusion of discount rate filters ensures focus on sustainable revenue growth rather than heavily discounted products, which may affect margins.


### Query #3: Retrieve a list of delayed shipments, including the customer's name, order total, carrier name, shipment delay in days, and total amount paid for the order.
![image](https://github.com/user-attachments/assets/eed8fe8e-8221-4389-8cac-320456dbb84c)
![image](https://github.com/user-attachments/assets/e2c89fe4-f367-4998-98ee-6f8939cec8c7)

**Q3 Managerial Perspective:** 


### Query #4: For each product category, calculate the total revenue generated, the total quantity sold, and the average revenue per product. Include only categories that have contributed more than $7000 in revenue.
![image](https://github.com/user-attachments/assets/96ba9dcc-14eb-4ef6-a536-79da67faab6c)
![image](https://github.com/user-attachments/assets/92a02a16-08c6-402e-b5b9-623eb7c14491)


**Q4 Managerial Perspective:** 


### Query #5: List suppliers who have replenished inventory for multiple products in the past year, including supplier name, the number of products replenished, and the total quantity added.
![image](https://github.com/user-attachments/assets/dd7ca599-948c-4919-930e-55d404cac6a8)
![image](https://github.com/user-attachments/assets/c4fe6b19-0ffd-4828-9d5e-ffcb9224067f)


**Q5 Managerial Perspective:** 


## Tableau Visualizations

**Tableau Visualization #1:** 

![image](https://github.com/user-attachments/assets/314ae607-1f51-4930-a080-86785f883a41)

**Description:**
This Tableau chart visualizes top-selling products based on two measures: quantity sold (the bar chart in purple) and subtotal revenue (the line chart in orange). 
Products like Portable SSD have the highest quantities sold, while others like Gaming Mouse or Graphics Card have lower quantities. 
Products with high quantities do not always have the highest revenue, most notably the Portable SSD, which has the highest quantity but comparatively low revenue compared to some of the other products.

**Justification:**
A combination of a bar graph and a line graph is appropriate for this visualization because it allows for a clear comparison of two distinct but related metrics: quantity sold (bar graph) and subtotal revenue (line graph).
The bar graph is good for showing categorical data and making comparisons across products. 
The line graph highlights trends or patterns in monetary performance and provides a continuous visual narrative of revenue changes.	
Products like the Gaming Chair and 4K Monitor generate much higher revenue ($4,000 and $2,500 respectively) despite lower quantities sold, which suggests higher unit prices. 
Other products, such as the Gaming Headset, have low sales and lower revenue, indicating they are less popular or more niche. 
Items generating the highest revenue may have premium pricing or higher demand in their category. 
The platform can use this data to focus on promoting high-revenue products or improving the sales of low-performing items with high potential. 

**Tableau Visualization #2:**

![image](https://github.com/user-attachments/assets/1e73e69a-82f9-44ac-8c7b-63222dc53f64)

**Description:**
This scatter plot visualizes the relationship between stock availability (measured by "Quantity Added") and sales performance (measured by "Subtotal"). 
Each dot represents a specific product, with the x-axis showing the quantity of stock available and the y-axis showing the total sales.
The color represents different suppliers, helping to categorize products by their source.

**Justification:**
Scatter plots are ideal for showing the correlation between two continuous variables, in this case, stock levels and sales performance. 
This chart allows viewers to quickly spot patterns, such as whether higher stock correlates with higher sales.
It enables easy identification of outliers, such as the Smartphone that is manufactured by Green Earth Goods. 
By encoding supplier information in colors, the chart provides an additional layer of analysis. 
This helps viewers see how different suppliers' products contribute to stock and sales trends.
The chart’s style is suitable for decision-making, as it helps inventory managers and sales teams balance stock levels with demand, identify products that may need restocking, or uncover inventory inefficiencies.

Tableau Visualization #3:
![image](https://github.com/user-attachments/assets/d5f00e39-023a-43d3-a9f6-64d19ae43269)

**Description:**
This is a pie chart showing the distribution of customer ratings. Each segment of the chart represents a percentage of ratings within specific ranges, as indicated by the color-coded scale on the right.
The chart shows percentages of customer ratings divided into distinct categories or ranges, which are based on 1 to 5 star ratings, given by customers.
The largest segment, accounting for 42.86%, is colored brown and accounts for the 5 star reviews. 
Other segments; the 32.86% in yellow and 21.43% in orange, are also represented proportionally and account for the 3 and 4 star reviews respectively.
The smallest segment, contains 2.86% of all of the reviews and accounts for the 2 star reviews. 
In this data set, there are no 1 star reviews, however they would also be represented accordingly in the pie chart, based on the legend. 

**Justification:**
Pie charts are ideal for showing parts of a whole, making it easy to visually compare the relative sizes of each category or rating range.
Since there are only a few categories of ratings, a pie chart provides a straightforward and clean way to display the data.
This chart emphasizes the proportional differences between categories, which is critical for understanding the overall trend in customer feedback.
Ultimately this chart seems to indicate that most customers are at least mostly satisfied with their products, as indicated by the high percentage of 4 and 5 star reviews. 

## Database Information
Name of the database: cs_lcm85000
