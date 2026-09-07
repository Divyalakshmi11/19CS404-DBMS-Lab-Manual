# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.
Program :
  <img width="782" height="285" alt="Screenshot 2026-09-07 080636" src="https://github.com/user-attachments/assets/891fc522-45ce-448c-8f5c-02505cd4becc" />


**Expected Output:**  
Greater number is: 80
<img width="1016" height="740" alt="image" src="https://github.com/user-attachments/assets/699d82fc-2d83-4933-b76e-3b6ca768258c" />


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

Program :

  <img width="907" height="320" alt="Screenshot 2026-09-07 080645" src="https://github.com/user-attachments/assets/1c0f8fa9-c75d-48a0-bd8a-41f578fe52a0" />


**Expected Output:**  
Sum of first 10 natural numbers is: 55
<img width="994" height="724" alt="image" src="https://github.com/user-attachments/assets/09acfb8c-04c5-4546-8b51-341648d8d3b8" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

Program :
  <img width="807" height="477" alt="Screenshot 2026-09-07 080653" src="https://github.com/user-attachments/assets/56637124-36d8-4e8e-b7bf-c44ed4d7c2da" />


**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8
<img width="996" height="725" alt="image" src="https://github.com/user-attachments/assets/0cd10036-9959-45d5-83d5-e78743d2e9c8" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
Program :
  <img width="891" height="353" alt="Screenshot 2026-09-07 080707" src="https://github.com/user-attachments/assets/348a5256-8c70-4676-a2a0-2eaa2f820fbd" />


**Expected Output:**  
n = 1535  
Reversed number is 5351
<img width="1004" height="732" alt="image" src="https://github.com/user-attachments/assets/ff6e507f-a0ca-4bae-ab62-d26081392deb" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

Program :
 <img width="902" height="468" alt="Screenshot 2026-09-07 080715" src="https://github.com/user-attachments/assets/c0bbc8c5-d93d-4747-982a-f217ed5a4476" />

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15
<img width="989" height="712" alt="image" src="https://github.com/user-attachments/assets/653b78e9-b894-48e3-be0a-bb3d8d5d767d" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
