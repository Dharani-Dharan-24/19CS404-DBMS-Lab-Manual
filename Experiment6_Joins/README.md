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
--
<img width="1227" height="767" alt="image" src="https://github.com/user-attachments/assets/a383569a-eef0-4299-a0f0-994e38d09a33" />


```sql
SELECT c.cust_name, c.city, c.grade, s.name AS "Salesman", s.city FROM customer c JOIN salesman s ON c.salesman_id = s.salesman_id order by c.customer_id;
```

**Output:**

<img width="1306" height="725" alt="image" src="https://github.com/user-attachments/assets/8d0dd0d0-1890-497e-a705-c8351662127b" />


**Question 2**
---
<img width="1322" height="567" alt="image" src="https://github.com/user-attachments/assets/c6cc513d-41f9-48a0-bb44-64a860123944" />


```sql
SELECT n.nurse_id, d.department_name
FROM NURSES n
JOIN DEPARTMENTS d ON n.department_id = d.department_id
WHERE n.first_name = 'David';
```

**Output:**

<img width="1156" height="292" alt="image" src="https://github.com/user-attachments/assets/3999fe46-5c2b-43d6-b01f-f3ec776803dc" />


**Question 3**
---
<img width="1302" height="652" alt="image" src="https://github.com/user-attachments/assets/2b96f342-a4b0-4730-b79a-660ed958a4d7" />


```sql
SELECT patients.*, doctors.first_name as doctor_name
FROM patients
JOIN doctors ON patients.doctor_id = doctors.doctor_id;
```

**Output:**

<img width="1222" height="271" alt="image" src="https://github.com/user-attachments/assets/df88b405-c07b-47fb-b7a0-ab64ef36bb0f" />


**Question 4**
---
<img width="1330" height="777" alt="image" src="https://github.com/user-attachments/assets/3d56378e-dc2c-4e73-acb4-dd8405581c00" />


```sql
SELECT 
    a.cust_name, 
    a.city, 
    b.ord_no, 
    b.ord_date, 
    b.purch_amt as "Order Amount"
FROM customer a
LEFT JOIN orders b 
  ON a.customer_id = b.customer_id
ORDER BY b.ord_date;
```

**Output:**

<img width="1132" height="792" alt="image" src="https://github.com/user-attachments/assets/6ab1f3ca-9830-4661-b94e-4ec9b354520d" />


**Question 5**
---
<img width="1307" height="615" alt="image" src="https://github.com/user-attachments/assets/e3af0a4f-7f07-4e51-a631-0af406573050" />


```sql
SELECT 
    c.cust_name, 
    c.city, 
    c.grade, 
    s.name AS "Salesman", 
    s.city 
FROM customer c 
JOIN salesman s 
  ON c.salesman_id = s.salesman_id 
WHERE c.grade < 300 
ORDER BY c.customer_id ASC;
```

**Output:**

<img width="1260" height="502" alt="image" src="https://github.com/user-attachments/assets/7c81fd69-c955-418d-a0c6-e161f1f045a5" />


**Question 6**
---
<img width="1340" height="377" alt="image" src="https://github.com/user-attachments/assets/26fe70a4-de72-49e2-a3ef-eac77620df06" />


```sql
SELECT 
    s.name AS salesman_name, 
    c.cust_name AS customer_name
FROM salesman s
LEFT JOIN customer c 
  ON s.salesman_id = c.salesman_id;
```

**Output:**

<img width="1322" height="612" alt="image" src="https://github.com/user-attachments/assets/6474ed30-ef48-4094-9bf6-f074f6d9f4b3" />


**Question 7**
---
<img width="1302" height="221" alt="image" src="https://github.com/user-attachments/assets/884af124-79ee-4342-ad4a-f48ed0f1af83" />



```sql
select s.name from Salesman s 
left join customer c
on s.salesman_id = c.salesman_id where c.city = "New York";
```

**Output:**

<img width="1092" height="257" alt="image" src="https://github.com/user-attachments/assets/1ca25c10-5866-4fe0-ba8a-1cf24da1babf" />


**Question 8**
---
<img width="1180" height="612" alt="image" src="https://github.com/user-attachments/assets/8aefd17c-4896-43a4-8ac3-f8f2775e8759" />


```sql
select c.cust_name as "Customer Name", c.city, s.name as Salesman, s.commission
from customer c
join salesman s
on c.salesman_id = s.salesman_id
where s.commission > 0.12;
```

**Output:**

<img width="1320" height="502" alt="image" src="https://github.com/user-attachments/assets/b6dd12ab-343a-4d12-9d13-4543aad1bdac" />


**Question 9**
---
<img width="917" height="737" alt="image" src="https://github.com/user-attachments/assets/d5ef831c-3ee9-4a8d-848c-e762faf29f15" />


```sql
SELECT 
    a.ord_no, 
    a.ord_date, 
    a.purch_amt, 
    b.cust_name AS "Customer Name", 
    b.grade, 
    c.name AS "Salesman", 
    c.commission 
FROM orders a 
JOIN customer b 
  ON a.customer_id = b.customer_id 
JOIN salesman c 
  ON a.salesman_id = c.salesman_id;
```

**Output:**

<img width="1137" height="600" alt="image" src="https://github.com/user-attachments/assets/f7413430-a76f-4dc7-84d5-4dfe2562e7a2" />


**Question 10**
---
<img width="1337" height="512" alt="image" src="https://github.com/user-attachments/assets/b8a35af8-df7b-4f7c-98db-fd57c75aefbe" />


```sql
select p.first_name, p.last_name
from patients p
inner join surgeries s
on p.patient_id = s.patient_id
where surgery_date between '2024-01-01' and '2024-01-31';
```

**Output:**

<img width="1007" height="247" alt="image" src="https://github.com/user-attachments/assets/ad91acfc-9356-4ddf-af1a-1fb2b5aaf3a0" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
