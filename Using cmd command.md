### Using cmd command to control PostgreSQL
<br>

0. Clear Screen
```
\! cls
```
<br><br>
1. PostgreSQL Documentation
```
http://www.postgres.cn/docs/current/index.html
```
<br><br>
2. Sign in
```
psql -h 127.0.0.1 -p 5432 -U postgres
```
<br><br>
3. How to create/delete database
```
CREATE DATABASE [Name];
DROP DATABASE [Name];
```
<br><br>
4. How to create table with Postgres
```
CREATE TABLE person (
  id int,
  first_name VARCHAR(50),
  last_name VARCHAR(50),
  gender VARCHAR(6),
  data_of_birth TIMESTAMP,
);
```
<br><br>
5. How to insert records into tables
```
INSERT INTO person (
  first_name,
  last_name,
  gender,
  data_of_birth)
VALUES ('Anne', 'Smith', 'FEMALE', DATE'1988-01-09');
```
```
INSERT INTO person (
  first_name,
  last_name,
  gender,
  data_of_birth,
  email)
VALUES ('Jake', 'Jones', 'MALE', DATE'1990-01-10', 'Jake@gmail.com');
```
<br><br>
5. How to select rows from a table
```
# SELECT [Row Name] From person;
SELECT first_name FROM person;
```
<br><br>
6. How to sort our data using the order by keyword
```
SELECT * FROM person ORDER BY country_of_birth ASC/DESC;
```
<br><br>
7. How to select distinct row from a table (order)
```
SELECT DISTINCT country_of_birth FROM person ORDER BY country_of_birth ASC/DESC;
```
<br><br>
8. How to use 'WHERE' cluase
```
SELECT * FROM person WHERE gender = 'Female';
SELECT * FROM person WHERE gender = 'Male' and (country_of_birth = 'China' OR country_of_birth = 'Japan');
```
<br><br>
9. How to use 'Limit, Offset, and Fetch'
```
SELECT * FROM person LIMIT 10;
SELECT * FROM person OFFSET 5 LIMIT 10;
SELECT * FROM person OFFSET 5; ;
SELECT * FROM person OFFSET 5 FETCH FIRST 3 ROW ONLY;
```
<br><br>
10. How to use 'In'
```
SELECT * FROM person WHERE country_of_birth IN ('Japan', 'Serbia', 'France');
SELECT * FROM person WHERE country_of_birth IN ('Japan', 'Serbia', 'France') ORDER BY country_of_birth;
```
<br><br>
11. How to use 'Between'
```
SELECT * FROM person WHERE date_of_birth BETWEEN DATE '2002-01-01' AND '2002-12-31';
SELECT * FROM person WHERE date_of_birth BETWEEN DATE '2002-01-01' AND '2002-12-31' ORDER BY date_of_birth;
```
<br><br>
12. How to use 'Like and iLike'
```
SELECT * FROM person WHERE email LIKE '%.com';
SELECT * FROM person WHERE email LIKE '%bloomber.com';
SELECT * FROM person WHERE email LIKE '%google%';
SELECT * FROM person WHERE email LIKE '________@%';
/* eight '_' */
SELECT * FROM person WHERE country_of_birth ILIKE 'p%';
```
<br><br>
13. How to use 'Group by'

This is very powerful, and basically allows us to group our data based on a column.
```
SELECT country_of_birth, COUNT(*) FROM person GROUP BY country_of_birth;
SELECT country_of_birth, COUNT(*) FROM person GROUP BY country_of_birth ORDER BY COUNT DESC;
```
<br><br>
14. How to use 'Group having'
```
SELECT country_of_birth, COUNT(*) FROM person GROUP BY country_of_birth HAVING COUNT(*) >= 30 ORDER BY country_of_birth;
```
<br><br>
15. How to use 'Min, Max, and Average'
```
SELECT MAX(price) FROM car;
SELECT MIN(price) FROM car;
SELECT AVG(price) FROM car;
SELECT ROUND(AVG(price)) FROM car;
SELECT make, model, MAX(price), MIN(price) FROM car GROUP BY make, model;
```
<br><br>
16. How to use 'Sum'
```
SELECT SUM(price) FROM car;
SELECT make, SUM(price) FROM car GROUP BY make;
```
<br><br>
17. Some of the arithmetic operators provided by Postgres
```
SELECT id, make, model, price, ROUND(price * .10, 2) FROM car;
SELECT id, make, model, price, ROUND(price * .10, 2), ROUND(price - (price * .10), 2) FROM car;
```
<br><br>
18. use 'Alias'
```
SELECT id, make, model, price AS original_price, ROUND(price * .10, 2) AS ten_percent, ROUND(price - (price * .10), 2) AS discount_after_10_percent FROM car;
```
<br><br>
19. How to use 'Coalesce'?<br>
在table: person中，有许多成员的email项空缺，我们可以使用'Coalesce'为其填充内容为'Email not provided'
```
SELECT COALESCE(null, 1) AS number;
SELECT COALESCE(email, 'Email not provided') FROM person;
```
<br><br>
20. How to use 'Nullif'
```
SELECT NULLIF(10, 1);
```
<br><br>
21. How to use 'Timestamps and Dates', 'Adding and Substraction with Dates'
```
SELECT NOW(); # 展示当前时间
SELECT NOW()::DATE;
SELECT NOW()::TIME;
SELECT NOW() - INTERVAL '1 YEAR'; # 回到一年前
SELECT NOW() - INTERVAL '20 YEAR'; # 回到20年前
SELECT NOW() - INTERVAL '3 MONTHS'; # 回到3个月前
# day/days, year/years both work
```
<br><br>
22. How to use 'Extracting Fields'<br>
It allow us to extract specific values from a date.
```
SELECT EXTRACT(CENTURY FROM NOW());
SELECT EXTRACT(YEAR FROM NOW());
SELECT EXTRACT(MONTH FROM NOW());
SELECT EXTRACT(DAY FROM NOW());
```















































 
