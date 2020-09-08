# SQL Clone Table & Combine Table
___

The `INSERT INTO SELECT` command clone or copies data from one table and inserts it into another table.

**The Number of columns and data types must be same.**

> create new table with the name of new_Student_info

### INSERT INTO SELECT
```
-- Syntax Example
INSERT INTO new_table_name (column_1, column_2, column_3)
SELECT * FROM existing_table
```
```SQL
-- Example 1
INSERT INTO new_Student_Info
SELECT * FROM student_Info

-- Example 2
INSERT INTO new_Student_Info (new_std_id, new_std_name, new_std_age)
SELECT std_id, std_name, std_age FROM student_Info

-- Example 3
-- Combine data from two table and save into one table
INSERT INTO new_Student_Info (new_std_id, new_std_name, new_std_marks)
SELECT SI.std_id, SI.std_name, SM.std_Marks
FROM student_Info AS SI JOIN student_Marks AS SM
ON SI.std_id = SM.std_id
```

### SQL UNION
1. Number of columns are same
2. Column must have same data type
3. The columns in each `SELECT` statement must also be in the same order

Example
```
-- UNION Example
firts_table (1, "Farhan",23), (2,"Shami", 25), (4, "saud", 21), (5, arslan, 19)
UNION
second_table (1, "Farhan",23), (2,"Shami", 25), (3, "saud", 34), (6, nauman, 12)

-- UNION Example Answer
output_table (1, "Farhan",23), (2,"Shami", 25), (4, "saud", 21), (5, arslan, 19), (3, "saud", 34), (6, nauman, 12)

-- UNION ALL Example Answer
output_table (1, "Farhan",23), (2,"Shami", 25), (4, "saud", 21), (5, arslan, 19), (1, "Farhan",23), (2,"Shami", 25), (3, "saud", 34), (6, nauman, 12)
```

```SQL
-- combine two table and remove duplicate record[s]
SELECT * FROM First_Table
UNION
SELECT * FROM Second_Table

-- combine two tables and accept duplicate record[s]
SELECT * FROM First_Table
UNION ALL
SELECT * FROM Second_Table
```

### SQL INTERSECT
`INTERSECT` clause return only matched record[s].
Example
```
-- INTERSECTON Example
firts_table (1, "Farhan",23), (2,"Shami", 25), (4, "saud", 21), (5, arslan, 19)
INTERSECT
second_table (1, "Farhan",23), (2,"Shami", 25), (3, "saud", 34), (6, nauman, 12)

output_table (1, "Farhan",23), (2,"Shami", 25)
```
```SQL
-- combine two table and return only first table record that matched with second table
SELECT * FROM First_Table
INTERSECT
SELECT * FROM Second_Table
```

### SQL EXCEPT
`EXCEPT` returns only rows, which are not available in the second `SELECT` statement.
Example
```
-- EXCEPT Example
firts_table (1, "Farhan",23), (2,"Shami", 25), (4, "saud", 21), (5, arslan, 19)
EXCEPT
second_table (1, "Farhan",23), (2,"Shami", 25), (3, "saud", 34), (6, nauman, 12)

output_table (4, "saud", 21), (5, arslan, 19)
```
```SQL
SELECT * FROM First_Table
EXCEPT
SELECT * FROM Second_Table
```
