# Ex. No: 6 PL/SQL program using Cursor 
### DATE: 
### AIM: To create PL/SQL program to display the customer table 

### Steps:
1. Declare the variable  in Declare section.
2. Fetch the variable with datatype similar to data type in cursor 
3. Create a cursor to select all rows from customers table.
4. Display the result 
5. End the begin section.

### Program:

Developed By : M.CHANDRU
Register number: 212222230026

### Create employee table:
```python
CREATE TABLE employee(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10), salary NUMBER);
```
### Insert values into employee table:
```python
INSERT INTO employee VALUES(1,'Dileep','HR',600000);
INSERT INTO employee VALUES(2,'Anji','MD',950000);
INSERT INTO employee VALUES(3,'Jaggu','Finance',800000);
```
### SQL Cursor code:
```python
set serveroutput on
declare
cursor employee_cursor is
select empid, empname, dept, salary
from employee;
empid number;
empname varchar(90);
dept varchar(90);
salary number;
begin
open employee_cursor;
loop
fetch employee_cursor into empid,empname,dept,salary;
exit when employee_cursor%notfound;
dbms_output.put_line('Employee ID: '||empid);
dbms_output.put_line('Employee Name: '||empname);
dbms_output.put_line('Department: '||dept);
dbms_output.put_line('Salary: '||salary);
dbms_output.put_line('-x-x-x-x-x-x-x-x-x-x-x-x-x-');
end loop;
close employee_cursor;
end;
/
```
### Output:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/667887bc-4a7e-4ed1-bcb8-2542cf9ce756)
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/231eeed6-ed25-40c8-8356-5c9497e03a4a)

### Result:
Thust the program was performed sucessfully.
