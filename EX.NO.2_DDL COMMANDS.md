# EXP NO 2: DATA DEFINITION LANGUGE COMMANDS 
### DATE
## AIM:
To create a student database and execute DDL queries using SQL.


## THEORY
### DDL (Data Definition Language)

* DDL or Data Definition Language actually consists of the SQL commands that can be used to define the database schema.
* It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database.
* DDL is a set of SQL commands used to create, modify, and delete database structures but not data.
* These commands are normally not used by a general user, who should be accessing the database via an application.

 
### List of DDL commands: 
1. CREATE: This command is used to create the database or its objects (like table, index, function, views, store procedure, and triggers).
2. DROP: This command is used to delete objects from the database.
3. ALTER: This is used to alter the structure of the database.
4. TRUNCATE: This is used to remove all records from a table, including all spaces allocated for the records are removed.
5. RENAME: This is used to rename an object existing in the database.

## Query:

Developed by:M.CHANDRU

Register No: 212222230026

### 1) Create a database 

### SQL QUERY:
```python
use chandrumk
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/33a2f6cf-297a-4794-8bc5-6b35d5d839e7)

### 2) Create a table student  and insert any two rows with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY: 
```python
create table STUDENT(S_Roll_no int,S_Name char(20),S_Age int,S_Address char(30),S_Phone_no int);
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/546b7d10-2f3d-458c-93e1-263c178605ac)

### 3) Alter the above student table by adding another attribute department

### SQL QUERY: 
```python
alter table STUDENT add S_Dept char(10);
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/7a6f43c2-7722-4ccc-9c50-187dec02d321)

### 4) Rename the student table to mystudent

### SQL QUERY: 
```python
rename table STUDENT to MYSTUDENT;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/4caaee67-1fe4-4a30-acfe-0fff0dd693ab)

### 5) Delete the mystudent rows using truncate keyword

### SQL QUERY: 
```python
 truncate table STUDENT;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/34efe174-772c-4be9-80f5-3b82a131252e)

### 6) Drop the mystudent table
 
### SQL QUERY: 
```python
 drop table MYSTUDENT;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/07813b5d-909c-424f-94fc-769b28adebfd)

## Result:
         Thus the basic DDL commands in SQL are executed. 
