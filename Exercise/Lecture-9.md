# SQL Subquery
---
other names
> Subquery / Nested query / Subselect / Inner query / Inner Select

### Define
A Subquery is a complete **SELECT** statement embedded within another **SELECT** statement.

For Example: Find out the data of students who live in the city of Roll No. **CS1170**

To solve this query you need to answer two questions;
1. Find out **CS1170** City Name
1. Find all records by city name of **CS1170**

### Types of Subquery
1. **Single Row Subquery** [that return zero or one row to the outer SQL statement]
1. **Multiple Row Subquery** [that returns more than one row to the outer SQL statement]

### Points for Subquery
* Subquery must be enclosed within parentheses.
* The **BETWEEN** operator cannot be used with a subquery. However, the **BETWEEN** operator can be used within the subquery.
* A subquery can have only one column in the **SELECT** clause, unless multiple columns are in the main query for the subquery to compare its selected columns.
* An **ORDER BY** clause cannot be used in a subquery, although the main query can use the **ORDER BY** clause.
* A subquery cannot be placed in the **GROUP BY** Clause
* Subquery that return only one row result will be used with comparison operators like, =,>,<>,etc.
* Subqueries that return more than one row can only be used with multiple value operators such as the IN,ALL,>ANY... operators.

### Single Row Subquery
```SQL
-- Show the data of students who live in the city of Roll No. "CS1170"

SELECT std_Name, std_Cell, std_City
FROM Student_Info
WHERE std_City = (SELECT std_City FROM Student_Info WHERE std_Roll_No = "CS1170")

-- for example: the city of "CS1170" is "Lahore"
-- SELECT std_Name, std_Cell, std_City
-- FROM Student_Info
-- WHERE std_City = "Lahore"
```
```SQL
-- Show the data of the student whose Marks are greater than to the Marks of Roll No. "CS2165"

SELECT std_Roll_No, std_Marks
FROM Student_Result
WHERE std_Marks > (SELECT std_Marks FROM Student_Result WHERE std_Roll_No = "CS2165")
```
```SQL
-- Show the data of the student whose Computer Marks is Greater than & English Marks is less than to the Marks of Roll No. "CS1222"

SELECT std_Roll_No, std_Computer_Marks, std_English_Marks
FROM Student_Result
WHERE std_Computer_Marks > (SELECT std_Computer_Marks FROM Student_Result WHERE std_Roll_No = "CS1222")
AND std_English_Marks < (SELECT std_Marks FROM Student_Result WHERE std_Roll_No = "CS1222")
```

### Multiple Row Subqueries
```SQL
-- Get the records of all the students who are enrolled in the department of "CS"

SELECT * FROM Student_Result 
WHERE std_Roll_No IN (SELECT std_Roll_No FROM Student_Result WHERE std_Roll_No like "CS%")

-- WHERE std_Roll_No IN ("CS1170", "CS2165", "CS1222"...)
```
```SQL
-- Find records that have Marks greater than Roll No. CS2165

SELECT * FROM Student_Result
WHERE std_Marks > ANY (SELECT std_Marks FROM Student_Result WHERE std_Roll_No = "CS2165")
```
---
[Read More](../master/Exercise/Lecture-6.md) about Advance Selection Query (ANY, IN, AND, =>...) etc.
