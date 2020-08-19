# SQL Advance Level SELECT Statement

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


**2. Arithmetic Operators**

|Operator|Discription|
|-|-|
|ALL|TRUE if all of the subquery values meet the condition|
|ANY|TRUE if any of the subquery values meet the condition|
|AND|TRUE if all conditions is TRUE that separated by AND|
|NOT|Display record if the condition is False|
|OR|True if any condition is TRUE that are separated by OR|
|IN|TRUE if record match one of a list of expression|
|BETWEEN|TRUE if record is within the range of expressions|
|EXISTS|TRUE if subquery is return one or more record|
|LIKE|True if record match the pattern|
