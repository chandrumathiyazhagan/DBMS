# Ex. No: 6 PL/SQL program -BIGGEST OF THREE NUMBERS  
### DATE: 
### AIM: To create PL/SQL program to find biggest of three numbers.

### ALGORITHM:
1. Declare the variable a, b, c and assign value in Declare section.
2. begin the section
3. Find biggest of three numbers 
4. 5. Display the result 
6. End the begin section.

### Program:
```python
--To find the Biggest number
-- among given three numbers
DECLARE
	--a assigning with 10
	a NUMBER := 10;
	--b assigning with 7
	b NUMBER := 7;
	--c assigning with 18
	c NUMBER := 18;
BEGIN
	--block start
	--If condition start
	IF a > b
	AND a > c THEN
	--if a is Bigger then print a
	dbms_output.Put_line('Biggest number is '
						||a);
	ELSIF b > a
		AND b > c THEN
	--if b is Bigger then print b
	dbms_output.Put_line('Biggest number is '
						||b);
	ELSE
	--if c is Bigger then print c
	dbms_output.Put_line('Biggest number is '
						||c);
	END IF;
--end if condition
END;
--End program
```
### Output:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/040f0d71-be51-4843-8166-94a8b7ebfae9)

### Result:
Thust the program was performed sucessfully.
