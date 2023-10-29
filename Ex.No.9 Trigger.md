# Ex. No: 6 PL/SQL program using Triggers 
### DATE: 
### AIM: To create PL/SQL program to display new and old salary of customer when before/ after updation takes place. 

### Steps:
1. Create a trigger for each row when updation occurs.
2. Declare the variable in Declare section.
3. Start the begin section.
4. Calculate the salary changes.
5. Display the result 
6. End the begin section.

### Program:
```
Developed By: M.CHANDRU
Register number: 212222230026
```
## Create employee table:
```python
create table EMPLOYEE1(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
```
## Insert values into employee table:
```python
insert into EMPLOYEE1(empid,empname,dept,salary) values(1,'Chandru','HR',2500000);
insert into EMPLOYEE1(empid,empname,dept,salary) values(2,'Chethan','MD',950000);
insert into EMPLOYEE1(empid,empname,dept,salary) values(3,'Dileep','HR',800000);
```
## Create salary_log table
```python
create table salary_log (log_id NUMBER , empid NUMBER,empname VARCHAR(10),old_salary NUMBER,new_salary NUMBER,update_date DATE);
```
## PLSQL Trigger code
```python
create or replace trigger log_salary_update
  2      before update on EMPLOYEE1
  3      for each row
  4      declare
  5      v_old_salary number;
  6      v_new_salary number;
  7      begin
  8      v_old_salary := :OLD.salary;
  9      v_new_salary := :NEW.salary;
 10      if v_old_salary <> v_new_salary then
 11      insert into salary_log(empid,empname,old_salary,new_salary,update_date)values(:OLD.empid,:OLD.empname,v_old_salary,v_new_salary,SYSDATE);
 12      end if;
 13      end;
 14      /
```
## Update the salary of an employee:
```python
update EMPLOYEE1 set salary = 97000 where empid = 2;
```
## Display the salary_log table:
```python
select * from salary_log;
```
### Output:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/111a0906-e5e0-42e7-82b2-c06501aea99e)
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/797beef0-8c53-4381-9913-793a49fb89ad)

### Result:
Thust the program was performed sucessfully.
