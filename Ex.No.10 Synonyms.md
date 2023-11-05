# EXP NO 10: SYNONYMS AND ASSERTIONS IN SQL 
### DATE: 
## AIM:
To create a student database and create a synonym and assertions.

## THEORY
## SYNONYM
<div align="justify">
A SYNONYM provides another name for database object, referred to as original object, that may exist on a local or another server.
</div>
## ASSERTIONS
<div align="justify">
* An assertion is a piece of SQL which makes sure a condition is satisfied, else or it stops the action being taken on a database.
* An assertion is a constraint that might be dependent upon multiple rows of multiple tables.
</div>

## Query:
### 1) Create a table EMPLOYEE and perform insertion of two rows.
### SQL QUERY: 
```python
 CREATE TABLE EMPLOYEE (EmployeeID NUMBER,FirstName VARCHAR2(50),LastName VARCHAR2(50),Salary NUMBER);
```
```python
INSERT INTO EMPLOYEE (EmployeeID, FirstName, LastName, Salary)VALUES (1, 'leo', 'Doe', 50000);
INSERT INTO EMPLOYEE (EmployeeID, FirstName, LastName, Salary)VALUES (2, 'chandru', 'Smith', 60000);
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/cb3b18c1-3f4d-4e96-a2ac-5de8b8e469d3)
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/482e4495-0f06-4aa4-bcbc-a4944faaa094)

### 2) Create a synonym S1 for EMPLOYEE  table.
### SQL QUERY: 
```python
 CREATE SYNONYM S1 FOR EMPLOYEE;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/ff4d0a11-9243-4f33-a71d-ce34d5c5220a)

### 3) Display the EMPLOYEE  table using synonym S1.
### SQL QUERY: 
```python
SELECT * FROM S1;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/1110955c-56d7-412f-a543-b15c2d314c61)

### 4) Drop the synonym.
### SQL QUERY: 
```python
DROP SYNONYM S1;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/46f7aab0-ed1d-4659-8fb4-f9870037f4a6)

### 5) Create a supplier table and create a sequence S2 for supplier table id.
### SQL QUERY: 
```python
CREATE TABLE Supplier (SupplierID NUMBER,SupplierName VARCHAR2(50));
CREATE SEQUENCE S2 START WITH 1  INCREMENT BY 1 NOCACHE NOCYCLE;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/e6bb0bb0-bf68-42b6-a368-1f94ebb1acee)

### 6) insert the data into supplier table use sequence.
### SQL QUERY: 
```python
INSERT INTO Supplier (SupplierID, SupplierName)VALUES (S2.NEXTVAL, 'ABC Supplier');
INSERT INTO Supplier (SupplierID, SupplierName)VALUES (S2.NEXTVAL, 'XYZ Supplier');
```
```python
SELECT * FROM Supplier;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/987d5e7d-7bb0-4f5e-a643-ec8c74b0837c)
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/5309ba2c-8ccd-43fa-83f0-e6695e36a744)


### 7) Drop the sequence
### SQL QUERY: 
```python
DROP SEQUENCE S2;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/5d59dfbf-e10c-48bd-9447-9e327b800510)

## RESULT :
### Thus the sequence and synonym created and used in SQL.
