# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```python
UPDATE manager SET SALARY = SALARY + (SALARY *10/100);
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/5fd4156b-a2e4-4577-b0db-d2c5abb7e130)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```python
delete from manager where salary<2750;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/aba217e5-a661-46a3-a09f-f784b27912dc)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```python
select ename as "Name",salary*12 as "Annual Salary" from manager;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/84a8a171-68f3-462f-ba4d-e60e1acce2ce)

### Q4)	List the names of Clerks from emp table.

### QUERY:
```python
select ename from manager where designation='clerk';
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/624417c4-ea00-40d2-8386-42f98ed37244)

### Q5)	List the names of employee who are not Managers.

### QUERY:
```python
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/51fc217e-8c8d-4ff3-9c4d-a23801573bd6)

### Q6)	List the names of employees not eligible for commission.

### QUERY:
```python
select ename from manager where commission=0;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/7939139b-9497-4db2-a13b-b8e7f9311810)

### Q7)	List employees whose name either start or end with ‘s’.

### QUERY:
```python
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/bae5f2fd-2c22-443d-84cc-d714484ba4cb)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```python
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/321b4c16-7e82-4ebb-a056-f80677533afd)

### Q9) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
```python
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/93d4fb7d-162d-4de3-916f-6bb5d0da7ae1)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/29a7e879-6344-4304-8628-316728ffcd54)

### Q11) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```python
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/2c21dd24-ccae-45d5-a3db-225b6a361de9)

### Q12) Find number of rows in the table EMP

### QUERY:
```python
select count(*) from manager;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/cbed0117-b3b2-413f-a574-711bf7cde91a)

### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
```python
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/1f7d2549-a00e-4474-b40e-57f87022741f)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```python
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/053c97fe-ed05-4807-978b-6056066d71e0)

## RESULT :
Thus the basic DML commands are executed.
