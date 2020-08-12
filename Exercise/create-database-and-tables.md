# SQL [DATABASE] & [TABLE] Excercise Using Query
___

## Example 1
#### Create Database
```SQL
CREATE DATABASE [STUDENTS]
```
#### Create Database Table
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

## Example 2

#### Create Database
```SQL
CREATE DATABASE [Employee]
```
#### Create Database Tables
```SQL
CREATE TABLE Employee (
emp_id INT PRIMARY KEY,
emp_name VARCHAR(30),
emp_email VARCHAR(30),
emp_street VARCHAR(60),
emp_city VARCHAR(30)
)
```
