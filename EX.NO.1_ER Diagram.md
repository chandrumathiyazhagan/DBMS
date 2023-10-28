# EXP NO 1: ER DIAGRAM CREATION, RELATIONAL MODEL AND SCHEMA GENERATION  
### DATE
## AIM:
<div align="justify">
   To create a ER Diagram for Bank management system or College management system using ERD Plus tool and generate the relational model with schema. 
</div>

## Algorithm
1. Create a login with https://erdplus.com.
2. Create a new ER Diagram with name
3. Create a strong entity, relation and attributes.
4. Create a weak entity, relation and attributes.
5. Specify attributes unique, multivalued and composite attributes.

### ER Diagram 
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/eb3eabf1-69c0-4694-a84a-e8ecc0adb866)

### Relational model
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/031cef92-216a-4e97-a6a8-584d5604c0f5)

### SQL DDL Schema 
```
Developed by:M.CHANDRU
Register No: 212222230026
```
```
CREATE TABLE bank
(
  code INT NOT NULL,
  Name INT NOT NULL,
  addr INT NOT NULL,
  PRIMARY KEY (code)
);

CREATE TABLE BANK_BRANCHES
(
  Addr INT NOT NULL,
  Branch_no INT NOT NULL,
  PRIMARY KEY (Branch_no)
);

CREATE TABLE ACCOUNT
(
  Acct_no INT NOT NULL,
  Balance INT NOT NULL,
  Type INT NOT NULL,
  PRIMARY KEY (Acct_no)
);

CREATE TABLE CUSTOMER
(
  Name INT NOT NULL,
  Ssn INT NOT NULL,
  phone INT NOT NULL,
  Addr INT NOT NULL,
  PRIMARY KEY (Ssn)
);

CREATE TABLE LOAN
(
  Loan_no INT NOT NULL,
  Amount INT NOT NULL,
  type INT NOT NULL,
  PRIMARY KEY (Loan_no)
);
```
## RESULT 
<div align="justify">
Thus the ER diagram was drawn and relational diagram, SQL DDL staements are generated using ERD plus tool.
</div>
