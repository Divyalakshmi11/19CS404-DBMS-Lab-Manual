# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.
PROGRAM :
<img width="847" height="306" alt="Screenshot 2026-09-07 055524" src="https://github.com/user-attachments/assets/b3c5b20b-8b50-421a-a0d9-39bdee39a112" />

**Expected Output:**  
Square of 6 is 36
<img width="1412" height="734" alt="image" src="https://github.com/user-attachments/assets/065749bf-6894-4ded-adcb-2674e2ca41ff" />

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.
PROGRAM :
<img width="910" height="417" alt="Screenshot 2026-09-07 055535" src="https://github.com/user-attachments/assets/ae01358a-603d-4dab-92a3-4dcd7470b376" />

**Expected Output:**  
Factorial of 5 is 120
<img width="1409" height="735" alt="image" src="https://github.com/user-attachments/assets/08b8dfa5-3860-4e7f-a2ed-537977c401e8" />

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.
PROGRAM :
<img width="867" height="336" alt="Screenshot 2026-09-07 055543" src="https://github.com/user-attachments/assets/683aa1a2-d688-4f24-bb75-60c5b058da2b" />

**Expected Output:**  
12 is Even
<img width="1394" height="793" alt="image" src="https://github.com/user-attachments/assets/b003612c-d0ca-4091-b390-a1d966f27973" />

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.
PROGRAM :
<img width="823" height="471" alt="Screenshot 2026-09-07 055630" src="https://github.com/user-attachments/assets/5af7bac0-36c5-4a73-a460-b719816ef6a5" />

**Expected Output:**  
Reversed number of 1234 is 4321
<img width="1396" height="741" alt="image" src="https://github.com/user-attachments/assets/6b6144c7-2c8d-40b4-ba05-df543331c52d" />

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.
PROGRAM :
<img width="842" height="316" alt="Screenshot 2026-09-07 055639" src="https://github.com/user-attachments/assets/5697d075-1f7a-49be-84e8-0277969f3596" />

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50
<img width="1395" height="730" alt="image" src="https://github.com/user-attachments/assets/af81d735-cc5d-4732-9f34-a49d23ba3f1b" />

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
