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
  <b>Let's see which CategoryName and Descriptions I have in the Categories table?</b>
  <br>
  <br>
  select CategoryName, Description <br>from Categories
  <br>
  <br>
  ![image](https://github.com/marcosalinas777/sqllogisticsdatabase/assets/95108103/7e881471-1375-4322-a283-f7256b60fa28)
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


  


  
  
  



