# Practical task for SQL

With tutorial [Databases "SQL Tutorial"](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all) I was able to practically work with the data in these databases.

### Actions that have been taken:

1. Using the SELECT FROM query, I searched for data: ```SELECT * FROM Customers WHERE CustomerName='Alfreds Futterkiste'```;
2. Set a value limit ```LIMIT 10```, pattern searching ```LIKE ('A%')```;
3. Set the sort value alphabetically ```ORDER BY ASC```;
4. Using the INSERT INTO query, I added data: ```INSERT  INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country) VALUES ('Liza', 'Dorosh', 'Street', 'Minsk', 1111, 'Belarus')```;
5. Using the UPDATE query, I changed the created data: ```UPDATE Customers SET ContactName='Lizaveta' WHERE CustomerID = 94```;
6. Using the DELETE request, I deleted the created data: ```DELETE FROM Customers WHERE ContactName='Lizaveta'```;
7. Using the INNER JOIN query, I combined the data of two tables: ```SELECT Orders.OrderID, Customers.CustomerName FROM Orders INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;```;
8. Using the SUBQUERY, I displayed the total quantity of the product 'Queso Cabrales' (column name Summ) shipped to all customers: ```SELECT SUM(Quantity) AS Summ FROM OrderDetails WHERE ProductID IN (SELECT ProductID FROM Products WHERE ProductName='Queso Cabrales');```;
9. Using LEFT JOIN, I transformed the query to combine LastName and FirstName from Employees into a single column separated by a space and nameed it EmployeeName : ```SELECT Orders.OrderID, Customers.CustomerName, CONCAT_WS(' ',Employees.FirstName, Employees.LastName) AS EmployeeName FROM Orders LEFT JOIN Customers ON Orders.CustomerID=Customers.CustomerID LEFT JOIN Employees ON Orders.EmployeeID=Employees.EmployeeID WHERE Customers.Address='Ekergatan 24';```;
10. Using aggregate function AVG, I calculated the average amount of goods supplied in bottles, rounding up to 2 decimal, the column was named Summ: ```SELECT ROUND(AVG(Price),2) AS Summ FROM Products WHERE Unit LIKE "%bottle%";```;
