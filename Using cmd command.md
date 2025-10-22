### Using cmd command to control PostgreSQL
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

3. How to create table with Postgres
```
CREATE TABLE person (
  id int,
  first_name VARCHAR(50),
  last_name VARCHAR(50),
  gender VARCHAR(6),
  data_of_birth TIMESTAMP,
);
```
