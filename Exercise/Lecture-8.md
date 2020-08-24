# SQL Aggregate Functions
---

SQL Aggregate functions operate on single column of a table and return a single value. 

## Aggregate Functions
1. COUNT
1. SUM
1. AVG
1. MIN
1. MAX

### SQL Count Function
counts how many rows are in a particular colum
```SQL
SELECT COUNT(std_Id) FROM Student_Info 
```

### SQL SUM Function
adds all the values in a particular column
```SQL
SELECT SUM(std_fee) FROM Student_Fees 
```

### SQL AVG Function
calculates the average of a group of selected values.
```SQL
SELET AVG(std_fee) FROM Student_Fees
WHERE std_fee IS NOT NULL
```

### SQL MIN Function
find the minimum value from selected column
```SQL
SELECT MIN(std_Age) FROM Student_Info
```

### SQL MAX Function
find the maximum value from selected column
```SQL
SELECT MAX(std_Age) FROM Student_Info
```
