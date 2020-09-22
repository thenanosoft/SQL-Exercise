# Procedure in SQL | Stored Procedures
____

Stored Procedure in SQL Server can be defined as the set of logical group of SQL statements which are grouped to perform a specific task.


## Procedure Creation

### Create Insert Record Procedure

```SQL
CREATE PROCEDURE Insert_Data
  @rollno Varchar(20), @name varchar(15), @email varchar(35), @age int
AS
  INSERT INTO Std_Info (std_Roll_No, std_Name, std_Email, std_Age) VALUES (@rollno, @name, @email, @age)
END
```

### Create Delete Record Procedure

```SQL
CREATE PROCEDURE Delete_Data
  @rollno Varchar(20)
AS
  DELETE FROM Std_Info WHERE std_Roll_No = @rollno
END
```

## Proceudre Execution

There are two ways to execute sql proceudre

1. With Varibale
1. Without Variable
  
### Execute Insert Data Procedure
```SQL
-- 1] Procedure Run Command (assign value with varibale)
EXEC Insert_Data @rollno = "CS181070", @name = "Farhan Ellahi", @age = 23, @email = "farhan@gmail.com"

-- 2] Procedure Run Command (assign value without varibale) 
EXEC Insert_Data "CS181070", "Farhan Ellahi", "farhan@gmail.com", 23
```

### Execute Delete Data Procedure

```SQL
-- Procedure Run Command (assign value without varibale) 
EXEC Delete_Data "CS181070"
```
