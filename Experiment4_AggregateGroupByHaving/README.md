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

<img width="1208" height="506" alt="image" src="https://github.com/user-attachments/assets/dc812681-d5f3-4ac8-bad0-0b0de96264e1" />

```sql
select avg(income) as Average_Salary
from employee;

```

**Output:**

<img width="1218" height="309" alt="image" src="https://github.com/user-attachments/assets/f43a7d7b-a0a0-4228-95ef-c79a2c8a725a" />


**Question 2**
---

<img width="1199" height="490" alt="image" src="https://github.com/user-attachments/assets/4b1d0a75-dad8-4fb2-b73c-ebf632dae0cc" />


```sql
select sum(income) as total_income
from employee
where age>=40;
```

**Output:**

<img width="1211" height="314" alt="image" src="https://github.com/user-attachments/assets/ecaec951-c80a-4946-ba1e-9a551cc83f80" />


**Question 3**
---

<img width="1216" height="472" alt="image" src="https://github.com/user-attachments/assets/c7d36dac-72eb-4f56-bace-7295feb098b5" />


```sql
select max(age)-min(age) as age_difference
from employee;
```

**Output:**

<img width="1203" height="319" alt="image" src="https://github.com/user-attachments/assets/d0a0ec3c-77cf-4c44-948f-d026f174229b" />


**Question 4**
---

<img width="1208" height="561" alt="image" src="https://github.com/user-attachments/assets/03eea770-c432-4c79-8e5c-40519f0b3773" />


```sql
select specialty,count(*) as TotalDocto
from doctors
group by specialty;
```

**Output:**

<img width="1202" height="678" alt="image" src="https://github.com/user-attachments/assets/0a91494c-ce78-4466-914d-a1c2fc01ef82" />


**Question 5**
---

<img width="1220" height="362" alt="image" src="https://github.com/user-attachments/assets/c13b1efc-3ca3-4890-9625-25bc310d3208" />


```sql
select substr(email,instr(email,'@')+1) as EmailDomain, count(*) as TotalPatients
from patients
group by EmailDomain;
```

**Output:**

<img width="1205" height="464" alt="image" src="https://github.com/user-attachments/assets/ef9b4101-4bb7-4f12-b701-b95b5c09c252" />


**Question 6**
---

<img width="1217" height="564" alt="image" src="https://github.com/user-attachments/assets/3eb0baab-a26c-492c-ad2f-8cf139e42ad2" />


```sql
select  strftime('%Y',validityperiod) as ValidityYear, count(distinct patientid) as TotalPatients
from insurance
group by validityperiod
order by validityyear asc;
```

**Output:**

<img width="1211" height="390" alt="image" src="https://github.com/user-attachments/assets/0cef11c7-3e47-4a5b-99ff-4dc2789dafac" />


**Question 7**
---

<img width="1194" height="524" alt="image" src="https://github.com/user-attachments/assets/5346392f-fd43-4aac-9720-57a09d4513ed" />


```sql
select city, avg(income) as "AVG(income)"
from employee
group by city
having AVG(income)>500000;
```

**Output:**

<img width="1219" height="441" alt="image" src="https://github.com/user-attachments/assets/3b842368-3917-48b7-8c9b-ec6eea921651" />


**Question 8**
---

<img width="1213" height="527" alt="image" src="https://github.com/user-attachments/assets/733b41ed-5246-4b46-a1fb-986381c1e3fa" />


```sql
select category_id, count(product_name) as 'count(product_name)'
from products
group by category_id
having min(category_id)<3;
```

**Output:**

<img width="1198" height="359" alt="image" src="https://github.com/user-attachments/assets/bc919d90-43a0-467e-b099-1ddf85b4a831" />

**Question 9**
---

<img width="1204" height="485" alt="image" src="https://github.com/user-attachments/assets/db42aa76-dbd1-4995-88d7-05b34ef88196" />

```sql
select category_id, sum(price) as Total_Cost
from products
group by category_id
having Total_Cost>50;
```

**Output:**

<img width="1212" height="346" alt="image" src="https://github.com/user-attachments/assets/384b78cc-ab82-4c0f-8485-cc8e56e7130d" />

**Question 10**
---

<img width="1206" height="519" alt="image" src="https://github.com/user-attachments/assets/4b769776-4e53-40c4-ad46-33b0c86b4466" />


```sql
select category_id, sum(price)*category_id as Revenue
from products
group by category_id
having Revenue>25;
```

**Output:**

<img width="1201" height="439" alt="image" src="https://github.com/user-attachments/assets/97b678ca-54bc-45dc-b56e-cee3e4ce5a97" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
