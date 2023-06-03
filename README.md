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
<br>where Title='Sales Representative'
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
  select OrderID, CustomerID, ShipCountry
<br>from Orders
<br>where ShipCountry ='France' or ShipCountry= 'Belgium'
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/5a553385-1b41-47d6-b0a5-7858f8e7af24)
<br>
  <br>
  <b>We want to show all OrderID, CustomerID and ShipCountry from orders that came from Brazil, Mexico, Argentina, Venezuela</b>
  <br>
  <br>
  select OrderID, CustomerID, ShipCountry
<br>from Orders
<br>where ShipCountry in('Brazil','Mexico','Argentina','Venezuela')
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/07fc7215-f10d-4a4d-93c2-1dd1bdf9e5a1)
  <br>
  <br>
  <b>For all the employees in the Employees table, show the FirstName, LastName, Title and Birthdate.  Order the results by BirthDate, so we have the oldest employees first</b>
  <br>
  <br>
  Select FirstName, LastName, Title, BirthDate 
<br>from Employees
<br>order by BirthDate 
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/258916da-185d-4406-9b2d-e1db05e84934)
   <br>
  <br>
  <b>In the output of the query above, showing Employees in order of BirthdDate, we see the time of the BirthDate, which we don't want.  Show only the date portion of the BirthDate field</b>
  <br>
  <br>
Select FirstName, LastName, Title, DateOnlyBirthDate = convert(date,BirthDate) 
br>from Employees
<br>order by BirthDate 
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/fcb2918b-ce27-412c-9b5c-3cf4df27d57e)
   <br>
  <br>
  <b>Show the FirstName and LastName columns from the Employees table, and then create a new column called FullName, showing FirstName and LastName joined together in one column, with a space in between</b>
  <br>
  <br>
  Select FirstName, LastName, FullName= concat(FirstName, ' ', LastName)
<br>from Employees
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/b97125a3-92b4-4cd7-ad9f-c9b0adee96c0)
 <br>
  <br>
  <b>xxx</b>
  <br>
  <br>
  
  
  

  
  
  

  
  
  

  
  

  


  
  
  



