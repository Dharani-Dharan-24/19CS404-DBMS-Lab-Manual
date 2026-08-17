# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="1246" height="353" alt="image" src="https://github.com/user-attachments/assets/ecbc7bd6-727f-402d-b10d-546deaa26aa1" />



```sql
CREATE TABLE Invoices(
InvoiceID INTEGER primary key,
InvoiceDate DATE,
Amount REAL CHECK(Amount>0),
DueDate DATE CHECK(DueDate>InvoiceDate),
OrderID INTEGER,
FOREIGN KEY (OrderID)REFERENCES Orders(OrderID)
);
```

**Output:**

<img width="1247" height="242" alt="image" src="https://github.com/user-attachments/assets/4132b1f0-46b6-4f4c-9601-d7e18b05a892" />



**Question 2**
---
<img width="1260" height="378" alt="image" src="https://github.com/user-attachments/assets/49c059b7-7d97-4774-8194-887e7faf9c34" />



```sql
insert into Student_details values(205, "Olivia Green", "F", null, null);
insert into Student_details values(207, "Liam Smith", "M", "Mathematics", 85);
insert into Student_details values(208, "Sophia Johnson", "F", "Science", null);

```

**Output:**

<img width="1248" height="208" alt="image" src="https://github.com/user-attachments/assets/42d91a6c-c5e2-4b36-bb84-9e087556bd52" />


**Question 3**
---
<img width="1257" height="202" alt="image" src="https://github.com/user-attachments/assets/6a83e7b7-033d-4306-a9cd-76d30da50253" />

```sql
create table jobs(
    job_id integer,
    job_title text default null,
    min_salary integer default 8000,
    max_salary integer default null
);
```

**Output:**

<img width="1182" height="147" alt="image" src="https://github.com/user-attachments/assets/e1f6d9f0-b28b-4506-8520-87b5bc828058" />


**Question 4**
---
<img width="910" height="267" alt="image" src="https://github.com/user-attachments/assets/acf7c761-270c-4884-935a-5be67097619e" />


```sql
insert into Products(ProductID, ProductName, Price, Stock)
select ProductID, ProductName, Price, Stock from Discontinued_products;
```

**Output:**

<img width="1252" height="212" alt="image" src="https://github.com/user-attachments/assets/df1272dd-733d-4698-87f6-da75f3acc87d" />


**Question 5**
---
<img width="937" height="310" alt="image" src="https://github.com/user-attachments/assets/1133ae03-d882-4cad-ac8d-6e432d94c53a" />


```sql
insert into Employee (EmployeeID, Name, Position) values (4, "Emily White", "Analyst");
```

**Output:**

<img width="1251" height="241" alt="image" src="https://github.com/user-attachments/assets/8130324e-fbaa-433c-9dbe-615b441b2120" />


**Question 6**
---
<img width="870" height="285" alt="image" src="https://github.com/user-attachments/assets/a69507fb-e9d7-40dc-a1eb-d000cc6bd2d0" />


```sql
create table Products(
    ProductID integer primary key,
    ProductName text not null,
    Price real check(Price > 0),
    Stock integer check(Stock >= 0)
);
```

**Output:**

<img width="1252" height="188" alt="image" src="https://github.com/user-attachments/assets/cc69a796-d018-48a7-86d9-29abe6147a03" />


**Question 7**
---
<img width="997" height="477" alt="image" src="https://github.com/user-attachments/assets/f9d8baff-6fcc-42dd-ba85-3dc9139dd175" />


```sql
alter table Student_details add Country TEXT;
```

**Output:**

<img width="1297" height="228" alt="image" src="https://github.com/user-attachments/assets/737f9e5f-91f2-4069-bd73-37251980eb00" />


**Question 8**
---
<img width="971" height="217" alt="image" src="https://github.com/user-attachments/assets/c4b06eaf-bb6e-4651-bacb-684c030dcff7" />


```sql
create table ProjectAssignments(
    AssignmentID  integer primary key,
    EmployeeID integer,
    ProjectID  integer,
    AssignmentDate  date not null,
    foreign key (EmployeeID) references Employees(EmployeeID),
    foreign key (ProjectID) references Projects(ProjectID)
);
```

**Output:**

<img width="1095" height="126" alt="image" src="https://github.com/user-attachments/assets/6315ed8c-976e-4b40-8236-debdbd279996" />


**Question 9**
---
<img width="741" height="260" alt="image" src="https://github.com/user-attachments/assets/79e1ed2f-5a3e-456f-90ad-762e2bd809b5" />


```sql
create table Locations(
    LocationID  INTEGER,
    LocationName  TEXT,
    Address  TEXT
);
```

**Output:**

<img width="1045" height="182" alt="image" src="https://github.com/user-attachments/assets/29281342-a254-41be-9f6d-c1e3a4bb4ccf" />


**Question 10**
---
<img width="695" height="207" alt="image" src="https://github.com/user-attachments/assets/9acbd863-d358-40af-8101-8a8f5dc2232c" />


```sql
alter table employee add designation varchar(50);
```

**Output:**

<img width="1268" height="162" alt="image" src="https://github.com/user-attachments/assets/3611f419-f0f0-4908-bb42-53c2f5a50022" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
