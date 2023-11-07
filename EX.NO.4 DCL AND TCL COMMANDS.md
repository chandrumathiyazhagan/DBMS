# EX.NO 4 Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL
### DATE:
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names

### Q1) Create a table employee with employee id ,name and Address
### QUERY:
```python
 CREATE TABLE employee (employee_id INT PRIMARY KEY,name VARCHAR(50),address VARCHAR(100));
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/6c171012-85eb-4b32-8172-b7c0247e7bbc)
### Q2) Insert three rows into emploee table 
### QUERY:
```python
 INSERT INTO employee (employee_id, name, address)VALUES (1, 'John Doe', '123 Main St');
 INSERT INTO employee (employee_id, name, address)VALUES (2, 'Jane Smith', '456 Elm St');
 INSERT INTO employee (employee_id, name, address)VALUES (3, 'Alice Johnson', '789 Oak St');
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/c73b414d-787c-4d98-a6e2-730d0eed9dc1)
### Q3) Start the transaction and create a save point s1.
### QUERY:
```python
 START TRANSACTION;
SAVEPOINT s1;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/7715421c-5f61-42f3-84b6-0a435751f06d)
### Q4) Perform insertion into employee table.
### QUERY:
```python
INSERT INTO employee (employee_id, name, address)VALUES(4, 'Bob Williams', '101 Pine St');
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/2c5ed06d-3000-4b05-adb2-882132d4affd)
### Q5)	Display the employee table and create a save point s2 .
### QUERY:
```python
 SELECT * FROM employee;
 SAVEPOINT s2;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/d225854b-78d3-42e4-8e27-24f0e71e2cc8)
### Q6)	Perform updation on any one of the row.
### QUERY:
```python
 UPDATE employee SET address = 'New Address'WHERE employee_id = 1;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/db8220bc-2443-40ff-b926-caeed3919a94)
### Q7) Display the employee table and rollback to  save point s2 
### QUERY:
```python
SELECT * FROM employee;
ROLLBACK TO s2;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/422b3a7e-7d16-4c3f-aa6a-5bad143c1ba0)
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/f3bf3dc5-e4bb-447a-8bbd-02b819633db4)
### Q8) Display the employee table and commit the changes; 
### QUERY:
```python
SELECT * FROM employee;
COMMIT;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/a6c6b3b5-722e-4f9f-a6f1-852cd54f5ff7)
### Q9) Rollback to save point s1;
### QUERY:
```python
ROLLBACK TO s1;
```
### Q10)	Create a new user and grant access to any one database with "insert and update"
### QUERY:
```python
 CREATE USER new_user IDENTIFIED BY 'password';
 GRANT INSERT, UPDATE ON your_database.employee TO new_user;
```
### Q11) Check the user access and display the result 
### QUERY:
```python
SHOW GRANTS FOR new_user;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/adeeb4c6-03a0-4a21-9620-a00a479a00ad)
### Q12) Revoke the privillages.
### QUERY:
```python
 REVOKE INSERT, UPDATE ON your_database.employee FROM new_user;
```
## RESULT :
Thus the basic TCL and DCL commands are executed.
