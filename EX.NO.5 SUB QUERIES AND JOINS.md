# EX.NO.6 SubQueries, Views and Joins 
### DATE
## AIM:To use SubQueries, Views and Joins in SQL 
## Create employee Table
```sql
CREATE TABLE EMP (EMPNO NUMBER(4) PRIMARY KEY,ENAME VARCHAR2(10),JOB VARCHAR2(9),MGR NUMBER(4),HIREDATE DATE,SAL NUMBER(7,2),COMM NUMBER(7,2),DEPTNO NUMBER(2));
```
## Insert the values
```sql
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7369, 'SMITH', 'CLERK', 7902, '17-DEC-80', 800, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '20-FEB-81', 1600, 300, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7521, 'WARD', 'SALESMAN', 7698, '22-FEB-81', 1250, 500, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7566, 'JONES', 'MANAGER', 7839, '02-APR-81', 2975, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '28-SEP-81', 1250, 1400, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7698, 'BLAKE', 'MANAGER', 7839, '01-MAY-81', 2850, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7782, 'CLARK', 'MANAGER', 7839, '09-JUN-81', 2450, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7788, 'SCOTT', 'ANALYST', 7566, '19-APR-87', 3000, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500, 0, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7876, 'ADAMS', 'CLERK', 7788, '23-MAY-87', 1100, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7902, 'FORD', 'ANALYST', 7566, TO_DATE('03-DEC-81', 'DD-MON-RR'), 3000, 20, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7934, 'MILLER', 'CLERK', 7782, TO_DATE('23-JAN-82', 'DD-MON-RR'), 1300, 10, 10);
```

## Create department table
```sql
CREATE TABLE DEPT (DEPTNO NUMBER(2) PRIMARY KEY,DNAME VARCHAR2(14),LOC VARCHAR2(13));
```
## Insert the values in the department table
```sql
INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (10, 'ACCOUNTING', 'NEW YORK');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (20, 'RESEARCH', 'DALLAS');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (30, 'SALES', 'CHICAGO');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (40, 'OPERATIONS', 'BOSTON');
```

### Q1) List the name of the employees whose salary is greater than that of employee with empno 7566.
### QUERY:
```python
 SELECT ename FROM emp WHERE sal > (SELECT sal FROM emp WHERE empno = 7566);
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/e948e218-906f-4c37-866c-c3d7a9073d56)
### Q2) List the ename,job,sal of the employee who get minimum salary in the company.
### QUERY:
```python
SELECT ename,job,sal FROM emp WHERE sal = (SELECT MIN(sal) FROM emp);
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/c9dca84c-8072-4c6b-bc8a-199d6eb2bdc0)


### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.
### QUERY:
```python
 SELECT ename,job FROM emp WHERE deptno = 10 AND job IN (SELECT job FROM emp WHERE job = 'sales');
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/5f306407-d295-4bf4-bf1c-23cac38cc479)

### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.
### QUERY:
```python
CREATE VIEW empv5 as select EMPNO,ENAME,JOB from EMP where DEPTNO = 10;
SELECT * FROM empv5;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/9ac6789c-0e6f-4a4c-9bb7-a7eee35ffad5)

### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.
### QUERY:
```python
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/a6e4f8c8-b6df-4da8-9bdf-4e89ad24a50b)

```
### OUTPUT:
### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table
### QUERY:
```python
DROP view empv5;
UPDATE emp SET sal=sal+(sal*0.10) WHERE job='CLERK';
CREATE VIEW empv5 AS SELECT empno,ename,sal,job FROM emp WHERE deptno = 10;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/eb36516d-1e89-4c9f-b8b5-89990c49f406)

## Create a Customer1 Table
```sql
CREATE TABLE Customer1 (customer_id INT,cust_name VARCHAR(20),city VARCHAR(20),grade INT,salesman_id INT);
```
## Inserting Values to the Table
```sql
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3002, 'Nick Rimando', 'New York', 100, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3007, 'Brad Davis', 'New York', 200, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3005, 'Graham Zusi', 'California', 200, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3008, 'Julian Green', 'London', 300, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3004, 'Fabian Johnson', 'Paris', 300, 5006);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3009, 'Geoff Cameron', 'Berlin', 100, 5003);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3003, 'Jozy Altidor', 'Moscow', 200, 5007);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3001, 'Brad Guzan', 'London', NULL, 5005);
```
## Create a Salesperson1 table
```sql
CREATE TABLE Salesman1 (salesman_id INT,name VARCHAR(20),city VARCHAR(20),commission DECIMAL(4,2));
```
## Inserting Values to the Table
```sql
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5001, 'James Hoog', 'New York', 0.15);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5002, 'Nail Knite', 'Paris', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5005, 'Pit Alex', 'London', 0.11);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5006, 'Mc Lyon', 'Paris', 0.14);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5007, 'Paul Adam', 'Rome', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5003, 'Lauson Hen', 'San Jose', 0.12);
```
### Q7) Write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.
### QUERY:
```python
 SELECT s.name AS "Salesman", c.cust_name, s.city FROM Salesman1 s, Customer1 c WHERE s.city=c.city;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/7d5bacf4-49d4-420b-be03-e419635f18a9)

### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.
### QUERY:
```python
SELECT c.cust_name AS "Customer name", c.city AS "Customer city", s.name AS "Salesman", s.commission FROM Salesman1 s INNER JOIN Customer1 c ON s.city=c.city WHERE s.commission > 0.13;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/0108895e-16a6-48fc-bd35-d8ad08ed924f)

### Q9) Perform Natural join on both tables
### QUERY:
```python
SELECT * FROM Salesman1 s NATURAL JOIN Customer1 c;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/6500de9c-b24f-44b0-bbe6-df505656df86)

### Q10) Perform Left and right join on both tables
### QUERY:
```python
SELECT s.salesman_id,s.name,s.city,s.commission,c.cust_name,c.grade FROM Salesman1 s LEFT JOIN Customer1 c ON s.salesman_id=c.salesman_id;

SELECT s.salesman_id,s.name,s.city,s.commission,c.cust_name,c.grade FROM Salesman1 s RIGHT JOIN Customer1 c ON s.salesman_id=c.salesman_id;
```
### OUTPUT:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/51ec4d32-fe45-415e-a288-5ff371915729)
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/53496da8-fe63-464a-a95c-9d507e73d510)

## RESULT 
### Thus the basics of subqueries,views,joins are performed in SQL.
