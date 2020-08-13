# SQL CREATE, ALTER, DROP, SHOW OR USE OF [DATABASE] & [TABLE] Excercise Using Query
___
## Database

#### Create Database
```SQL
CREATE DATABASE [STUDENTS]
```
#### Use Existing Database
```SQL
USE [STUDENTS]
```
#### Drop Database
```SQL
DROP DATABASE [STUDENTS]
```
#### Show list of available Database without including system database
```SQL
SELECT * FROM SYS.DATABASES
WHERE NAME NOT IN ('master','tempdb','model','msdb')
```
#### Alter Database
> This command works for SQL Server 2005, 2008, 2008R2, 2012, 2014, 2016 and 2017
```SQL
ALTER DATABASE [STUDENTS] MODIFY NAME = [STUDENTS_CHANGE]
```
> if the above command not work on your server then use this command
```SQL
EXEC sp_renamedb 'STUDENTS', 'STUDENTS_CHANGE'
```

## Table

#### Create Table
```SQL
CREATE TABLE Std_Info (
std_Roll_No INT PRIMARY KEY,
std_Name VARCHAR(40) NOT NULL ,
std_email VARCHAR(30) UNIQUE,
std_Cell_Number VARCHAR(13),
std_Program VARCHAR(20),
std_Semester INT,
std_Addresss VARCHAR(100)
)
```
#### Drop Table
```SQL
DROP TABLE [Std_Info]
```
#### Alter Table
> Alter Table Name

_"SQL Server does not have any statement that directly renames a table. However, it does provide you with a stored procedure named sp_rename that allows you to change the name of a table."_
```SQL
EXEC sp_rename 'Std_Info', 'Student_Info'
```
> Alter Table Column

**Add new column in table**
```SQL
ALTER TABLE Student_Info
ADD std_Blood_Group VARCHAR(2)
```
**Alter column name**
```SQL
EXEC sp_rename 'Student_Info.std_Blood_Group', 'std_BG', 'COLUMN';
```
**Alter column datatype**
```SQL
ALTER TABLE Student_Info
ALTER COLUMN std_BG CHAR(3);
```
**Drop column from table**
```SQL
ALTER TABLE Student_Info
DROP COLOUMN std_BG
```
