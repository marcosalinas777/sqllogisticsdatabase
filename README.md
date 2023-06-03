# sqllogisticsdatabase
This real world practice problems shows how to bring up my SQL skills to the next level.    This database shows the most common problems you encounter when you deal with data to query.
<br>
<br>
The database has 9 tables, each with its own columns and data:
<br>
We Have the <b>OrderDetails, Orders, Emloyees, Products, Categories, Suppliers, Shippers, Customers and CustomerGroupThresholds</b> tables
<br>
<br>
<b>Let's see which shippers do we have?</b>
  <br>
  <br>
  Select * <br>from Shippers
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/7d15f10f-c9b2-44bb-b71e-547edb497591)
  <br>
  <br>
  <b>Let's see which CategoryName and Descriptions I have in the Categories table?</b>
  <br>
  <br>
  select CategoryName, Description <br>from Categories
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/7e881471-1375-4322-a283-f7256b60fa28)
<br>
<br>
<b>We want to see just the FirstName, LastName and HireDate of all the employees with the title of Sales Representative</b>
  <br>
  <br>
  select FirstName, LastName, HireDate <br>from Employees
<br>where Title='Sales Representative'
<br>
<br>
![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/135bae0a-fde6-4f29-b8e6-44c28dc60583)
<br>
<br>
<b>Now we'd lilke to see the same columns as above, but only for those employees that both have the title of Sales Representative and also are in the United States</b>
  <br>
  <br>
  select FirstName, LastName, HireDate <BR>from Employees
where Title='Sales Representative'
<BR>and
<br>Country='USA'
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/5827dbe4-01c9-411e-852d-eb6a8630d92a)
  <br>
  <br>
<b>Show all the orders placed by a specific employee.  The EmployeeID for this Employee (Steven Buchanan) is 5</b>
  <br>
  <br>
  select OrderID, OrderDate
<br>from Orders
<br>where 
<br>EmployeeID=5
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/73c216db-6faa-4cd0-af51-df79ff5ba6aa)
   <br>
  <br>
<b>In the Suppliers table, show the SupplierID, ContactName and ContactTitle for those Suppliers whose ContactTitle is not Marketing Manager</b>
  <br>
  <br>
select SupplierID, ContactName, ContactTitle
<br>from Suppliers
<br>where ContactTitle <> 'Marketing Manager'
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/9d2b866b-d6fb-4e07-925f-c0c0471e6a32)
 <br>
  <br>
<b>In the Products table, we'd like to see the ProductID and ProductName for those products where the ProductName includes the string 'queso'</b>
  <br>
  <br>
  select ProductID, ProductName
<br>from Products
<br>where ProductName like '%queso%'
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/6c6606d7-cbd9-4e26-8be7-079653aea659)
   <br>
  <br>
<b>Looking at the Orders table, there's a field called ShipCountry.  Write a query that shows the OrderID, CustomerID and ShipCountry for the orders where the ShipCountry is either France or Belgium</b>
  <br>
  <br>

  
  

  


  
  
  



