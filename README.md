# Ladies In Tech Africa SQL Projects
## Table of Contents
- [Acknowledgments](#acknowlegments)
- [Project Review](#project-review)
- [Tools Used](#tools-used)
- [SQL Queries](#sql-queries)
- [Example SQL file (queries.sql)](#example-sql-file-(queries.sql))
- [Projects](#projects)
- 

## Acknowledgment 
I would like to express my deepest gratitude to the following individuals and organizations for their support and guidance throughout this project:
First and foremost, I acknowledge the Ladies in Tech African organization for providing the platform and resources necessary to develop my skills in Excel and data analysis. Their commitment to empowering women in technology is truly inspiring.
I would also like to extend my sincere appreciation to my tutor, Mr. Femi Ayodele his expertise, patience, and dedication were instrumental in my success. His guidances were invaluable, and I am grateful for the opportunity to learn from him.

## Project Review
This repository contains SQL projects completed during the Ladies in Tech Africa SQL class. The projects demonstrate various SQL concepts, including SELECT statements, JOINs, UNIONs, views, and CASE statements.
#### Project Overview
- The repository includes:
- SQL queries for employee and salary databases
- Database design and entity-relationship diagrams
- International Breweries project with profit analysis

## Tools Used
- Database Management System (DBMS): Microsoft SQL Server
- SQL Editor: SQL Server Management Studio (SSMS)
- Version Control: Git, GitHub
  
## SQL Queries
- SELECT statements
- JOINs (INNER, LEFT, RIGHT, FULL)
- UNION and UNION ALL
- Views
- CASE statements
- Database Design
- Employee database schema
- Entity-relationship diagram

  ## Example SQL file (queries.sql)
```
  -- SELECT statements
SELECT * FROM EMPLOYEE;
SELECT * FROM SALARY;

-- JOINs
SELECT employee.staffid, employee.firstname, employee.gender,
       Salary.department, Salary.salary
FROM employee
JOIN Salary
ON salary.Staffid = employee.staffid;

-- CASE statements
SELECT Staffid, firstname, Gender, state_of_origin, Age,
       CASE
           WHEN Age >= 60 THEN 'Senior Executive'
           WHEN Age BETWEEN 40 AND 59 THEN 'Senior Manager'
           WHEN Age BETWEEN 30 AND 39 THEN 'Manager'
           WHEN Age <= 29 THEN 'Assistant Manager'
           ELSE 'Unknown'
       END AS AgeGroup
FROM [dbo].[Employee];
```

  
## Projects
- Employee Database
- Employee information
- Salary analysis
- International Breweries
- Profit analysis by country and brand

## Contact
#### Adamu Peace
- Email: peacejoadamu@gmail.com
- LinkedIn: https://www.linkedin.com/in/peace-adamu-34576b23a

## Acknowledgments
- Ladies in Tech Africa for the SQL class
- SQL Server Management Studio for database management
