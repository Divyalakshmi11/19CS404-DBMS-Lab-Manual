# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
Write the SQL query that achieves the selection of all columns from the "salesman" table (aliased as "s"), with a left join on the "salesman_id" column and a condition filtering for customers with the name 'Fabian Johns'.

sql
Answer: SELECT s.* FROM salesman s LEFT JOIN customer c ON s.salesman_id = c.salesman_id WHERE c.cust_name = 'Fabian Johns';

**Output:**
<img width="583" height="359" alt="image" src="https://github.com/user-attachments/assets/5a408545-c6f9-4548-b2f4-7b7db8ff1a21" />

**Question 2**
From the following tables write a SQL query to locate those salespeople who do not live in the same city where their customers live and have received a commission of more than 12% from the company. Return Customer Name, customer city, Salesman, salesman city, commission. 
Sample table: customer
<img width="578" height="261" alt="image" src="https://github.com/user-attachments/assets/492f5732-8616-430a-9f55-af161b492c1d" />
Sample table: salesman
<img width="441" height="233" alt="image" src="https://github.com/user-attachments/assets/64a2ad5a-ad69-4664-82d9-ed9dc278e42e" />

sql
Answer:

SELECT c.cust_name AS "Customer Name", c.city AS "city", s.name AS "Salesman", s.city AS "city", s.commission FROM customer c JOIN salesman s ON c.salesman_id = s.salesman_id WHERE c.city <> s.city AND s.commission > 0.12;


**Output:**
<img width="534" height="452" alt="image" src="https://github.com/user-attachments/assets/ce74cc79-bca1-45e3-8de2-21f2ed74ff04" />


**Question 3**
Write the SQL query that achieves the selection of the "cust_name" column from the "customer" table (aliased as "c"), and the "ord_no," "ord_date," and "purch_amt" columns from the "orders" table (aliased as "o"), with a left join on the "customer_id" column.

sql
Answer: SELECT c.cust_name, o.ord_no, o.ord_date, o.purch_amt FROM customer c LEFT JOIN orders o ON c.customer_id = o.customer_id;


**Output:**
<img width="649" height="603" alt="image" src="https://github.com/user-attachments/assets/189c5941-5047-45e7-8102-2fd86f283fcd" />


**Question 4**
Write the SQL query that accomplishes the selection of all columns from the "patients" table and the first name of doctors from the "doctors" table, with an inner join on the "doctor_id" column. 
PATIENTS TABLE:
<img width="271" height="232" alt="image" src="https://github.com/user-attachments/assets/d323afca-7a71-40cd-bdc5-d5e84a5cfe33" />
DOCTORS TABLE:
<img width="292" height="174" alt="image" src="https://github.com/user-attachments/assets/78331f76-23a6-46d0-9149-fb2c6d964d71" />

sql
Answer: SELECT p.patient_id, p.first_name AS first_name, p.last_name AS last_name, p.date_of_birth, p.admission_date, p.discharge_date, p.doctor_id, d.first_name AS doctor_name FROM patients p INNER JOIN doctors d ON p.doctor_id = d.doctor_id;


**Output:**
<img width="576" height="453" alt="image" src="https://github.com/user-attachments/assets/5005f722-c4ce-4488-aaac-fa5fd1569d80" />


**Question 5**
From the following tables write a SQL query to display the customer name, customer city, grade, salesman, salesman city. The results should be sorted by ascending customer_id. 
Sample table: customer
<img width="585" height="250" alt="image" src="https://github.com/user-attachments/assets/8f2675b2-85dc-4d65-9272-801fa91e3e2f" />
Sample table: salesman
<img width="443" height="211" alt="image" src="https://github.com/user-attachments/assets/59b27fae-6321-471f-b57e-cd1c59cf8e78" />

sql
Answer:

SELECT c.cust_name, c.city AS city, c.grade, s.name AS Salesman, s.city AS city FROM customer c JOIN salesman s ON c.salesman_id = s.salesman_id ORDER BY c.customer_id ASC;


**Output:**
<img width="909" height="533" alt="image" src="https://github.com/user-attachments/assets/258d7038-31ea-49ea-bdd7-82d30cb69571" />


**Question 6**
Write the SQL query that achieves the selection of all columns from the "patients" table and the specialization from the "doctors" table (aliased as "doctor_specialization"), with an inner join on the "doctor_id" column. 
PATIENTS TABLE:
<img width="271" height="237" alt="image" src="https://github.com/user-attachments/assets/57a14ddc-1077-4f36-996a-dd91c0e2ed6a" />
DOCTORS TABLE:
<img width="288" height="159" alt="image" src="https://github.com/user-attachments/assets/21822326-4d43-44ad-bd39-ae2ab4558a62" />

sql
Answer:

SELECT p.*, d.specialization AS doctor_specialization FROM patients p INNER JOIN doctors d ON p.doctor_id = d.doctor_id;


**Output:**
<img width="527" height="395" alt="image" src="https://github.com/user-attachments/assets/1215d695-61ab-40d7-8b4a-a54437150da0" />


**Question 7**
From the following tables write a SQL query to find those customers with a grade less than 300. Return cust_name, customer city, grade, Salesman, salesmancity. The result should be ordered by ascending customer_id. 
Sample table: customer
<img width="600" height="246" alt="image" src="https://github.com/user-attachments/assets/78e162bd-4a30-4cfb-862d-d70ad30d5ca0" />
Sample table: salesman
<img width="425" height="212" alt="image" src="https://github.com/user-attachments/assets/5d885ec5-7853-4cf4-a270-43bad0b3891d" />

sql
Answer:

SELECT c.cust_name, c.city AS city, c.grade, s.name AS Salesman, s.city AS city FROM customer c INNER JOIN salesman s ON c.salesman_id = s.salesman_id WHERE c.grade < 300 ORDER BY c.customer_id ASC;


**Output:**
<img width="735" height="425" alt="image" src="https://github.com/user-attachments/assets/9b4883e9-4f2d-4b8d-a370-0750a4ded692" />


**Question 8**
write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city. 
Sample table: salesman
<img width="457" height="194" alt="image" src="https://github.com/user-attachments/assets/24467fbc-01ac-4bb1-8eb6-229d141f9f36" />
Sample table: customer
<img width="572" height="253" alt="image" src="https://github.com/user-attachments/assets/ed0b630a-545f-4b86-aba0-a79d73af19eb" />

sql
Answer:

SELECT s.name AS Salesman, c.cust_name, s.city FROM salesman s INNER JOIN customer c ON s.city = c.city;


**Output:**
<img width="800" height="526" alt="image" src="https://github.com/user-attachments/assets/8cf3ad30-e087-47e7-9e63-524d937f5121" />



**Question 9**
Write the SQL query that accomplishes the selection of the first name from the "patients" table and all columns from the "surgeries" table, with an inner join on the "patient_id" column and a condition filtering for patients with the first name 'Alice'.
PATIENTS TABLE:
<img width="260" height="223" alt="image" src="https://github.com/user-attachments/assets/8f3acb02-dfdb-4d21-bc20-9575ac99defc" />
SURGERIES TABLE:
<img width="247" height="157" alt="image" src="https://github.com/user-attachments/assets/18140c81-7f33-4ddf-bac1-2e3118d4798f" />

sql
Answer:

SELECT p.first_name, s.surgery_id, s.patient_id, s.surgeon_id, s.surgery_date FROM patients p INNER JOIN surgeries s ON p.patient_id = s.patient_id WHERE p.first_name = 'Alice';


**Output:**
<img width="438" height="246" alt="image" src="https://github.com/user-attachments/assets/e3339e44-8c7f-44ad-8230-0133ab9721a9" />

**Question 10**
Write a SQL statement to join the tables salesman, customer and orders so that the same column of each table appears once and only the relational rows are returned. 
Sample table: orders image
<img width="525" height="353" alt="image" src="https://github.com/user-attachments/assets/bb3098dc-ec42-4621-bb61-f92400dfc02e" />
Sample table: customer image
<img width="560" height="248" alt="image" src="https://github.com/user-attachments/assets/e026e04b-aeb3-46f1-b507-29f1ad8ce32a" />
Sample table : salesman image
<img width="431" height="218" alt="image" src="https://github.com/user-attachments/assets/8198e92a-6e96-4230-a658-b57ecb95572a" />

sql
Answer:

SELECT o.ord_no, o.purch_amt, o.ord_date, c.cust_name, c.city AS customer_city, c.grade, s.name AS salesman_name, s.city AS salesman_city, s.commission FROM orders o INNER JOIN customer c ON o.customer_id = c.customer_id INNER JOIN salesman s ON o.salesman_id = s.salesman_id;

**Output:**
<img width="798" height="431" alt="image" src="https://github.com/user-attachments/assets/bbff9943-2bb1-40a5-b5a3-a867ad3ab565" />

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
