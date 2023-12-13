# DDL exercise 2
Creating Tables with Null and Not Null Constraints:
Create a table named Books with the following columns:

book_id (integer)
title (varchar, maximum length 100, not null)
author (varchar, maximum length 50)
genre (varchar, maximum length 50)
publish_date (date, not null)
Ensure that title and publish_date columns do not allow NULL values, while author and genre columns can have NULL values.

```SQL
CREATE TABLE books(book_id INT, title VARCHAR(100) NOT NULL, author VARCHAR(50), genre VARCHAR(50), publish_date DATE NOT NULL);
DESCRIBE books;

+--------------+--------------+------+-----+---------+-------+
| Field        | Type         | Null | Key | Default | Extra |
+--------------+--------------+------+-----+---------+-------+
| book_id      | int          | YES  |     | NULL    |       |
| title        | varchar(100) | NO   |     | NULL    |       |
| author       | varchar(50)  | YES  |     | NULL    |       |
| genre        | varchar(50)  | YES  |     | NULL    |       |
| publish_date | date         | NO   |     | NULL    |       |
+--------------+--------------+------+-----+---------+-------+
5 rows in set (0.00 sec)
```

Altering Tables with Not Null Constraints:
Alter the Books table to modify the author column to not allow NULL values.

```SQL
ALTER TABLE books MODIFY COLUMN author VARCHAR(50) NOT NULL;
DESCRIBE books;

+--------------+--------------+------+-----+---------+-------+
| Field        | Type         | Null | Key | Default | Extra |
+--------------+--------------+------+-----+---------+-------+
| book_id      | int          | YES  |     | NULL    |       |
| title        | varchar(100) | NO   |     | NULL    |       |
| author       | varchar(50)  | NO   |     | NULL    |       |
| genre        | varchar(50)  | YES  |     | NULL    |       |
| publish_date | date         | NO   |     | NULL    |       |
+--------------+--------------+------+-----+---------+-------+
5 rows in set (0.00 sec)
```
Dropping Tables:
Create a new table named Employees with the following columns:

employee_id (integer)
employee_name (varchar, maximum length 50, not null)
department (varchar, maximum length 50)
salary (decimal)
Then, drop the Employees table.

```SQL
 CREATE TABLE employees(employee_id INT, employee_name VARCHAR(50) NOT NULL, department VARCHAR(50), salary DECIMAL);
 DESCRIBE employees;
+---------------+---------------+------+-----+---------+-------+
| Field         | Type          | Null | Key | Default | Extra |
+---------------+---------------+------+-----+---------+-------+
| employee_id   | int           | YES  |     | NULL    |       |
| employee_name | varchar(50)   | NO   |     | NULL    |       |
| department    | varchar(50)   | YES  |     | NULL    |       |
| salary        | decimal(10,0) | YES  |     | NULL    |       |
+---------------+---------------+------+-----+---------+-------+

SHOW TABLES;

+----------------+
| Tables_in_mydb |
+----------------+
| books          |
| diningspots    |
| employees      |
| events         |
| movies         |
| users          |
| users2         |
+----------------+

DROP TABLE employees;

SHOW TABLES;
+----------------+
| Tables_in_mydb |
+----------------+
| books          |
| diningspots    |
| events         |
| movies         |
| users          |
| users2         |
+----------------+
```
