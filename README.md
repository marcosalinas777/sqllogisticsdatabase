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
  <b>In the OrderDetails table, we have the fields UnitPrice and Qunatity.  Create a new field, TotalPrice, that multiplies these 2 together.  Show the OrderID, ProductID, UnitPrice, Qunatity and Qunatity.  Order by OrderID and ProductID</b>
  <br>
  <br>  
Select OrderID, ProductID, UnitPrice, Quantity, TotalPrice = (UnitPrice*Quantity)
<br>from OrderDetails
<br>order by OrderID, ProductID
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/6b0e845c-6d8e-452b-ad25-3096e9d8d6e8)
  <br>
  <br>
  <b>How many customers do we have in the Customers table?  Show one value only, and don't rely on getting the record count at the end of a result set</b>
  <br>
  <br>
  Select TotalCustomers=COUNT(CustomerID) 
  <br>from Customers
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/4a89a297-316a-4e60-b8d1-863dd9f261dd)
  <br>
  <br>
  <b>When was the first order?  Show the date of the first order ever made in the Orders table</b>
  <br>
  <br>
  Select firstorder=min(OrderDate)
<br>from Orders
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/3af5d9aa-2843-4be3-bffc-6a22b36c63be)
   <br>
  <br>
  <b>Show a list of countries where the Northwind company has customers</b>
  <br>
  <br>
  Select Country from Customers
<br>group by Country
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/9c1b42f5-7fff-4497-913b-494d7f38ab40)
<br>
  <br>
   <b>Show a list of all the different values in the Customers table for ContactTitles.  Also include a count for each ContactTitle</b>
  <br>
  <br>
  Select ContactTitle, totalcontacttitle=COUNT(*) 
<br>from Customers
<br>group by ContactTitle
<br>order by COUNT(*) desc
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/e93d56b0-07a7-4315-8e87-f3bc603b3b85)
<br>
  <br>
  <b>Show for each product, the associated supplier.  Show the ProductID, ProductName and the CompanyName of the Supplier, sort the Result by ProductID</b>
  <br>
  <br>
  Select ProductID, ProductName, Supplier=CompanyName
<br>from Products
<br>join Suppliers
<br>on Products.SupplierID=Suppliers.SupplierID
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/287952c6-4190-4faa-a564-bd4707a3315e)
<br>
  <br>
  <b>Show a list of the Orders that were made, including the Shipper that was used.  Show the OrderID, OrderDate (date only), and CompanyName of the Shipper, and sort by OrderID, Show only rows with OrderID of less than 10270</b>
  <br>
  <br>
  Select OrderID, OrderDate=CONVERT(date,OrderDate), Shipper=CompanyName
<br>from Shippers
<br>join Orders
<br>on Shippers.ShipperID=Orders.ShipVia
<br>where OrderID<10270
<br>order by OrderID
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/a1b809e4-8e91-44c6-bf25-68a932b21b7a)
  <br>
  <br>
  <b>Show the total number of products in each category.  Sort the results by the number of products, in descending order</b>
  <br>
  <br>
  Select CategoryName, totalproducts=COUNT(*)
<br>from Products
<br>join Categories
<br>on Products.CategoryID=Categories.CategoryID
<br>group by CategoryName
<br>order by COUNT(*) desc
<br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/7ca4fd3e-4609-4ff3-9878-b0eaf402ba01)
<br>
  <br>
  <b>Show a the total number of customers per Country and City</b>
  <br>
  <br>
  Select Country, City, TotalCustomers=COUNT(*)
<br>from Customers
<br>Group by Country, City
<br>order by TotalCustomers desc
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/d99df15f-51e9-4de9-bacb-4b476226706b)
<br>
  <br>
   <b>What products do we have in our inventory that should be reordered?  Where UnitsInStock is less or equal to the ReorderLevel</b>
  <br>
  <br>
  Select ProductID, ProductName, UnitsInStock, ReorderLevel
<br>from Products
<br>where
<br>UnitsInStock<=ReorderLevel
<br>order by 
<br>ProductID
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/262c470e-173a-46c7-9e97-d92b4f5902e9)
<br>
  <br>
   <b>Now we need to incorporate these fields -UnitsInStock, UnitsOnOrder, ReorderLevel, Discontinued -into our calculation.  Define the "products that need reordering" with:
  <br> UnitsInStock + UnitsOnOrder <= ReorderLevel
                                                 <br>
  The Discontinued flag is false(0)</b>
  <br>
  <br>
  Select ProductID, ProductName, UnitsInStock, UnitsOnOrder, ReorderLevel, Discontinued
<br>from Products
<br>where
<br>UnitsInStock + UnitsOnOrder<=ReorderLevel
<br>AND
<br>Discontinued=0
<br>order by 
<br>ProductID
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/f50c678d-8529-4b27-8cc4-be965fe34861)
<br>
  <br>
   <b>A salesperson for the Company is going on a business trip to visit customers, and would like to see a list of all customers, sorted by region alphabetically.  However he wanst the customers with no region (null in the region field) to be at the end, instead of at the top.  Within the same region companies should be sorted by CustomerID</b>
  <br>
  <br>
  Select CustomerID, CompanyName, Region
<br>from Customers
<br>order by
<br>Case
<br>when Region is null then 1
<br>else 0
<br>END,
<br>Region,
<br>CustomerID
<br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/ecf02a35-fbaf-4aca-9e7a-3d611ff8e33d)
<br>
  <br>
  <b>Some of the countries we shipto have very high freight charges.  We'd like to investigate some more shipping otions for our customers, to be able to offer them lower freight charges.  Return the 3 ship countries with the highest average freight overall, in descending order by average freight</b>
  <br>
  <br>
  Select top 3  ShipCountry, averagefreight = AVG(Freight)
<br>from Orders	
<br>group by ShipCountry
<br>order by averagefreight desc
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/0ca405c2-dd01-4acd-b534-da361944502f)
<br>
  <br>
  <b>We're comtinuing on the question above on high freight charges.  Now instead of using all the orders we have, we only want to see orders from the year 2015</b>
  <br>
  <br>
  Select top 3  ShipCountry, averagefreight = AVG(Freight)
<br>from Orders	
<br>where OrderDate>='20150101'
<br>and OrderDate<='20160101'
<br>group by ShipCountry
<br>order by averagefreight desc
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/0d6a1c83-06ab-4e91-9183-dcefeb7e73d3)
<br>
  <br>
  <b>If we use the between command to get the year 2015, we will have an issue of not grabbing order 10806, because the OrderDate data tye is Date Time which includes the time of the day.  The between command in inclusive and would have worked fine if the data type was Date field.  But because the order was done on 20151231 at 11:00:00.000 the query doesnt pick it up because for SQL a Date Time field of '20151231' is equivalent to<br>
  2015-12-31 00:00:00.000
  <br> Tha's why Sweeden came out as 3rd place because the query didn't pick u this french order that was placed at the end of the year</b>
  <br>
  <br>Select top 3  ShipCountry, averagefreight = AVG(Freight)
<br>from Orders	
<br>where OrderDate between '20150101' and '20151231'
<br>group by ShipCountry
<br>order by averagefreight desc
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/3027defc-02a5-4654-bb8c-4b604bc049a6)

  
  
  
  
  
  
  
  
  

  

  
  
  

  
  
  
  

  
  
  

  
  
  

  
  

  


  
  
  



