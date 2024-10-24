# Ladies In Tech Africa SQL Projects
## Table of Contents
- [Acknowledgments](#acknowlegments)
- [Project Review](#project-review)
- [Tools Used](#tools-used)
- [SQL Queries](#sql-queries)
    - [Create Tables](#create-table)
    - [Insert Data](#insert-data)
    - [Update Data](#update-data)
    - [Delete Data](#delete-data)
    - [Truncate Table](#truncate-table)
    - [Aggregate Functions](#aggregate-function)
    - [ORDER BY Clause](#order-by-clause)
    - [Filtering with WHERE Clause](#filtering-with-where-clause)
    - [GROUP BY and HAVING Clauses](#group-by-and-having-clause)
    - [Comparison Operators](#comparison-operators)
    - [List Operators](#list-operators)
    - [Logical Operators](#logical-operators)
    - [Joining Tables](#joining-tables)
    - [UNION and UNION ALL Operators](#union-and-union-all-operators)
    - [Creating a VIEW](#creating-a-view)
    - [Using CASE WHEN](#using-case-when)
    - [International Breweries Analysis](#international=breweries-analysis)
    - [Example SQL file (queries.sql)](#example-sql-file-(queries.sql))



## Acknowledgment 
I would like to express my deepest gratitude to the following individuals and organizations for their support and guidance throughout this project:
First and foremost, I acknowledge the Ladies in Tech African organization for providing the platform and resources necessary to develop my skills in Excel and data analysis. Their commitment to empowering women in technology is truly inspiring.
I would also like to extend my sincere appreciation to my tutor, Mr. Femi Ayodele his expertise, patience, and dedication were instrumental in my success. His guidances were invaluable, and I am grateful for the opportunity to learn from him.

## Project Preview
The "Ladies in Tech" project aims to demonstrate basic SQL skills by creating a database, designing tables, and performing CRUD (Create, Read, Update, Delete) operations.

#### Project Review
This project involves designing and managing a SQL database, including the creation of tables and execution of various SQL queries to perform data manipulation and retrieval.

#### Project Highlights
This project showcases fundamental SQL skills, including table creation, data insertion, updating, deletion, and the use of advanced queries. The effective use of SQL queries extracts key metrics, enabling thorough data analysis and informed decision-making.

#### Key Strengths
- Clear Objectives: Well-defined goals and concise reporting.
- Effective Data Management: Efficient SQL queries for data manipulation and retrieval.
- Well-Structured Queries: Organized and logical structure of SQL queries.
- Thorough Analysis: Comprehensive exploration of database operations and queries.

#### Key Insights
- Employee Data Management: Efficient handling and querying of employee-related data.
- Salary Analysis: Insights into salary distribution and statistics.
- Conditional Logic: Application of conditional logic to categorize data.
- Data Integration: Combining data from multiple tables for comprehensive analysis.
- SQL Database Management System (DBMS)
- SQL Queries

## Objective
The objective of the "Ladies in Tech" project is to demonstrate and enhance fundamental SQL skills by creating a structured database, designing tables, and performing various CRUD (Create, Read, Update, Delete) operations. Additionally, the project aims to showcase the ability to execute advanced SQL queries for data manipulation, retrieval, and analysis.

## Significance
- Skill Development: Provides hands-on experience in SQL, enhancing database management and query writing skills.
- Data Management: Demonstrates efficient handling and manipulation of data within a structured database environment.
- Decision Making: Enables the extraction of key metrics and insights through SQL queries, supporting informed decision-making processes.
- Comprehensive Analysis: Showcases the ability to perform thorough data analysis, including aggregate functions, conditional logic, and data integration from multiple tables.
- Practical Application: Prepares individuals for real-world database management and analysis tasks, making them proficient in using SQL for various business and technical applications.

## Prerequisities
- SQL Database Management System (DBMS)
- Github for reporting the project

## SQL Queries
#### Create Tables
sql code
```
create database LITA_DB

CREATE TABLE Employee (
staffid varchar (10) not null,
FirstName varchar (255) NOT NULL,
SecondName varchar (255),
Gender varchar (10),
Date_of_Birth date,
HireDate datetime,
primary key (staffid)
)

CREATE TABLE PERSON (
personid int identity (1,1) primary key not null,
personname varchar (255) not null,
age int
)

CREATE TABLE Salary (
salary_id int identity (1,1)not null,
Staffid varchar (255),
firstname varchar (255),
lastname varchar (255),
department nvarchar(max),
salary decimal (10, 3) ---(10: precision, 3:scale)
)
```
#### Insert Data
```
insert into salary (staffid, FirstName, lastname, Department, Salary)

values ( 'AB401', 'ayan', 'olakun', 'Information Tech.', 45000.45),
( 'AB212', 'okorie', 'mercy','Account',500000.99999),
( 'AB223', 'joshua', 'chukwuemeka', 'Human Resources',100560.9339999),
( 'AB234', 'sanni', 'ibrahim', 'Sales and Marketing',845688.99),
( 'AB254', 'mercy', 'olanipekun', 'Account',8889.999999),
( 'AB249', 'johnson', 'mercy', 'Information Tech.',234000.90909090),
( 'AB298', 'ayomide', 'halleluyah', 'Logistics', 678000.991999),
( 'AB260', 'deborah', 'justin', 'Logistics',900099.00697969),
( 'AB281', 'wale', 'olanipekun', 'Information Tech',873093.2344)
```
#### Update Data
```
UPDATE SALARY
SET department = 'Information Tech.'
where Staffid = 'AB234'

UPDATE SALARY
SET department = 'Information Tech.'
where Staffid = 'AB240'
```
#### Delete Data
```
delete from employee
where staffid  = 'ab281'
```
#### Truncate Table
```
TRUNCATE TABLE Employees;
```
#### Aggregate Functions
```
SELECT SUM(Salary) AS TOTALSALARY FROM Salary

SELECT AVG(Salary) AS AVERAGESALARY FROM Salary

SELECT COUNT(Staffid) AS EmployeeCount FROM EMPLOYEE
```
#### ORDER BY Clause
```
select count(staffid) as StaffPerSate, state_of_origin 
from Employee
GROUP BY State_of_Origin
order by  count(staffid) desc
```
#### GROUP BY and HAVING Clauses
```
select count(staffid) as StaffPerSate, state_of_origin 
from Employee
GROUP BY State_of_Origin
HAVING COUNT(staffid) >=3
```
#### Comparison Operators
```
Select * from Salary
where salary = 100560.934
```
#### List Operators
```
SELECT * FROM Salary
WHERE department IN ('ACCOUNT', 'LOGISTICS','HUMAN RESOURCES')
```
```
SELECT * FROM Salary
WHERE department NOT IN 
('ACCOUNT', 'LOGISTICS','HUMAN RESOURCES')
```
#### Logical Operators
```
SELECT * FROM EMPLOYEE
WHERE FIRSTNAME = 'JUSTIN'
```
#### Joining Tables
```
select employee.staffid, employee.firstname, employee.gender,
			 employee.hiredate,employee.state_of_origin, Salary.department,
			 Salary.salary
from employee
join Salary
on salary.Staffid = employee.staffid
```
#### UNION and UNION ALL Operators
```
select * from LITA_Store_Lekki
	union all
	select * from LITA_Store_Marina
```
#### Creating a VIEW
```
CREATE VIEW vw_LITA_STORE_TRANSACTION_tbl
 AS
 select 'Lekki Store' as [BRANCHES], customerID AS [CUSTOMERID],
           firstname as [FIRST NAME], lastname as [LAST NAME], 
		   customer_gender as [GENDER],age as AGE, address as [ADDRESS], 
		   transaction_amount as [TRANSACTION AMOUNT]
FROM LITA_Store_Lekki
UNION 
select 'Marina Store' as [BRANCHES], customerID AS [CUSTOMERID],
           firstname as [FIRST NAME], lastname as [LAST NAME], 
		    customer_gender as [GENDER], age as AGE, address as [ADDRESS], 
		   transaction_amount as [TRANSACTION AMOUNT]
from LITA_Store_Marina
```
#### Using CASE WHEN
```

SELECT * FROM Employee

UPDATE Employee
SET State_of_origin = CASE Staff_id
	WHEN 'AB299' THEN 'Jos'
    WHEN 'AB282' THEN 'Abuja'
    WHEN 'AB405' THEN 'Kano'
    WHEN 'AB298' THEN 'Enugu'
    WHEN 'AB234' THEN 'Ekiti'
    WHEN 'AB405' THEN 'Jos'
    WHEN 'AB401' THEN 'Kano'
    ELSE 'Niger'
END;
```
#### International Breweries Analysis
-- INTERNATIONAL BWEWERIES----

SELECT * FROM [dbo].[International_Breweries]

- To  get the total profit
```
SELECT SUM(profit) AS TotalProfit 
FROM [dbo].[International_Breweries]
```
- To get total profit for a particular country
```
SELECT SUM(profit) AS Totalprofit_seneal
FROM [dbo].[International_Breweries]
WHERE countries = 'Senegal'
```
- To get totalprofit for Hero brand
```
SELECT Brands, SUM(profit) AS Totalprofit_nig
FROM [dbo].[International_Breweries]
WHERE countries = 'Nigeria' AND Years = '2019' AND Brands = 'Hero'
GROUP BY Brands 
ORDER BY 2 DESC
```

## Contact
#### Adamu Peace
- Email: peacejoadamu@gmail.com
- LinkedIn: https://www.linkedin.com/in/peace-adamu-34576b23a

