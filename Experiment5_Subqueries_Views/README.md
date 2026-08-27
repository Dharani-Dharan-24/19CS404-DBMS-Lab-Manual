# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="1087" height="562" alt="image" src="https://github.com/user-attachments/assets/12517bf5-4b13-4222-b5d8-6c7cb1b261f2" />


```sql
select * from customers where salary = 1500;
```

**Output:**

<img width="1242" height="302" alt="image" src="https://github.com/user-attachments/assets/8b7c9d8b-8793-40ba-a3f3-fb4972d04599" />


**Question 2**
---
<img width="1200" height="465" alt="image" src="https://github.com/user-attachments/assets/2380045d-fca0-45f0-be3f-f4d3b182ee2e" />


```sql
select  medication_id as medic, medication_name, dosage from medications where dosage = (select max(dosage) from medications);
```

**Output:**

<img width="1167" height="342" alt="image" src="https://github.com/user-attachments/assets/ad5f86ba-4e86-433d-ba08-ea27229b0692" />


**Question 3**
---
<img width="1236" height="601" alt="image" src="https://github.com/user-attachments/assets/6db39675-556f-41e4-8312-cc244bbdc388" />


```sql
select * from employee where age < (select avg(age) from employee where income > 250000);
```

**Output:**

<img width="1247" height="437" alt="image" src="https://github.com/user-attachments/assets/d1cf73f6-778a-4754-8f3e-c3d35dca4ee4" />


**Question 4**
---
<img width="1047" height="571" alt="image" src="https://github.com/user-attachments/assets/f3780716-4267-49af-af96-25ab5855ad53" />


```sql
select * from customers where address = 'Delhi';
```

**Output:**

<img width="1202" height="291" alt="image" src="https://github.com/user-attachments/assets/bd27619b-e586-44b8-b885-54cfe0f30e29" />


**Question 5**
---
<img width="1287" height="655" alt="image" src="https://github.com/user-attachments/assets/38b7dcea-0c5c-473b-9477-94ff5ddf4b84" />


```sql
select * from orders where salesman_id = (select salesman_id from salesman where name = 'Paul Adam');
```

**Output:**

<img width="1282" height="332" alt="image" src="https://github.com/user-attachments/assets/a8ad15c9-55cb-4473-8dff-5fc3cc1cbcea" />


**Question 6**
---
<img width="1287" height="717" alt="image" src="https://github.com/user-attachments/assets/e57ce429-8d59-47ff-a034-5628b9a7d5cc" />


```sql
select order_no as ord_no, purch_amt, ord_date, salesman_id from orders where salesman_id in (select salesman_id from salesman where commission = (select max(commission) from salesman));
```

**Output:**

<img width="1281" height="595" alt="image" src="https://github.com/user-attachments/assets/5c30a36c-28be-44c5-91e8-298dc84a2ad7" />


**Question 7**
---
<img width="1286" height="665" alt="image" src="https://github.com/user-attachments/assets/ab6db032-4838-493b-b7ba-199da4d66b02" />


```sql
select * from customers where age < 30;
```

**Output:**

<img width="1270" height="526" alt="image" src="https://github.com/user-attachments/assets/f471935c-e7bf-4e46-9b1a-7ea92eba40cd" />


**Question 8**
---
<img width="1237" height="671" alt="image" src="https://github.com/user-attachments/assets/5ddc2379-9ccc-4810-87c5-9796d74e9aec" />


```sql
select * from customers where salary > 1500;
```

**Output:**

<img width="1290" height="540" alt="image" src="https://github.com/user-attachments/assets/5f160eba-643e-48f9-9dec-ada9734a3b12" />


**Question 9**
---
<img width="1327" height="732" alt="image" src="https://github.com/user-attachments/assets/0f40a9f0-29dd-4a51-92fe-9cb1f5bbd954" />


```sql
select * from orders where salesman_id in (select salesman_id from salesman where city='New York');
```

**Output:**

<img width="1267" height="437" alt="image" src="https://github.com/user-attachments/assets/6478b216-c8ec-4305-bace-5aaf1cdb960e" />


**Question 10**
---
<img width="1290" height="652" alt="image" src="https://github.com/user-attachments/assets/a4d98839-2b41-4181-b1cb-f2ef5a0dc842" />


```sql
select * from orders where salesman_id in (select salesman_id from salesman where city='London');
```

**Output:**

<img width="1241" height="356" alt="image" src="https://github.com/user-attachments/assets/37ee13a8-090f-446a-bfec-79a486c5d695" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
