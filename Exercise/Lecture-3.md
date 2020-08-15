# SQL CONSTRAINT
___

SQL constraints (Rules) are used to specify rules for the data in a table. Constraints enforce
rules on the data in a table whenever a row is inserted, deleted, or updated. Constraints can be
defined at the column or table level.

If there is any violation between the constraint and the data action, the action is aborted by
the constraint.

### In SQL we have following Constraint

1. NOT NULL
2. UNIQUE
3. CHECK
4. DEFAULT
5. PRIMARY KEY
6. FOREIGN KEY
7. INDEX
---

1. **NOT NULL** - The NOT NULL constraint enforces a column to **NOT** accept **NULL** values.
```SQL
CREATE TABLE Std_Info(
std_Id INT NOT NULL,
std_Name VARCHAR(20) NOT NULL,
std_Cell VARCHAR(15) NOT NULL,
std_City VARCHAR(20)
)
```

2. **UNIQUE** - The **UNIQUE** constraint ensures that the all values in a column are not same.
```SQL
CREATE TABLE Std_Info(
std_Id INT NOT NULL,
std_Name VARCHAR(20) NOT NULL,
std_Cell VARCHAR(15) NOT NULL UNIQUE,
std_City VARCHAR(20)
)
```


3. **CHECK** - The **CHECK** constraint is a column level condition, if the condition is true then value will be inserted in a column.
```SQL
CREATE TABLE Std_Info(
std_Id INT NOT NULL,
std_Name VARCHAR(20) NOT NULL,
std_Cell VARCHAR(15) NOT NULL UNIQUE,
std_City VARCHAR(20),
std_Age INT NOT NULL CHECK (std_Age>=18 AND std_Age<=35)
)
```

4. **DEFAULT** - The default value will be added to all new records IF no other value is defined.
```SQL
CREATE TABLE Std_Info(
std_Id INT NOT NULL,
std_Name VARCHAR(20) NOT NULL,
std_Cell VARCHAR(15) NOT NULL UNIQUE,
std_City VARCHAR(20) DEFAULT 'Lahore',
std_Age INT NOT NULL CHECK (std_Age>=18 AND std_Age<=35)
)
```

5. **PRIMARY KEY** - The **PRIMARY KEY** constraint is the combination of **NOT NULL** & **UNIQUE** constraint. The help of **PRIMARY KEY** constraint uniquely identifies each record in a table. A table can have only one **PRIMARY KEY**.
```SQL
CREATE TABLE Std_Info(
std_Id INT NOT NULL PRIMARY KEY,
std_Name VARCHAR(20) NOT NULL,
std_Cell VARCHAR(15) NOT NULL UNIQUE,
std_City VARCHAR(20) DEFAULT 'Lahore',
std_Age INT NOT NULL CHECK (std_Age>=18 AND std_Age<=35)
)
```

6. **FOREIGN KEY** - A **FOREIGN KEY** is a key used to link two tables together. A **FOREIGN KEY** is a column/field in one table that refers to the **PRIMARY KEY** in another table. A table can have multiple **FOREIGN KEY**s. The table containing the **FOREIGN KEY** is called **child** table & other table that contain the **RIMARY KEY** is called  **referenced/parent** table. The **FOREIGN KEY** & **PRIMARY KEY** have same data type.
```SQL
CREATE TABLE Std_Info(
std_Id INT NOT NULL PRIMARY KEY,
std_Name VARCHAR(20) NOT NULL,
std_Cell VARCHAR(15) NOT NULL UNIQUE,
std_City VARCHAR(20) DEFAULT 'Lahore',
std_Age INT NOT NULL CHECK (std_Age>=18 AND std_Age<=35)
)

# Create table that contain foreign key
CREATE TABLE Std_Address(
std_Address_Id INT PRIMARY KEY,
std_Address VARCHAR(50) NOT NULL,
std_FId INT FOREIGN KEY (std_FId) REFERENCES Std_Info(std_Id)
)
```

7. **INDEX** - Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.
```SQL
CREATE INDEX std_Name_Index #index name
ON Std_Info (std_Name);

# unique index like (username, email, phone number) that moslty used for searches.
CREATE UNIQUE INDEX std_Cell_Index
ON Std_Info (std_Cell)

# If you want to test the index in working or not then run this query
SELECT * FROM Std_Info WITH(INDEX(std_Cell_Index))
```

### Table Level Constraint
1. Created after defining the various column.
2. Can refer to more than one column (a constraint that comprises two columns together).
3. Allows creating several constraints on the same column.
```SQL
CREATE TABLE Std_Info(
std_Id INT,
std_First_Name VARCHAR(20) ,
std_Last-Name VARCHAR(20) ,
UNIQUE(std_First-Name, std_Last_Name), # this constraint is table level
CONSTRAINT PRIMARY KEY (std_Id) # and also this constraint is table level
)
```
