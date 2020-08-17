# SQL DATA MANIPULATION LANGUAGE (DML)
---

A data manipulation language (DML) is a query language used for adding (inserting), deleting, and modifying (updating) data in a database.

DML most common statment consists of the following
1. **SELECT** - to display or retrieve data from table[s]
1. **INSERT** - to insert or add data into table[s]
1. **UPDATE** - to update existing inserted data
1. **DELETE** - to delete data from table[s]

### SELECT Quries
```SQL
# display all data from all coloumns
SELECT * from Std_Info;

# display all data from selected columns
SELECT std_Id, std_Name, std_Cell from Std_info

# display selected data with where clause
SELECT * from Std_Info
WHERE std_Id = 1

#in next lexture we learn retrieve data with condition or where clause
```

### INSERT Quries
```SQL
# insert in selected column (must check the column contraint, like not null, unique, check etc)
INSERT INTO Std_Info (std_id, std_Name, std_Cell) VALUES (1, "Farhan Ellahi", "+923054860000")

# insert in all column without selecting the column names (make sure the order of the values is in the same order as the columns in the table.)
INSERT INTO Std_Info VALUES (2, "John Doe", "+18556323131", "johndoe@example.com", "Lahore")
```

### UPDATE Quries
```SQL
# select column where you want to update values
UPDATE Std_Info
SET std_Name = "John Doee", std_Cell = "+1954699999"
WHERE std_Id = 2

# update multiple column
UPDATE Std_Info
SET std_Email = "example@lahore.com"
WHERE std_Address = "Lahore"

# (update warning!) if you not use where clause then all record will be update
```

### DELETE Quries
```SQL
#delete selected record
DELETE FROM Std_Info
WHERE std_Id = 1

# delete multiple record
DELETE FROM Std_Info
WHERE std_Address = "Lahore"

# delete all record from table
DELETE FROM Std_Info
```
