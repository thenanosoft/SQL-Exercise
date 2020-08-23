# SQL Clause
---

ALL SQL Clauses

1. SELECT CLAUSE
1. TOP CLAUSE
1. FROM CLAUSE
1. WHERE CLAUSE
1. GROUP BY CLAUSE
1. HAVING CLAUSE
1. ORDER BY CLAUSE

The clause in SQL is used to retrieve data from table with different way.

### SELECT CLAUSE
The **SELECT** clause is the basic SQL clause that is used to select data from table

### TOP CLAUSE
The SQL **TOP** clause is used to select N top records. [N is positive integer]

### FROM CLAUSE
The SQL **FROM** clause is used to get the record of the specific table

```SQL
-- select top 10 record from student info table

SELECT TOP[10] * FROM Student_Info


-- select top 5 record from teacher table

SELECT TOP[5] teacher_Name FROM ABC_Teacher


-- select all record from student info table
SELECT * FROM Student_Info
```

### WHERE CLAUSE
The **WHERE** clause is used to filter records with specified condition

```SQL
SELECT * FROM Student_Info
WHERE std_Name = "Farhan" AND std_Age = 20
```

### GROUP BY CLAUSE
The **GROUP BY** statement groups rows that have the same values into summary rows.

```SQL
-- find the number of students from each city

SELECT COUNT(std_Id) , std_City
FROM Student_Info
GROUP BY std_City
```

### HAVING CLAUSE
we could not use **WHERE** clause with aggregate functions (like: count, min, max etc) so that way SQL added **HAVING** clause to select data with aggregate functions.

The **HAVING** clause coud not use without **GROUP BY** clause

```SQL
-- select lists the number of students in each city. Only include cities with more than 100 students 

SELECT COUNT(std_Id) , std_City FROM Student_Info
GROUP BY std_City
HAVING COUNT(std_Id) > 100


-- where and having in one query

SELECT COUNT(Std_Id), std_City FROM Student_Info
WHERE std_City IN ('LAHORE', "ISLAMABAD", "PESHAWAR")
GROUP BY std_City
HAVING COUNT(std_Id) > 100
```


### ORDER BY CLAUSE
The **ORDER BY** clause is used to sort the record in **Ascending** or **Descending** order

by default the record is in ascending order

```SQL
-- ORDER BY ASC with Single column 

SELECT * FROM Std_Info
ORDER BY (std_Age)

-- ORDER BY DESC with using all SQL clause

SELECT TOP[2] COUNT(Std_Id), std_City FROM Student_Info
WHERE std_City IN ('LAHORE', "ISLAMABAD", "PESHAWAR")
GROUP BY std_City
HAVING COUNT(std_Id) > 100
ORDER BY (std_City) DESC


-- ORDER BY Clause used with multiple column

SELECT COUNT(Std_Id), std_City FROM Student_Info
GROUP BY std_City
ORDER BY (std_Id),(std_City) DESC
```

Note: [All the clauses in the list above are in order, You cannot use any down clause before using the up clause, and if you are not using any above clause then you can use the clause below it]

