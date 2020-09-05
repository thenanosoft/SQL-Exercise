SQL Joins
___

A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

Different types of SQL Joins
1. INNER JOIN
1. OUTER JOIN
   1. LEFT JOIN
   1. RIGHT JOIN
   1. FULL JOIN

### INNER JOIN
Take a look at the following diagram in order to understand visually.

<img src="https://imgur.com/iybzvO8.png"  width="500" height="500">

Retrieve only matching records with respect to columns

```SQL
-- AS is a keyword, use to create Aliases
-- SI and SC are the aliases for the table

SELECT SI.std_Roll_No, SI.std_Name, SC.Crs_Name
FROM Student_Info AS SI
INNER JOIN Student_Course AS SC
ON SI.crs_ID = SC.crs_Id
```

### OUTER JOIN
#### LEFT JOIN

<img src="https://imgur.com/wnjoFBC.png" width="500" height="500">

**LEFT JOIN** retrieve all matching records from both tables and also retrieve all remaining record only from left table.

```SQL
SELECT SI.std_Roll_No, SI.std_Name, SC.Crs_Name
FROM Student_Info AS SI
LEFT JOIN Student_Course AS SC
ON SI.crs_ID = SC.crs_Id
```

#### RIGHT JOIN

<img src="https://imgur.com/DX3XSCz.png" width="500" height="500">

**RIGHT JOIN** retrieve all matching records from both tables and also retrieve all remaining record only from right table.

```SQL
SELECT SI.std_Roll_No, SI.std_Name, SC.Crs_Name
FROM Student_Info AS SI
RIGHT JOIN Student_Course AS SC
ON SI.crs_ID = SC.crs_Id
```

#### FULL JOIN

<img src="https://imgur.com/t5r9c0t.png" width="500" height="500">

**FULL JOIN** combine result of both **LEFT JOIN** and **RIGHT JOIN**.

`Note` <code>FULL JOIN</code> and <code>FULL OUTER JOIN</code> both are same.

```SQL
SELECT SI.std_Roll_No, SI.std_Name, SC.Crs_Name
FROM Student_Info AS SI
FULL JOIN Student_Course AS SC
ON SI.crs_ID = SC.crs_Id 
```
