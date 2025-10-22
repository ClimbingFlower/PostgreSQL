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
SELECT * FROM person WHERE date_of_birth BETWEEN DATE '2002-01-01' AND '2002-01-01';
```














 
