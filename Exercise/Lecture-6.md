# SQL Advance Level SELECT Statement

> Please make new table as you want we already learn how to create table and column in sql in lecture #1 or Lecture #2

### SELECT Statement with DISTINCT Keyword
A table data can contain several duplicate values. Select statement does not ignore/remove/eliminate duplicate data. To eliminate the duplicates, we use the DISTINCT keyword.

*For Example:* in ABC School have different designation like Priniciple, Administrator, Worker, etc.

*[Without Distinct Keyword]*
|Designation|Count|
|-|-|								
|Principle|1|
|Administrator|1|
|Administrator|1|
|Worker|1|
|Worker|1|
|Worker|1|

*[With Distinct Keyword]*
|Designation|Count|
|-|-|							
|Principle|1|
|Administrator|2|
|Worker|3|
```SQL
#without counting the number of duplicate values
SELECT DISTINCT Designation
FROM ABC_Designation

#with counting the number of duplicate values
SELECT DISTINCT Designation, COUNT(Designation)
FROM ABC_Designation
```

### SELECT Statement with Arithmetic Operators
In SQL we use these arithmetic operators (addition,subtraction,multiplcation,division,modulus).
When you use these operators then must check the column is numeric data type.

*For Example:*

Teacher_Salary * 1.2 | Joining_Date + 10 | std_Age / 2  [All ✔]

std_Name * 2 | Street_Address + 1  [All ❌]

```SQL
#calculate the teacher salary after an addition of 10%
SELECT teacher_Name, teacher_salary, teacher_salary * 1.1
FROM ABC_Teachers

#add 10 days from the hiring date
SELECT teacher_Name, hiring_Date, hiring_Date + 10
FROM ABC_Teachers
```

### Use of AS keyword
To give any name to the computed field we use "AS" keyword
```SQL
#calculate the teacher salary after an addition of 10% and the addition column name set "Increase"
SELECT teacher_Name, teacher_salary, teacher_salary * 1.1 AS Increase
FROM ABC_Teachers
```

### WHERE Clause
WHERE Clause is use to retrieve only those record who fulfil the specified criteria or condition.
```SQL
# show only those teacher name their salary is greater than 20 thousand
SELECT teacher_Name from ABC_Teachers
WHERE teacher_salary > 20000
```

### SQL Operators
There are two types of operators that are commonly used in SQL

**1. Comparison Operators**

|Operator|Discription|
|-|-|
|=|Is Equal to|
|<>|Is not Equal to|
|>|Is Greater than|
|<|Is Less than|
|>=|Is Greater than or Equal to|
|<=|Is Less than or Equal to|


**2. Logical Operators**

|Operator|Discription|
|-|-|
|ALL|TRUE if all of the subquery values meet the condition|
|ANY|TRUE if any of the subquery values meet the condition|
|AND|TRUE if all conditions is TRUE that separated by AND|
|NOT|Display record if the condition is NOT TRUE|
|OR|True if any condition is TRUE that are separated by OR|
|IN|TRUE if record match one of a list of expression|
|BETWEEN|TRUE if record is within the range of expressions|
|EXISTS|TRUE if subquery is return one or more record|
|LIKE|True if record match the pattern|


**SQL COMPARISON Operator Statement Examples**
```SQL
# Equal to
SELECT std_Name FROM Student_Info
WHERE std_Name = "Farhan"

# Is not Equal to
SELECT std_Name FROM Student_Info
WHERE std_Last_Name <> "Ali"

# Is greater than
SELECT std_Name FROM Student_Info
WHERE std_Age > 18

# Is less than
SELECT std_Name FROM Stduent_Info
WHERE std_Age < 25

# Is Greater than or equal to
SELECT std_Name FROM Student_Info
WHERE std_Enroll_Date >= '2020-01-15'

# IS Less than or Equal to
SELECT std_Name FROM Student_Info
WHERE std_Enroll_Date <= '2019-01-15'
```

**SQL Logical OERATOR Statements Examples**
> in future we learn subquery how it's work
```SQL
# ALL Operator (if any record found in the table that can not fulfil the condition then no data is return)
# Example: 35 > 1 to 34; if (any student have 36 or Greater than from given age[35] then no data return) else (the condition is true and the all record is return)

SELECT * FROM Student_Info
WHERE std_Age > ALL (SELECT std_Age FROM Student_Info WHERE std_Age > 35)

#-----------------------------------------------------------------------------

# ANY Operator (if any record is equal to given date then the data is return otherwise the condition is false and record not return)

SELECT * FROM Student_Info
WHERE std_Enroll_Date = ANY (SELECT std_Enroll_Date FROM Student_Info WHERE std_Enroll_Date = '2020-02-29')

#-----------------------------------------------------------------------------

# AND Operator
SELECT * FROM Student_Info
WHERE std_Age > 18 AND std_Address = "Lahore"

#-----------------------------------------------------------------------------

# NOT Operator
SELECT * FROM Student_Info
WHERE NOT std_Address = "Lahore"

#-----------------------------------------------------------------------------

# OR Operator
SELECT * FROM Student_Info
WHERE NOT std_Address = "Lahore" OR NOT std_Address = "Islamabad"

#-----------------------------------------------------------------------------

# IN Operator
SELECT * FROM Student_Info
WHERE std_Address IN ('Lahore','Islamabad','Peshawar')

#-----------------------------------------------------------------------------

#BETWEEN Operator
SELECT * FROM Student_Info
WHERE std_Age BETWEEN 50 AND 60

#-----------------------------------------------------------------------------

#EXISTS Operator
SELECT * FROM Student_Info
WHERE EXISTS (SELECT student_Name From Student_Info WHERE std_Id = 11070 AND std_First_Name = "Farhan")

#-----------------------------------------------------------------------------

# Like Operator
# % : The percent sign represents zero, one, or multiple characters
# _ : The underscore represents a single character

#Example 1 [find any name that start with "Mohammad"]

SELECT std_Name FROM Student_Info
WHERE std_Name LIKE 'Mohammad%'


#Example 2 [find any name that end with "Khan"]

SELECT std_Name FROM Student_Info
WHERE std_Name LIKE '%Khan'


#Example 3 [find any name that have "aa" in any position]

SELECT std_Name FROM Student_Info
WHERE std_Name LIKE '%aa%'


#Example 4 [find any name that have "h" in the third position]

SELECT std_Name FROM Student_Info
WHERE std_Name LIKE 'Mo_%'


#Example 5 [find any name that start with "F" & Atleast 3 charachters]

SELECT std_Name FROM Student_Info
WHERE std_Name LIKE 'F__%'


#Example 6 [find any name that start with 'f' & end with 'n']

SELECT std_Name FROM Student_Info
WHERE std_Name LIKE 'f%n'

# you can check more patterns from google
```

### SELECT NULL or NOT NULL Values
```SQL
SELECT std_Name, std_Cell FROM Student_Info
WHERE std_Cell IS NULL
```

```SQL
SELECT std_Name, std_Fees FROM Student_Fee
WHERE std_Fees IS NOT NULL
```

