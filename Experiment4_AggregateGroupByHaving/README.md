# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="1082" height="634" alt="image" src="https://github.com/user-attachments/assets/6dc01471-9d1f-4c6b-a900-eb11eb30b028" />


sql

select Medication,count() as TotalPrescriptions
from Prescriptions
group by Medication

**Output:**

<img width="1073" height="735" alt="image" src="https://github.com/user-attachments/assets/6370950d-28df-4b22-adca-8a80d342c1ca" />


**Question 2**
<img width="1066" height="628" alt="image" src="https://github.com/user-attachments/assets/58e972ab-01d8-4862-8902-b3a733287292" />


sql
select DoctorID,count() as TotalPrescriptions from Prescriptions
group by DoctorID

**Output:**
<img width="1043" height="741" alt="image" src="https://github.com/user-attachments/assets/9bbef230-3ce8-421b-84d5-9dba4c38fb58" />


**Question 3**
<img width="1064" height="548" alt="image" src="https://github.com/user-attachments/assets/cc483e75-b295-41e0-ad80-56d9479503cf" />

sql
SELECT PatientID,COUNT() as TotalRecords
from MedicalRecords
group by PatientID

**Output:**
<img width="738" height="623" alt="image" src="https://github.com/user-attachments/assets/6ceab914-beda-4919-afc3-0bd1761064a0" />


**Question 4**
<img width="765" height="475" alt="image" src="https://github.com/user-attachments/assets/52ad6f61-ab4e-4162-b236-6a079f7cf635" />

sql
select name,length(name) as length from customer
ORDER BY LENGTH(name) DESC
LIMIT 1

**Output:**
<img width="769" height="400" alt="image" src="https://github.com/user-attachments/assets/44ac4067-936a-4114-bf95-9a01a4aa1688" />

**Question 5**
<img width="829" height="491" alt="image" src="https://github.com/user-attachments/assets/9a877afe-26cc-42f8-9386-b4795b0e0b0b" />

sql
select sum(income) as 'total_income' from employee
where age>=40


**Output:**
<img width="526" height="304" alt="image" src="https://github.com/user-attachments/assets/25aae053-1b32-4619-bab2-663d2a338ab1" />


**Question 6**
<img width="1050" height="514" alt="image" src="https://github.com/user-attachments/assets/2360ab62-5aad-421c-bf8d-b962f0ad2702" />

sql
select COUNT(DISTINCT(salesman_id)) as 'COUNT' FROM orders


**Output:**
<img width="493" height="333" alt="image" src="https://github.com/user-attachments/assets/c263708a-7e86-49b8-820c-1fcf5d7d8c0e" />


![Output6](output.png)

**Question 7**
<img width="1139" height="485" alt="image" src="https://github.com/user-attachments/assets/00ed2004-d425-42e5-a2d8-8a2df94d1536" />

sql
select max(age) - min(age) as 'age_difference' from employee


**Output:**
<img width="638" height="319" alt="image" src="https://github.com/user-attachments/assets/b44c384b-52d1-450a-a8e7-c7531184f6b1" />


**Question 8**
<img width="1246" height="556" alt="image" src="https://github.com/user-attachments/assets/4cd4009a-7a3f-4184-a862-85a8961090d3" />

sql
select category_id, sum(price*category_id) as 'Revenue' from products
group by category_id
having Revenue > 25

**Output:**
<img width="798" height="454" alt="image" src="https://github.com/user-attachments/assets/be2c3c38-e3c3-452c-afb1-1778693d35d7" />


![Output8](output.png)

**Question 9**
<img width="979" height="546" alt="image" src="https://github.com/user-attachments/assets/0df10adf-d1df-4909-82af-1d055a054c4e" />

sql
select PatientID,COUNT(*) AS 'TotalRecords' from MedicalRecords
group by PatientID
HAVING TotalRecords > 3


**Output:**
<img width="902" height="391" alt="image" src="https://github.com/user-attachments/assets/f63a96e8-fbe8-42a9-9787-7e8e5bec9f14" />


![Output9](output.png)

**Question 10**
<img width="1327" height="532" alt="image" src="https://github.com/user-attachments/assets/b9b19aed-420a-4170-85f0-f33c222704ca" />

sql
select category_id,count(*) as COUNT FROM products
group by category_id
having category_id>2


**Output:**
<img width="735" height="397" alt="image" src="https://github.com/user-attachments/assets/09861e50-eea8-43ce-8df0-aa40cc222200" />


![Output10](output.png)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
