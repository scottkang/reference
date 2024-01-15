# psql

```bash
psql -U postgres

postgres=# \l
                                                List of databases
   Name    |  Owner   | Encoding |  Collate   |   Ctype    | ICU Locale | Locale Provider |   Access privileges   
-----------+----------+----------+------------+------------+------------+-----------------+-----------------------
 employees | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
(4 rows)

postgres=# \c employees
You are now connected to database "employees" as user "postgres".
employees=# \d employees
                      Table "public.employees"
   Column   |         Type          | Collation | Nullable | Default 
------------+-----------------------+-----------+----------+---------
 emp_no     | integer               |           | not null | 
 birth_date | date                  |           | not null | 
 first_name | character varying(14) |           | not null | 
 last_name  | character varying(16) |           | not null | 
 gender     | gender                |           | not null | 
 hire_date  | date                  |           | not null | 
Indexes:
    "employees_pkey" PRIMARY KEY, btree (emp_no)
Referenced by:
    TABLE "dept_emp" CONSTRAINT "dept_emp_emp_no_fkey" FOREIGN KEY (emp_no) REFERENCES employees(emp_no) ON DELETE CASCADE
    TABLE "dept_manager" CONSTRAINT "dept_manager_emp_no_fkey" FOREIGN KEY (emp_no) REFERENCES employees(emp_no) ON DELETE CASCADE
    TABLE "salaries" CONSTRAINT "salaries_emp_no_fkey" FOREIGN KEY (emp_no) REFERENCES employees(emp_no) ON DELETE CASCADE
    TABLE "titles" CONSTRAINT "titles_emp_no_fkey" FOREIGN KEY (emp_no) REFERENCES employees(emp_no) ON DELETE CASCADE

```
