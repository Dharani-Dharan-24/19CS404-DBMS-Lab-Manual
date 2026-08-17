# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="1213" height="740" alt="image" src="https://github.com/user-attachments/assets/011c5385-aff0-4f16-b1df-90d31f2ae25a" />



```sql
update employees set salary = salary + 500, email = "updated" where job_id = "SA_REP" and commission_pct > 0.15;
```

**Output:**

<img width="1287" height="317" alt="image" src="https://github.com/user-attachments/assets/f939d1d1-3e52-4e0c-ae94-94fb1e30b96d" />


**Question 2**
---
<img width="711" height="153" alt="image" src="https://github.com/user-attachments/assets/f4d74fbf-1553-455d-916b-3dd92f1b9d1a" />


```sql
update products set availability = availability * 2 where product_id = 1;
```

**Output:**

<img width="935" height="152" alt="image" src="https://github.com/user-attachments/assets/e2854521-0be1-489f-8f90-e98da258185c" />


**Question 3**
---
<img width="1081" height="401" alt="image" src="https://github.com/user-attachments/assets/ec91f069-14e6-4916-ba19-7c7cb1158b51" />


```sql
update employees set email = "not available", commission_pct = 0.55 where department_id = 110;
```

**Output:**

<img width="1277" height="230" alt="image" src="https://github.com/user-attachments/assets/b9fb1f9c-04e3-4e02-a40c-ef2a0dca4c66" />


**Question 4**
---
<img width="852" height="422" alt="image" src="https://github.com/user-attachments/assets/942da4fe-ab1d-4455-9333-385a8beac0ec" />


```sql
update employees set hire_date = "2024-01-24" where department_id = 50;
```

**Output:**

<img width="1012" height="176" alt="image" src="https://github.com/user-attachments/assets/31ff17f2-74f1-44f2-810e-7d71dfd4211d" />


**Question 5**
---
<img width="1051" height="402" alt="image" src="https://github.com/user-attachments/assets/ceafd706-3389-472d-9454-b0e49d8bcbd7" />


```sql
update products set reorder_lvl = (reorder_lvl * 0.7) where product_name like '%cream%' and quantity > reorder_lvl;
```

**Output:**

<img width="1353" height="211" alt="image" src="https://github.com/user-attachments/assets/80011036-f0fe-4e6b-af75-76c2ff059651" />


**Question 6**
---
<img width="1052" height="513" alt="image" src="https://github.com/user-attachments/assets/0811a39e-54f9-4a6b-97b5-07c09d706687" />


```sql
delete from customer where agent_code = "A003" or agent_code = "A008";
```

**Output:**

<img width="973" height="733" alt="image" src="https://github.com/user-attachments/assets/f627a36f-56ba-4f1e-ba86-ffba032c51a7" />


**Question 7**
---
<img width="1157" height="291" alt="image" src="https://github.com/user-attachments/assets/5f0d4a5c-d42b-44dd-8b13-c898574751be" />


```sql
delete from customer where grade = 3 and cust_name like "%BBB%" and payment_amt > 2000;
```

**Output:**

<img width="1657" height="253" alt="image" src="https://github.com/user-attachments/assets/66c0e543-8bfb-4ca7-b895-5d59b1f1628d" />


**Question 8**
---
<img width="1283" height="302" alt="image" src="https://github.com/user-attachments/assets/4640db52-7540-46f0-a385-b9bb4375f031" />


```sql
delete from customer where cust_country not in ("India", "USA");
```

**Output:**

<img width="1781" height="296" alt="image" src="https://github.com/user-attachments/assets/a8a2cafc-d1be-473e-ab22-da1d13cdad9b" />


**Question 9**
---
<img width="1146" height="353" alt="image" src="https://github.com/user-attachments/assets/22a08796-e6ce-4e67-ab96-6a96d70946e9" />


```sql
delete from customer where cust_country not in ('UK', 'USA', 'Canada') and grade >= 3;
```

**Output:**

<img width="1645" height="212" alt="image" src="https://github.com/user-attachments/assets/2c6a97f1-4431-4a0e-a402-d80cbe93a5e3" />


**Question 10**
---
<img width="1288" height="472" alt="image" src="https://github.com/user-attachments/assets/70a84e19-456c-43b5-8005-13ddd3797452" />


```sql
delete from customer where opening_amt between 4000 and 6000;
```

**Output:**

<img width="1572" height="281" alt="image" src="https://github.com/user-attachments/assets/b8cfeaa9-c4fc-4f32-b30e-b9bb89b76492" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
