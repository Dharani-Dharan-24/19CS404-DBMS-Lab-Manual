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
<img width="1216" height="572" alt="image" src="https://github.com/user-attachments/assets/e3bb41c1-8a67-49df-ae1f-f27c63442821" />


```sql
select DoctorID, count(PrescriptionID) as TotalPrescriptions from Prescriptions group by DoctorID;
```

**Output:**

<img width="1232" height="681" alt="image" src="https://github.com/user-attachments/assets/26e0a48b-0dd0-44ef-9e47-e7ea274c3e19" />


**Question 2**
---
<img width="991" height="497" alt="image" src="https://github.com/user-attachments/assets/91f08a8e-3e76-4481-8c8e-d157e97fbd1d" />


```sql
select Specialty, Gender, count(DoctorID) as TotalDoctors from Doctors group by Specialty, Gender;
```

**Output:**

<img width="1222" height="577" alt="image" src="https://github.com/user-attachments/assets/a95c261b-153e-4705-8937-15945d110ae3" />


**Question 3**
---
<img width="1167" height="571" alt="image" src="https://github.com/user-attachments/assets/cc0810b0-e579-4efb-9134-fd9408a6db87" />


```sql
select InsuranceCompany, count(InsuranceID) as TotalPatients from Insurance group by  InsuranceCompany;
```

**Output:**

<img width="1157" height="602" alt="image" src="https://github.com/user-attachments/assets/50a837aa-c380-49d6-9fd3-be4d2f5f2c9b" />


**Question 4**
---
<img width="962" height="455" alt="image" src="https://github.com/user-attachments/assets/6b372ced-c486-4039-b3dd-2974c0084ebd" />


```sql
select count(customer_id) as COUNT from customer where grade is not null;
```

**Output:**

<img width="1255" height="262" alt="image" src="https://github.com/user-attachments/assets/ba11a809-6a1d-4c28-bc7a-8574711f6776" />


**Question 5**
---
<img width="1085" height="427" alt="image" src="https://github.com/user-attachments/assets/4ee29090-657f-4f6f-b018-693cf145d7cd" />


```sql
select max(age) - min(age) as age_difference from employee;
```

**Output:**

<img width="1137" height="260" alt="image" src="https://github.com/user-attachments/assets/9c742143-c89d-45aa-9858-fb42fdd23f94" />


**Question 6**
---
<img width="1000" height="415" alt="image" src="https://github.com/user-attachments/assets/938ac8e2-efa1-4775-8e00-e088a2f63a52" />


```sql
select sum(purch_amt) as TOTAL from orders;
```

**Output:**

<img width="1217" height="270" alt="image" src="https://github.com/user-attachments/assets/cc0f5d7d-80b8-44e9-938e-0245c0a1051f" />


**Question 7**
---
<img width="1150" height="420" alt="image" src="https://github.com/user-attachments/assets/d7b8093b-ec17-4dc8-b6fd-87cdb582704a" />


```sql
select name, max(income) from employee where city = "California";
```

**Output:**

<img width="1100" height="290" alt="image" src="https://github.com/user-attachments/assets/0e90658d-b034-459a-ba1a-64925241a8bc" />


**Question 8**
---
<img width="1232" height="422" alt="image" src="https://github.com/user-attachments/assets/f5a16b31-b6ab-4ac1-8192-89f557d7ce2d" />


```sql
select category_id, count(*) as COUNT from products where category_id > 2 group by category_id;
```

**Output:**

<img width="1295" height="275" alt="image" src="https://github.com/user-attachments/assets/582d87f1-f449-457a-8e62-7161dd76834a" />


**Question 9**
---
<img width="980" height="456" alt="image" src="https://github.com/user-attachments/assets/ccbe8537-f515-4ead-9af4-db55a187b4f0" />


```sql
select PatientID, count(*) as TotalRecords from MedicalRecords group by PatientID having count(*) > 3;
```

**Output:**

<img width="1242" height="277" alt="image" src="https://github.com/user-attachments/assets/d96abbc3-4a1d-4524-b6e0-ee6ddb1c0fe4" />


**Question 10**
---
<img width="1247" height="496" alt="image" src="https://github.com/user-attachments/assets/41655c16-5a56-4d19-aa09-95fb34bc1d04" />


```sql
select address, SUM(salary) from customer1 group by address having SUM(salary) > 2000;
```

**Output:**

<img width="812" height="400" alt="image" src="https://github.com/user-attachments/assets/c2fb1bfc-b0b5-4e89-8b72-44fe3d970244" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
