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

Enhanced Customer Experience: It allows businesses to personalize customer interactions, track preferences, and reward loyalty, fostering stronger relationships.

Operational Efficiency: Automating inventory management, order processing, and payment tracking reduces manual work and errors.

Scalability and Insights: The structured data supports advanced analytics, helping entrepreneurs identify trends, optimize pricing, and forecast demand.

Data-Driven Decisions: It enables entrepreneurs to gain actionable insights through queries and visualizations, which can improve strategies and profitability.

By leveraging this database, entrepreneurs can focus more on growth while the system handles the heavy lifting of data management."


## Data Model 
Explanation of the Data Model: 

This data model represents a relational structure for an e-commerce management system. It supports the storage and organization of various entities, including customers, orders, products, reviews, inventory, payments, shipments, suppliers, and categories. Below is a breakdown of how the data is organized and the relationships between entities:

1. Customer and Order Relationship:
The Customer entity contains information about individual customers, such as name, email, and loyalty points.
Each customer can place multiple orders, represented by the Order entity. This relationship is captured through the customerID in the Order table.
2. Order and OrderItem Relationship:
Orders are linked to individual products via the OrderItem entity. Each order can have multiple products, and this relationship is captured by the orderID and productID in OrderItem.
The OrderItem entity also stores details about the quantity of products ordered, subtotal, and unit price.
3. Product and Category Relationship:
The Product entity stores details about items available for purchase, such as name, price, stock quantity, and discount rates.
Products are categorized using the Category entity, allowing a hierarchical structure of categories with a parent-child relationship (parentCategoryID).
4. Product and Inventory Relationship:
Inventory levels for each product are tracked using the Inventory entity. This includes information about restock dates, quantity added, and cost price.
The Supplier entity is linked to the inventory, storing details about the suppliers who provide the products.
5. Order and Payment Relationship:
Payments for orders are recorded in the Payment entity. This includes details such as payment method, amount, status, and the associated order (orderID).
Each order can have one corresponding payment record.
6. Order and Shipment Relationship:
The Shipment entity tracks the shipping details for each order, including shipment date, tracking number, carrier, and estimated delivery date.
Each order can have one associated shipment record.
7. Customer and Review Relationship:
Customers can leave reviews for products they have purchased, which is captured by the Review entity.
Reviews include a rating, comment, and the date of the review, linking products and customers.
What the Data Model Supports:
Customer Management:
Tracks customer details and loyalty points.
Order Processing:
Captures order details, associated items, and total amounts.
Product Management:
Stores product information, pricing, and categories.
Inventory and Supplier Management:
Tracks stock levels, restock dates, and supplier details.
Payment and Shipment Tracking:
Records payment information and shipping details for orders.
Customer Feedback:
Stores product reviews and ratings from customers.
What the Data Model Does Not Support:
Advanced Marketing Features:
No structure for promotions, campaigns, or loyalty programs beyond loyalty points.
Detailed Service-Level Inventory:
Does not track detailed inventories like batch numbers or expiration dates for specific stock items.
Order Returns or Refunds:
No entity to handle order returns or refunds.
Multi-Vendor Marketplaces:
Does not support multiple vendors selling the same product.
Customer Interaction Records:
No mechanism to track customer inquiries or support requests.

![2954ab4f-6b56-4e31-920c-a65194ef97dc](https://github.com/user-attachments/assets/d60194a2-c36d-4287-9e9f-9bb58ff4ae37)


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
*EXAMPLE IMAGE, DELETE WHEN FINISHED* ![image](https://github.com/user-attachments/assets/75509222-3188-4f22-8777-84274ed7e9b2)

Query #1: Retrieve top 5 customers by total spending, including order details and average spending per order.
![image](https://github.com/user-attachments/assets/63fcf7ac-a470-4d3b-83f1-1e78ab96dc7f)

![00b405d7-400f-4c71-8f26-e88d63355ace](https://github.com/user-attachments/assets/5041b08d-5584-43b4-ad1d-2e6c4b7ba7b2)

Q1 Managerial Perspective: This query provides valuable insights into the behavior and value of high-spending customers. By identifying the top customers based on total spending, managers can focus on retaining these loyal and profitable individuals through targeted marketing campaigns, personalized offers, or loyalty program enhancements. Additionally, metrics like average order value and largest order help refine strategies to encourage higher spending per transaction. 


Query #2: Find the top 3 products by total revenue, with details on supplier, category, and inventory availability.
![image](https://github.com/user-attachments/assets/f0b7d7c6-8bdd-4b26-bb0f-4f0c60e5ca92)

![2a151c4d-0975-48b0-b1f2-c6d3718bcd8a](https://github.com/user-attachments/assets/98fcddbf-52fe-46d7-bdf2-a94b7630eece)

Q2 Managerial Perspective: This query highlights the most profitable products and their associated suppliers, categories, and stock levels. This information enables managers to prioritize inventory planning, supplier relationships, and product promotion strategies. Products with high revenue but low stock may indicate a need for restocking or renegotiating supply contracts. Additionally, the inclusion of discount rate filters ensures focus on sustainable revenue growth rather than heavily discounted products, which may affect margins.


Query #3: 

Q3 Managerial Perspective: 


Query #4: 

Q4 Managerial Perspective: 


Query #5: 

Q5 Managerial Perspective: 


## Tableau Visualizations

Tableau Visualization #1: 

![image](https://github.com/user-attachments/assets/314ae607-1f51-4930-a080-86785f883a41)

Description:
This Tableau chart visualizes top-selling products based on two measures: quantity sold (the bar chart in purple) and subtotal revenue (the line chart in orange). 
Products like Portable SSD have the highest quantities sold, while others like Gaming Mouse or Graphics Card have lower quantities. 
Products with high quantities do not always have the highest revenue, most notably the Portable SSD, which has the highest quantity but comparatively low revenue compared to some of the other products.

Justification:
A combination of a bar graph and a line graph is appropriate for this visualization because it allows for a clear comparison of two distinct but related metrics: quantity sold (bar graph) and subtotal revenue (line graph).
The bar graph is good for showing categorical data and making comparisons across products. 
The line graph highlights trends or patterns in monetary performance and provides a continuous visual narrative of revenue changes.	
Products like the Gaming Chair and 4K Monitor generate much higher revenue ($4,000 and $2,500 respectively) despite lower quantities sold, which suggests higher unit prices. 
Other products, such as the Gaming Headset, have low sales and lower revenue, indicating they are less popular or more niche. 
Items generating the highest revenue may have premium pricing or higher demand in their category. 
The platform can use this data to focus on promoting high-revenue products or improving the sales of low-performing items with high potential. 

Tableau Visualization #2:

Tableau Visualization #3:


## Database Information
Name of the database: cs_lcm85000
