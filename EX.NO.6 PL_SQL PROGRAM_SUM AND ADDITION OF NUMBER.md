# Ex. No: 6 PL/SQL program to perform addition and subtraction of two number 
### DATE: 
### AIM: To create PL/SQL program to perform addition and subtraction of two number.

### Steps:
1. Declare the variable a, b and necessary variables in Declare section.
2. Perform addition of two numbers
3. Perform subtraction of two numbers 
4. Display the result 
5. End the begin section.

### Program:
```python
DECLARE
  num1 NUMBER := 10; -- Replace 10 with the first number you want to use
  num2 NUMBER := 5;  -- Replace 5 with the second number you want to use
  sum_result NUMBER;
  difference_result NUMBER;
BEGIN
  -- Addition
  sum_result := num1 + num2;

  -- Subtraction
  difference_result := num1 - num2;

  -- Display the results
  DBMS_OUTPUT.PUT_LINE('The Addition of ' || num1 || ' and ' || num2 || ' is ' || sum_result);
  DBMS_OUTPUT.PUT_LINE('The Subraction between ' || num1 || ' and ' || num2 || ' is ' || difference_result);
END;
/
```
### Output:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/bf89b14c-2038-4863-b867-e6cad508d95d)

### Result:
Thust the program was performed sucessfully.
