# 🗃️ Northwind Database - MySQL Project

Welcome to the **Northwind MySQL Project**! This repository contains SQL scripts, queries, and insights derived from the classic Northwind sample database, adapted for MySQL.

---

## 📌 About the Project

The **Northwind database** is a well-known sample dataset that simulates a trading company’s operations. It includes data on customers, orders, products, employees, and more. This project uses the Northwind schema to demonstrate SQL querying, data analysis, and reporting using MySQL.

---

## 🎯 Project Goals

- ✅ Practice SQL skills using a real-world-style dataset
- ✅ Explore relational database design and normalization
- ✅ Generate business insights through SQL queries
- ✅ Create reusable scripts for data analysis and reporting
- ✅ Support learning and teaching of SQL fundamentals

---

## ✨ Key Features

- 📦 Full Northwind schema adapted for MySQL
- 📊 Analytical queries for sales, customers, and employees
- 🔍 Views and stored procedures for reusable logic
- 📈 Sample reports for business intelligence use cases
- 🧪 Clean and modular SQL scripts for easy execution

---

## 🌟 Project Highlights

- **Top Customers Report**: Identify customers with the highest order value
- **Sales by Region**: Analyze sales performance across different territories
- **Employee Performance**: Track order fulfillment and sales by employee
- **Product Insights**: Discover best-selling and underperforming products
- **Monthly Trends**: Visualize sales trends over time

---

## 📁 Repository Sections

- SQL Queries
    This section contains SQL queries used for data extraction, transformation, and analysis. These scripts are designed to explore the Northwind dataset and generate meaningful business insights.

- Documentation
    The documentation offers detailed explanations of the data analysis process and showcases the insights we've uncovered. It includes query logic, visualizations, and interpretations of the results.

- Data
    Access the dataset used for analysis, as well as any cleaned or transformed data, in this section. This includes the original Northwind schema and any modified versions used for reporting.
## Example Queries

--


select * from Customers where Country ='USA' and City  in('Portland', 'Kirkland') order by CustomerName asc;

![image](https://github.com/user-attachments/assets/eb891fa3-841b-4c62-b99b-a5eeab005826)


select * from orders where customerID in(select Customerid from Customers where CustomerName like 'A%');

![image](https://github.com/user-attachments/assets/a8ed95f4-b418-4473-8b36-53c6c14f1b86)


select products.ProductName, suppliers.SupplierName from products
inner join suppliers on products.SupplierID=suppliers.SupplierID
where suppliers.SupplierName = "Tokyo Traders" Order by products.ProductName;

![image](https://github.com/user-attachments/assets/b9368117-ac82-48eb-a6cb-7b5bfe02c906)


SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;

![image](https://github.com/user-attachments/assets/6217f712-e8d3-4be2-bbba-8a3d8f433fdb)


SELECT 
    Categories.CategoryName,
    SUM(Order_Details.Quantity) AS TotalQuantitySold
FROM 
    Categories
Inner JOIN 
    Products ON Categories.CategoryID = Products.CategoryID
Inner JOIN 
    Order_Details ON Products.ProductID = Order_Details.ProductID
GROUP BY 
    Categories.CategoryName
ORDER BY 
    TotalQuantitySold DESC;
    
![image](https://github.com/user-attachments/assets/1df0f110-c6cb-47b6-ade9-ad8a1a6efc82)





