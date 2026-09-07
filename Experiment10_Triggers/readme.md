# Experiment 10: PL/SQL – Triggers

## AIM
To write and execute PL/SQL trigger programs for automating actions in response to specific table events like INSERT, UPDATE, or DELETE.

---

## THEORY

A **trigger** is a stored PL/SQL block that is automatically executed or fired when a specified event occurs on a table or view. Triggers can be used for enforcing business rules, auditing changes, or automatic updates.

### Types of Triggers:
- **Before Trigger**: Executes before the operation (INSERT, UPDATE, DELETE).
- **After Trigger**: Executes after the operation.
- **Row-level Trigger**: Executes for each affected row.
- **Statement-level Trigger**: Executes once for the triggering statement.

**Basic Syntax:**
```sql
CREATE OR REPLACE TRIGGER trigger_name
BEFORE|AFTER INSERT|UPDATE|DELETE ON table_name
[FOR EACH ROW]
BEGIN
   -- trigger logic
END;
```

## 1. Write a trigger to log every insertion into a table.
**Steps:**
- Create two tables: `employees` (for storing data) and `employee_log` (for logging the inserts).
- Write an **AFTER INSERT** trigger on the `employees` table to log the new data into the `employee_log` table.
PROGRAM :
<img width="955" height="802" alt="Screenshot 2026-09-07 060853" src="https://github.com/user-attachments/assets/363ef6bc-b495-46a1-9eaf-1fe986326b3a" />


**Expected Output:**
- A new entry is added to the `employee_log` table each time a new record is inserted into the `employees` table.
<img width="1405" height="554" alt="image" src="https://github.com/user-attachments/assets/6a869bb2-882a-45ee-bc36-46d099418280" />

---

## 2. Write a trigger to prevent deletion of records from a sensitive table.
**Steps:**
- Write a **BEFORE DELETE** trigger on the `sensitive_data` table.
- Use `RAISE_APPLICATION_ERROR` to prevent deletion and issue a custom error message.
PROGRAM :
<img width="975" height="485" alt="Screenshot 2026-09-07 060928" src="https://github.com/user-attachments/assets/d3ce8d2c-b04d-49bb-8f6c-8a3b77cba524" />

**Expected Output:**
- If an attempt is made to delete a record from `sensitive_data`, an error message is raised, e.g., `ERROR: Deletion not allowed on this table.`
<img width="1409" height="598" alt="image" src="https://github.com/user-attachments/assets/e6a54152-a276-4077-a4e1-a2fa9dbb7f26" />

---

## 3. Write a trigger to automatically update a `last_modified` timestamp.
**Steps:**
- Add a `last_modified` column to the `products` table.
- Write a **BEFORE UPDATE** trigger on the `products` table to set the `last_modified` column to the current timestamp whenever an update occurs.
PROGRAM:
<img width="860" height="642" alt="Screenshot 2026-09-07 060954" src="https://github.com/user-attachments/assets/24501008-cde1-421d-b725-267f5e5ee926" />

**Expected Output:**
- The `last_modified` column in the `products` table is updated automatically to the current date and time when any record is updated.
<img width="1394" height="636" alt="image" src="https://github.com/user-attachments/assets/825abbb6-1573-40b5-87e6-76600e44ad8e" />

---

## 4. Write a trigger to keep track of the number of updates made to a table.
**Steps:**
- Create an `audit_log` table with a counter column.
- Write an **AFTER UPDATE** trigger on the `customer_orders` table to increment the counter in the `audit_log` table every time a record is updated.
PROGRAM :
<img width="876" height="662" alt="Screenshot 2026-09-07 061030" src="https://github.com/user-attachments/assets/0eee0d0c-0391-490b-be2c-e8d1ab14370c" />
<img width="917" height="231" alt="Screenshot 2026-09-07 061635" src="https://github.com/user-attachments/assets/538bae04-6dbe-4ebd-a7d6-8e801a38d792" />

**Expected Output:**
- The `audit_log` table will maintain a count of how many updates have been made to the `customer_orders` table.
<img width="1388" height="569" alt="image" src="https://github.com/user-attachments/assets/f43db5cf-0f06-44ca-8e6d-f3480c33f364" />

---

## 5. Write a trigger that checks a condition before allowing insertion into a table.
**Steps:**
- Write a **BEFORE INSERT** trigger on the `employees` table to check if the inserted salary meets a specific condition (e.g., salary must be greater than 3000).
- If the condition is not met, raise an error to prevent the insert.
PROGRAM :
<img width="987" height="378" alt="Screenshot 2026-09-07 061701" src="https://github.com/user-attachments/assets/3247fd71-c3f4-42d9-a9c9-7640e9ba60b5" />

**Expected Output:**
- If the inserted salary in the `employees` table is below the condition (e.g., salary < 3000), the insert operation is blocked, and an error message is raised, such as: `ERROR: Salary below minimum threshold.`
<img width="1402" height="639" alt="image" src="https://github.com/user-attachments/assets/d767ba1f-c518-4347-8f0c-d24f0cdd6798" />
<img width="1404" height="599" alt="image" src="https://github.com/user-attachments/assets/659360b4-258e-42fe-8c92-7e35c91e6330" />

## RESULT
Thus, the PL/SQL trigger programs were written and executed successfully.
