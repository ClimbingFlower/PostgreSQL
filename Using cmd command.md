### Using cmd command to control PostgreSQL
<br>

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














 
