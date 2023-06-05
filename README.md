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
  <br>
  <br>
  <b>We're comtinuing to work on high freight charges.  We now want to get the 3 ship countries with the higherst average freight charges.  But instead of filtering for a particular year, we want to use the last 12 months of order data, using as the end date the last OrderDate in Orders</b>
  <br>
  <br>
  Select top (3) ShipCountry,
<br>averagefreight = avg(Freight)
<br>from Orders
<br>where
<br>OrderDate >= DATEADD(yy,-1,(select max(OrderDate) from Orders))
<br>Group by ShipCountry
<br>order by averagefreight desc
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/d99c146f-a321-4097-803d-c3675aef3768)
<br>
  <br>
   <b>We're doing inventory and need to show Employee and Order Detail information like the below for all orders.  Sort bt OrderID and ProductID</b>
  <br>
  <br>
  Select Employees.EmployeeID,
<br>Employees.LastName,
<br>Orders.OrderID,
<br>Products.ProductName,
<br>OrderDetails.Quantity
<br>from Employees
<br>join Orders
<br>on Orders.EmployeeID=Employees.EmployeeID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>join Products
<br>on Products.ProductID=OrderDetails.ProductID
<br>Order by
<br>Orders.OrderID,
<br>Products.ProductID
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/10f27c7c-06bb-4afa-8218-0395b3d81cb1)
<br>
  <br>
   <b>There are customers who have never actually placed an order.  Show these customers</b>
  <br>
  <br>
  Select
<br>Customers_CustomerID=Customers.CustomerID,
<br>Orders_CustomerID=Orders.CustomerID
<br>from Customers
<br>left join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>where
<br>Orders.CustomerID is null
 <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/8a9ee028-038d-4bf3-bb40-817769f639ed)
<br>
  <br>
   <b>One employee (Margaret Peacock, EmployeeIF 4) has placed most the most orders.  However, there are some customers who've placed never an order with her.  Show only those customers who have never an order with her</b>
  <br>
  <br>
  Select
<br>Customers.CustomerID,
<br>Orders.CustomerID
<br>from Customers
<br>left join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>and orders.EmployeeID=4
<br>where
<br>Orders.CustomerID is null
<br>Order by Customers.CustomerID
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/f55a15eb-ff66-4764-b2d5-2a2a5bd22524)
<br>
  <br>
   <b>We want to send all of our high-value customers a special VIP gift.  We're defining high-value customers as those who've made at least 1 order with a total value (not including the discount) equal to $10,000 or more. We only want to consider orders made in the year 2016</b>
  <br>
  <br>
  Select
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>Orders.OrderID,
<br>TotalOrderAmount=SUM(Quantity*UnitPrice)
<br>from Customers
<br>join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>where
<br>OrderDate>='20160101'
<br>and OrderDate<'20170101'
<br>group by
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>Orders.OrderID
<br>having sum(Quantity*UnitPrice)>10000
<br>order by TotalOrderAmount desc
 <Br> 
  <Br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/d952d5b1-0c9c-4193-a049-bf777f2f49f8)
<br>
    <br>
     <b>The manager has changed his mind.  Instead of requiring that customers have at least one individual order totaling %10,000 or more, he wants to define high-value customers differently.  Now, high value customers are customers who have orders totaling $15,000 or more in 2016.</b>
  <br>
    <br>
    Select
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>--Orders.OrderID,
<br>TotalOrderAmount=SUM(Quantity*UnitPrice)
<br>from Customers
<br>join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>where
<br>OrderDate>='20160101'
<br>and OrderDate<'20170101'
<br>group by
<br>Customers.CustomerID,
<br>Customers.CompanyName
<br>--Orders.OrderID
<br>having sum(Quantity*UnitPrice)>15000
<br>order by TotalOrderAmount desc
  <br>
  <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/b3c7c5ae-bac4-4d33-bf8f-4691a04dd88e)
    <br>
    <br>
    <b>Change the answer from the previous problem to use the discount when calculating high-value customers.  Order by the toal amount, taking into consideration the discount.</b>
  <br>
    <br>
    Select
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>TotalWithoutDiscount=SUM(Quantity*UnitPrice),
<br>TotalWithDiscount=SUM(Quantity*UnitPrice*(1-Discount))
<br>from Customers
<br>join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>where
<br>OrderDate>='20160101'
<br>and OrderDate<'20170101'
<br>group by
<br>Customers.CustomerID,
<br>Customers.CompanyName
<br>having SUM(Quantity*UnitPrice*(1-Discount))>15000
<br>order by TotalWithDiscount desc
<br>
<br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/0b0c1c73-bc2c-43d3-9a40-7f26583d3acd)
<br>
    <br>
    <b>At the end of the month, salespeople are likely to try much harder to get orders, to meet their month-end quotas.  Show all orders made on the last day of the month.  Order by EmployeeID and OrderID</b>
    <br>
    <br>
    Select
<br>EmployeeID,
<br>OrderID,
<br>OrderDate
<br>from Orders
<br>where
<br>OrderDate=EOMONTH(OrderDate)
<br>order by
<br>EmployeeID,
<br>OrderID
    <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/548976e3-1b4a-434f-b047-575219a6b4dd)
<br>
    <br>
    <b>The Company's mobile app developers are testing an app that consumers will use to show orders.  In order to make sure that even the largest orders will show up correctly on the app, they'd like some samples of ordersthat have lots of individual line items.  Show the 10 orders with the most line items, in order of total line items</b>
    <br>
    <br>
   Select top 10 
<br>OrderID,
<br>TotalOrderDetails= count(*)
<br>from OrderDetails
<br>Group by OrderID
<br>Order by count(*) desc
    <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/99adf78a-d2ca-44f8-aa8e-f98985b6a1f7)
<br>
    <br>
    <b>The Northwind mobile app developers would now lke to just  get a random assortment of orders for beta testing on their app.  Show set of 2% of all orders</b>
    <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/912e515f-0fe4-49cb-b899-0482bb59383d)
<BR>
  <BR>
    <b>One of the salespeople has come to you with a request.  She thinks that she accidentally entered  line item twice on an order, each time with a different ProductI, but the exact same quantity.  She remembers that the quantity was 60 or more.  Show all OrderIDs with line items that match this, in order of OrderID</b>
    <br>
    <br>
    Select 
<br>OrderID
<br>From OrderDetails
<br>where Quantity>=60
<br>Group by
<br>OrderID, Quantity
<br>having COUNT(*)>1
<br>order by
<br>OrderID
  <br>
    <br>
![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/594b2c68-b5fd-4327-9a9b-816c11114584)
<br>
    <br>
    <b>Based on the previous question, we now want to show details of the order, for orders that match the above criteria</b>
      <br>
      <br>
    ;with PotentialDuplicates as(
<br>Select
<br>OrderID
<br>From OrderDetails
<br>where Quantity>=60
<br>Group by OrderID,Quantity
<br>having count(*)>1)
<br>Select
<br>OrderID,
<br>ProductID,
<br>UnitPrice,
<br>Quantity,
<br>Discount
<br>From OrderDetails
<br>Where 
<br>OrderID in (Select OrderID from PotentialDuplicates)
<br>Order by
<br>OrderID, 
<br>Quantity
    <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/68067283-d516-431a-ae1f-22208000209a)
<br>
    <br>
    <b>Here's another wy of getting the same results as in the previous problems, using a derived table instead of CTE  </b>
<br>
    <br>
 Select 
<br>OrderDetails.OrderID,
<br>ProductID,
<br>Unitprice,
<br>Quantity,
<br>Discount
<br>From OrderDetails
<br>join (
<br>Select distinct
<br>OrderID
<br>From OrderDetails
<br>where Quantity>=60
<br>group by OrderID, Quantity
<br>Having Count(*)>1) PotentialProblemOrders
<br>on PotentialProblemOrders.OrderID = OrderDetails.OrderID
<br>Order by OrderID, ProductID
<br>
<br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/edf03175-537f-4388-a04c-5fc33702c088)
<br>
    <br>
    <b>Some customers are complaining about their orders arriving late.  Which orders are late?  Sort the results by OrderID?</b>
    <br>
    <br>
    Select
<br>OrderID,
<br>OrderDate=CONVERT(date,OrderDate),
<br>RequiredDate=CONVERT(date,RequiredDate),
<br>ShippedDate=CONVERT(date,ShippedDate)
<br>from Orders
<br>where
<br>RequiredDate<=ShippedDate
<br>order by
<br>OrderID
    <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/2009c9fe-c212-4921-a90a-f96ad2cb1344)
<br>
    <br>
    <b>Some salespeople have more orders arriving late than others.  Maybe they're not following up on the order process, and need more training.  Which salespeople have the most orders arriviing late?  </b>
    <br>
    <br>
    Select
<br>Employees.EmployeeID,
<br>LastName,
<br>TotalLateOrders=COUNT(*)
<br>from Orders
<br>join Employees
<br>on Employees.EmployeeID=Orders.EmployeeID
<br>where
<br>RequiredDate<=ShippedDate
<br>group by
<br>Employees.EmployeeID,
<br>Employees.LastName
<br>Order by TotalLateOrders desc
                         <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/609e2b7f-f28f-43e8-a920-fa61a2d65ad6)
<br>
    <br>
    <b>Andrew, the VP of sales has been doing soe more thinking about the problme of late orders.  He realizes that just looking at the number of orders arriving late for each salesperson isn't a good idea.  It needs to be compared to the total number of orders per salesperson.  We want results like the following:  </b>
<br>
    <br>
    ;With LateOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = count(*)
<br>from Orders
<br>where
<br>RequiredDate<=ShippedDate
<br>Group by
<br>EmployeeID
<br>),
<br>AllOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = COUNT(*)
<br>from Orders
<br>Group by
<br>EmployeeID)
<br>Select
<br>Employees.EmployeeID,
<br>LastName,
<br>AllOrders=AllOrders.TotalOrders,
<br>LateOrders=LateOrders.TotalOrders
<br>From Employees
<br>join AllOrders
<br>on AllOrders.EmployeeID=Employees.EmployeeID
<br>Join LateOrders
<br>on LateOrders.EmployeeID=Employees.EmployeeID
<br>order by Employees.EmployeeID
   <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/b189464e-84c5-4a85-abe3-f86d66b64558)
<br>
    <br>
    <b>There's an employee missing in the answer from the problem above.  Fix the SQL to show all employees who have taken orders </b>
    <br>
    <br>
    With LateOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = count(*)
<br>from Orders
<br>where
<br>RequiredDate<=ShippedDate
<br>Group by
<br>EmployeeID
<br>),
<br>AllOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = COUNT(*)
<br>from Orders
<br>Group by
<br>EmployeeID)
<br>Select
<br>Employees.EmployeeID,
<br>LastName,
<br>AllOrders=AllOrders.TotalOrders,
<br>LateOrders=LateOrders.TotalOrders
<br>From Employees
<br>join AllOrders
<br>on AllOrders.EmployeeID=Employees.EmployeeID
<br>left Join LateOrders
<br>on LateOrders.EmployeeID=Employees.EmployeeID
<br>order by Employees.EmployeeID
   <br> 
  <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/60adb1d1-4d3c-46e6-83e8-cd8901383a06)
<br>
    <br>
    <b>Continuing on the answer for the previous problem, let's fix the results for row 5 -Buchanan.  He should have a 0 instead of a Null in LateOrders  </b>
  <br>
  <br>
  ;With LateOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = count(*)
<br>from Orders
<br>where
<br>RequiredDate<=ShippedDate
<br>Group by
<br>EmployeeID
<br>),
<br>AllOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = COUNT(*)
<br>from Orders
<br>Group by
<br>EmployeeID)
<br>Select
<br>Employees.EmployeeID,
<br>LastName,
<br>AllOrders=AllOrders.TotalOrders,
<br>LateOrders=ISNULL(LateOrders.TotalOrders,0)
<br>From Employees
<br>join AllOrders
<br>on AllOrders.EmployeeID=Employees.EmployeeID
<br>left Join LateOrders
<br>on LateOrders.EmployeeID=Employees.EmployeeID
<br>order by Employees.EmployeeID
<br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/82b5e69d-a660-4047-8d74-23385303a295)
<br>
    <br>
    <b>Now we want to get the percentage of late orders over total orders  </b>
  <br>
      <br>
      ;With LateOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = count(*)
<br>from Orders
<br>where
<br>RequiredDate<=ShippedDate
<br>Group by
<br>EmployeeID
<br>),
<br>AllOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = COUNT(*)
<br>from Orders
<br>Group by
<br>EmployeeID)
<br>Select
<br>Employees.EmployeeID,
<br>LastName,
<br>AllOrders=AllOrders.TotalOrders,
<br>LateOrders=ISNULL(LateOrders.TotalOrders,0),
<br>PercentLateOrders=(IsNull(LateOrders.TotalOrders,0)*1.00)/AllOrders.TotalOrders
<br>From Employees
<br>join AllOrders
<br>on AllOrders.EmployeeID=Employees.EmployeeID
<br>left Join LateOrders
<br>on LateOrders.EmployeeID=Employees.EmployeeID
<br>order by Employees.EmployeeID
  <br>
  <br>
      ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/8ebcd5ac-291e-4b7f-8447-39b8e390ae1a)
<br>
      <br>
      <b>So now for the PercentageLateOrders, we get a decimal value like we should.  But to make the output easier to read, let's cut the PercentLateOrders off at 2 digits to the right of the decimal point</b>
  <br>
    <br>
    ;With LateOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = count(*)
<br>from Orders
<br>where
<br>RequiredDate<=ShippedDate
<br>Group by
<br>mployeeID
<br>),
<br>AllOrders as(
<br>Select
<br>EmployeeID,
<br>TotalOrders = COUNT(*)
<br>from Orders
<br>Group by
<br>EmployeeID)
<br>Select
<br>Employees.EmployeeID,
<br>LastName,
<br>AllOrders=AllOrders.TotalOrders,
<br>LateOrders=ISNULL(LateOrders.TotalOrders,0),
<br>PercentLateOrders=convert(decimal(2,2),(IsNull(LateOrders.TotalOrders,0)*1.00)/AllOrders.TotalOrders)
<br>From Employees
<br>join AllOrders
<br>on AllOrders.EmployeeID=Employees.EmployeeID
<br>left Join LateOrders
<br>on LateOrders.EmployeeID=Employees.EmployeeID
<br>order by Employees.EmployeeID
<br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/76c66589-2e78-4340-943b-cb5a66b4c18a)
<br>
    <br>
    <b>Andrew Fuller, the VP of sales at Northwind, would like to do a sales campaign for existing customers.  He'd like to categorize customers into groups, based on how much they ordered in 2016.  Then depending on which group the customer is in, he will target the customer with different sales material.<br>
    The customer grouing categories are 0 to 1000, 1000 to5000, 5000 to 10000 and over 10000.  So if the total ollar mount of the custoer's purchases in that year were between 0 to 1000 they would be in the "Low" group.  A customer with purchases from 1000 to 5000 would be in the Medium group and so on.
    <br>
    We only want to show customers who ordered in 2016.  Orde the results by CustomerID</b>
  <br>
    <br>
;With Orders2016 as (
<br>Select
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>TotalOrderAmount=SUM(Quantity*UnitPrice)
<br>from Customers
<br>join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>where
<br>OrderDate>='20160101'
<br>and OrderDate<'20170101'
<br>Group by
<br>Customers.CustomerID,
<br>Customers.CompanyName)
<br>Select
<br>CustomerID,
<br>CompanyName,
<br>TotalOrderAmount,
<br>CustomerGroup=
<br>Case
<br>when TotalOrderAmount between 0 and 1000 then 'Low'
<br>when TotalOrderAmount between 1001 and 5000 then 'Medium'
<br>when TotalOrderAmount between 5001 and 10000 then 'High'
<br>when TotalOrderAmount > 10000 then 'Very High'
<br>.End
<br>from Orders2016
<br>order by CustomerID
<br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/69edd4a1-8da8-4854-9103-2fda6c4f034d)
<br>
    <br>
    <b> There's a problem with the answer to the previous question.  The CustomerGroup value for one of the rows is null.  Fix the SQL so that there are no nulls in the CustomerGroup field </b>
  <br>
    <br>
    ;With Orders2016 as (
<br>Select
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>TotalOrderAmount=SUM(Quantity*UnitPrice)
<br>from Customers
<br>join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>where
<br>OrderDate>='20160101'
<br>and OrderDate<'20170101'
<br>Group by
<br>Customers.CustomerID,
<br>Customers.CompanyName)
<br>Select
<br>CustomerID,
<br>CompanyName,
<br>TotalOrderAmount,
<br>CustomerGroup=
<br>Case
<br>when TotalOrderAmount >= 0 and TotalOrderAmount < 1000 then 'Low'
<br>when TotalOrderAmount >= 1001 and TotalOrderAmount < 5000 then 'Medium'
<br>when TotalOrderAmount >= 5001 and TotalOrderAmount < 10000 then 'High'
<br>when TotalOrderAmount >= 10000 then 'Very High'
<br>End
<br>from Orders2016
<br>order by CustomerID
  <br>
<br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/b7684270-f9bc-4d1e-a6e2-2ae7cc91c59a)
<br>
    <br>
    <b> Based on the above query, show all the defined CustomerGroups, and the percentage in each.  Sort by total in each group, in descending order </b>
  <br>
  <br>
    ;With Orders2016 as (
<br>Select
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>TotalOrderAmount=SUM(Quantity*UnitPrice)
<br>from Customers
<br>join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>where
<br>OrderDate>='20160101'
<br>and OrderDate<'20170101'
<br>Group by
<br>Customers.CustomerID,
<br>Customers.CompanyName),
<br>CustomerGrouping as(
<br>Select
<br>CustomerID,
<br>CompanyName,
<br>TotalOrderAmount,
<br>CustomerGroup=
<br>Case
<br>when TotalOrderAmount >= 0 and TotalOrderAmount < 1000 then 'Low'
<br>when TotalOrderAmount >= 1001 and TotalOrderAmount < 5000 then 'Medium'
<br>when TotalOrderAmount >= 5001 and TotalOrderAmount < 10000 then 'High'
<br>when TotalOrderAmount >= 10000 then 'Very High'
<br>End
<br>from Orders2016
<br>)
<br>Select
<br>CustomerGroup,
<br>TotalInGroup=COUNT(*),
<br>PercentageInGroup=COUNT(*)* 1 / (select COUNT(*) from CustomerGrouping)
<br>from CustomerGrouping
<br>group by CustomerGroup
<br>order by TotalInGroup desc
<br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/d42b19e6-3b81-4c5a-8262-11b0f326b507)
<br>
    <br>
    <b>Andrew, the VP of Sales is still thinking about how best to group customers, and define low, medium, high and very high value customers.  He now wants to complete flexibility to grouping the customers, based on the dollar amunt they've ordered.  He doesn't want to have to edit SQL i order to change the boundaries of the customer groups.  There's a table called CustomerGroupThereshold that I will need to use.  Use only orders from 2016  </b>
    <br>
    <br>
    ;With Orders2016 as (
<br>Select
<br>Customers.CustomerID,
<br>Customers.CompanyName,
<br>TotalOrderAmount=SUM(Quantity*UnitPrice)
<br>from Customers
<br>join Orders
<br>on Orders.CustomerID=Customers.CustomerID
<br>join OrderDetails
<br>on Orders.OrderID=OrderDetails.OrderID
<br>where
<br>OrderDate>='20160101'
<br>and OrderDate<'20170101'
<br>Group by
<br>Customers.CustomerID,
<br>Customers.CompanyName)
<br>Select
<br>CustomerID,
<br>CompanyName,
<br>TotalOrderAmount,
<br>CustomerGroupName
<br>from 
<br>Orders2016
<br>join CustomerGroupThresholds
<br>on Orders2016.TotalOrderAmount between
<br>CustomerGroupThresholds.RangeBottom and
<br>CustomerGroupThresholds.RangeTop
<br>Order by CustomerID
<br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/081d5ba5-72d6-4c20-ad43-b55afaa53215)
<br>
    <br>
    <b>Some Northwind empoyees are planning a business trip, and would like to visit as many suppliers as ossible.  For their planning they'd like to see a lo st of all countries where suppliers and/or customers are based</b>
    <br>
    <br>
    Select Country from Customers
<br>Union
<br>Select Country from Suppliers
<br>order by Country
  <br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/c5288d84-526a-4cb3-9a52-5f918e35ae13)
<br>
    <br>
    <b>The employees going on the business trip don't want just a raw list of countries, they want more details like a supplierCountry and CustomerCountry  </b>
<br>
    <br>
    ;with SupplierCountries as
<br>(Select Distinct Country from Suppliers),
<br>CustomerCountries as
<br>(Select Distinct Country from Customers)
<br>select
<br>SupplierCountry = SupplierCountries.Country,
<br>CustomerCountry = CustomerCountries.Country
<br>from SupplierCountries
<br.full outer join CustomerCountries
<br>on CustomerCountries.Country=SupplierCountries.Country
    <br>
    <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/55c6a2e1-a02b-4865-8bd5-93108a3667dd)
<br>
    <br>
    <b>The output in the above practice problem is improved, but it's still not ideal.  What we'd really like to see is the country name, total suppliers and the total customers </b>
<br>
    <br>
    ;with SupplierCountries as
<br>(Select Country, Total=COUNT(*) from Suppliers group by Country),
<br>CustomerCountries as
<br>(Select Country, Total=COUNT(*) from Customers group by Country)
<br>select
<br>Country=ISNULL(SupplierCountries.Country, CustomerCountries.Country),
<br>TotalSuppliers=ISNULL(SupplierCountries.Total,0),
<br>TotalCustomers=ISNULL(CustomerCountries.Total,0)
<br>from SupplierCountries
<br>full Outer join CustomerCountries
<br>on CustomerCountries.Country=SupplierCountries.Country
<br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/b91001b3-058b-4783-a68e-31a124160d4d)
<br>
    <br>
    <b>Looking at the Orders table - we'd like to show details for each order that was the first in that particular country, ordered by OrderID. So, for each country, we want one row.  That row should contain  the earliest order for that country, with the associated ShipCountry, CustomerID, OrderID, and OrderDate</b>
    <br>
    <br>
    ;with OrdersByCountry as(
<br>Select
<br>ShipCountry,
<br>CustomerID,
<br>OrderID,
<br>OrderDate=CONVERT(date,OrderDate),
<br>RowNumberPerCountry=ROW_NUMBER()
<br>over (Partition by ShipCountry Order by ShipCountry, OrderID)
<br>From Orders)
<br>Select
<br>ShipCountry,
<br>CustomerID,
<br>OrderID,
<br>OrderDate
<br>from OrdersByCountry
<br>where
<br>RowNumberPerCountry=1
<br>Order by
<br>ShipCountry
<br>
    <br>
    ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/de2af79c-fdca-46b8-89be-121251e53ddb)
<br>
    <br>
    <b>There are some customers for whom freight is a major expense when ordering from Northwind.  
    <br> However by, batching up their orders, and making one larger instead of mutiple smaller orders in a short period of time, they could reduce their freight costs significantly.
    <br>Show those customers who have made more than 1 order in a 5 day period.  The salespeople will use this to help customers reduce their freight costs.
    </b>
    <br>
    <br>
    Select
<br>InitialOrder.CustomerID,
<br>InitialOrderID=InitialOrder.OrderID,
<br>InitialOrderDate=convert(date,InitialOrder.OrderDate),
<br>NextOrderID=NextOrder.OrderID,
<br>NextOrderDate=CONVERT(date,NextOrder.OrderDate),
<br>DaysBetweenOrders=datediff(dd,InitialOrder.OrderDate,NextOrder.OrderDate)
<br>from Orders InitialOrder
<br>join Orders NextOrder
<br>on InitialOrder.CustomerID=NextOrder.CustomerID
<br>where
<br>InitialOrder.OrderID<NextOrder.OrderID
<br>and datediff(dd,InitialOrder.OrderDate,NextOrder.OrderDate)<=5
<br>order by
<br>InitialOrder.CustomerID,
<br>InitialOrder.OrderID
   <br> 
 <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/0550724c-b19c-4ab5-aca2-768795f3252f)
<br>
    <br>
    <b>There's another way of solving the problem above, using Window function.</b>
  <br>
        <br>
        ;with NextOrderDate as(
Select
<br>CustomerID,
<br>OrderDate=CONVERT(date,OrderDate),
<br>NextOrderDate=CONVERT(date,Lead(OrderDate,1)
<br>OVER (Partition by CustomerID order by CustomerID, OrderDate))
<br>from Orders)
<br>Select
<br>CustomerID,
<br>OrderDate,
<br>NextOrderDate,
<br>DaysBetweenOrders=DATEDIFF(dd,OrderDate,NextOrderDate)
<br>from NextOrderDate
<br>where
<br>DATEDIFF(dd,OrderDate,NextOrderDate)<=5
  <br>
        <br>
        ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/003a2a74-800d-43b1-b2d0-d12edd3d8fcf)




