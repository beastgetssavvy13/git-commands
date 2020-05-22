## The Pixelated Coder  :man_technologist:

> Contributor : Kavish Pandit 

<H2>SQL JOURNEY</H2>
============
## :busts_in_silhouette: Author
- [Kavish Pandit](https://github.com/beastgetsssavvy13)

_My journey of 10000 lines of sql commands using 3 databases_

### DATABASED INVOLVED 

_DataBases : School | Company | OnlineShop_

_Tables : School :? Students | teachers | subjects_

_Tables : Company :? Employess | Clients  | Projects_

_Tables : Onlineshop :? Items | Categories | Customers |Orders_


### Basic Snapshotting
mysql> CREATE USER 'admin' IDENTIFIED BY 'password1234';

Query OK, 0 rows affected (0.02 sec)
//CHANGE PASSWORD

mysql> ALTER USER 'admin' IDENTIFIED BY 'php1234';
Query OK, 0 rows affected (0.01 sec)

//GRANT ALL PRIVELLEGES TO ALL DB (*) ALL TABLES (*) TO THE USER 'ADMIN' WITH USER CAN SET PRIVELLEGES AND NEW USER

mysql> GRANT ALL ON *.* TO 'admin' WITH GRANT OPTION;
Query OK, 0 rows affected (0.02 sec)
//PRIVILEGES TO TAKE PLACE

mysql> FLUSH PRIVILEGES;

//EXIT TO LOG IN TO ADMIN

Microsoft Windows [Version 10.0.18362.836]
(c) 2019 Microsoft Corporation. All rights reserved.

C:\Users\ASUS>cd C:\Program Files\MySQL\MySQL Server 8.0\bin

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u admin -p

Enter password: *******

Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> SHOW DATABASES;

+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.08 sec)
mysql> CREATE DATABASE school;
Query OK, 1 row affected (0.01 sec)

mysql> SHOW DATABASES;

+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| school             |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

/// Clear the Screen
system cls;

//see the column

+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| school             |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> use school;
Database changed
mysql> use sql;
ERROR 1049 (42000): Unknown database 'sql'
mysql> use mysql;
Database changed
mysql> select user from user;
+------------------+
| user             |
+------------------+
| admin            |
| mysql.infoschema |
| mysql.session    |
| mysql.sys        |
| root             |
+------------------+
5 rows in set (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| school             |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> use school;
Database changed

mysql> use sql;

ERROR 1049 (42000): Unknown database 'sql'

mysql> use mysql;
Database changed
mysql> select user from user;
+------------------+
| user             |
+------------------+
| admin            |
| mysql.infoschema |
| mysql.session    |
| mysql.sys        |
| root             |
+------------------+
5 rows in set (0.00 sec)

mysql> use school
Database changed
mysql> show tables;
Empty set (0.00 sec)

mysql> create table students (
    -> id INT NOT NULL PRIMARY KEY,
    -> firstname VARCHAR(40) NOT NULL,
    -> lastname VARCHAR(40) NOT NULL,
    -> class VARCHAR(40) NOT NULL,
    -> age INT
    -> );
Query OK, 0 rows affected (0.07 sec)

mysql> DESC STUDENTS;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| id        | int         | NO   | PRI | NULL    |       |
| firstname | varchar(40) | NO   |     | NULL    |       |
| lastname  | varchar(40) | NO   |     | NULL    |       |
| class     | varchar(40) | NO   |     | NULL    |       |
| age       | int         | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
5 rows in set (0.05 sec)

mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
+------------------+
1 row in set (0.00 sec)

mysql> DROP TABLE students;
Query OK, 0 rows affected (0.04 sec)

mysql> SHOW TABLES;
Empty set (0.00 sec)

mysql> DESC STUDENTS;
ERROR 1146 (42S02): Table 'school.students' doesn't exist

mysql> CREATE DATABASE school;
ERROR 1007 (HY000): Can't create database 'school'; database exists
mysql> USE SCHOOL;
Database changed
mysql> SHOW TABLES;
Empty set (0.00 sec)

mysql> CREATE TABLE students (
    -> id INT NOT NULL PRIMARY KEY,
    -> firstname VARCHAR(40) NOT NULL,
    -> lastname VARCHAR(40) NOT NULL,
    -> class VARCHAR(40) NOT NULL,
    -> age INT,
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ')' at line 7
mysql> CREATE TABLE students (
    -> id INT NOT NULL PRIMARY KEY,
    -> firstname VARCHAR(40) NOT NULL,
    -> lastname VARCHAR(40) NOT NULL,
    -> class VARCHAR(40) NOT NULL,
    -> age INT
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
+------------------+
1 row in set (0.00 sec)

mysql> DESC STUDENTS;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| id        | int         | NO   | PRI | NULL    |       |
| firstname | varchar(40) | NO   |     | NULL    |       |
| lastname  | varchar(40) | NO   |     | NULL    |       |
| class     | varchar(40) | NO   |     | NULL    |       |
| age       | int         | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
5 rows in set (0.00 sec)

mysql> INSERT INTO students VALUES (1,'JOHN','SMITH','FIRST',5);
Query OK, 1 row affected (0.02 sec)

mysql> SELECT * FROM STUDENTS;
+----+-----------+----------+-------+------+
| id | firstname | lastname | class | age  |
+----+-----------+----------+-------+------+
|  1 | JOHN      | SMITH    | FIRST |    5 |
+----+-----------+----------+-------+------+
1 row in set (0.00 sec)

mysql> INSERT INTO students (id,firstname,lastname,class,age) VALUES (2,'MIKA','SMITH','FIRST',15);
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM STUDENTS;
+----+-----------+----------+-------+------+
| id | firstname | lastname | class | age  |
+----+-----------+----------+-------+------+
|  1 | JOHN      | SMITH    | FIRST |    5 |
|  2 | MIKA      | SMITH    | FIRST |   15 |
+----+-----------+----------+-------+------+
2 rows in set (0.00 sec)

mysql> INSERT INTO students (id,firstname,lastname,class,age) VALUES (2,'MIKA','SMITH','FIRST',15);
ERROR 1062 (23000): Duplicate entry '2' for key 'students.PRIMARY'
mysql> INSERT INTO students (id,firstname,lastname,class,age) VALUES
    -> (3,'FAISAL','SHAH','THIRD',34);
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM STUDENTS;
+----+-----------+----------+-------+------+
| id | firstname | lastname | class | age  |
+----+-----------+----------+-------+------+
|  1 | JOHN      | SMITH    | FIRST |    5 |
|  2 | MIKA      | SMITH    | FIRST |   15 |
|  3 | FAISAL    | SHAH     | THIRD |   34 |
+----+-----------+----------+-------+------+
3 rows in set (0.00 sec)

TWO TYPES OF SQL STATEMENTS;
1.Data Definition Language;
2.Data Manipulation Language;

DDL and DML both are SQL statements;
DDL changes the database structure while DML changes only the data.

Data Definition Language;

Manage database objects like tables and columns;
 Changes the database structure;
 Tables and column are created modified or removed
 CREATE,ALTER AND DROP
 
Data Mainpulation Language;

Manage the data that resides in our tables and columns;
 Changes only the data;
 Data inside a table is inserted updated or deleted
 INSERT UPDATE AND DELETE
 
 ///DataBases : School | Company | OnlineShop
 ///Tables : School :? Students | teachers | subjects
 ///Tables : Company :? Employess | Clients  | Projects
 /// Tables : Onlineshop :? Items | Categories | Customers |Orders
  
 mysql> CREATE DATABASE school;
ERROR 1007 (HY000): Can't create database 'school'; database exists
mysql> CREATE DATABASE company;
Query OK, 1 row affected (0.01 sec)

mysql> CREATE DATABASE onlineshop;
Query OK, 1 row affected (0.01 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| company            |
| information_schema |
| mysql              |
| onlineshop         |
| performance_schema |
| school             |
| sys                |
+--------------------+
7 rows in set (0.00 sec)

### Creating DATABASES

mysql> USE school;
Database changed
mysql> CREATE TABLE students (
    -> studentid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> firstname VARCHAR(40) NOT NULL,
    -> lastname VARCHAR(40) NOT NULL,
    -> class VARCHAR(20),
    -> age INT(3)
    -> );
Query OK, 0 rows affected, 1 warning (0.06 sec)

mysql> CREATE TABLE teachers (
    -> teacherid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> name VARCHAR(80) NOT NULL,
    -> phone VARCHAR(10)
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> CREATE TABLE subjects (
    -> subjectid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> title VARCHAR(50) NOT NULL
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> show tables;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| subjects         |
| teachers         |
+------------------+
3 rows in set (0.01 sec)

mysql> USE company;
Database changed
mysql> CREATE TABLE employees (
    -> employeeid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> name VARCHAR(80) NOT NULL,
    -> jobtitle VARCHAR(50) NOT NULL,
    -> salary FLOAT
    -> );
Query OK, 0 rows affected (0.05 sec)

mysql> CREATE TABLE clients (
    -> clientid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> name VARCHAR(80) NOT NULL,
    -> phone VARCHAR(15),
    -> address VARCHAR(150)
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> CREATE TABLE projects (
    -> projectid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> title VARCHAR(200) NOT NULL,
    -> clientid INT,
    -> employeeid INT,
    -> startdate DATETIME,
    -> enddate DATETIME
    -> );
Query OK, 0 rows affected (0.05 sec)

mysql> show tables;
+-------------------+
| Tables_in_company |
+-------------------+
| clients           |
| employees         |
| projects          |
+-------------------+
3 rows in set (0.01 sec)

mysql> use onlineshop;
Database changed
mysql> CREATE TABLE items (
    -> itemid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> categoryid INT,
    -> name VARCHAR(100) NOT NULL,
    -> price FLOAT
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> CREATE TABLE categories (
    -> categoryid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> title VARCHAR(50) NOT NULL,
    -> status TINYINT(1) NOT NULL
    -> );
Query OK, 0 rows affected, 1 warning (0.05 sec)

mysql> CREATE TABLE customers (
    -> userid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> name VARCHAR(80) NOT NULL,
    -> phone VARCHAR(15),
    -> address VARCHAR(150)
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> CREATE TABLE orders (
    -> orderid INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    -> userid INT,
    -> items TEXT,
    -> total FLOAT,
    -> orderdate DATETIME
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> show tables;
+----------------------+
| Tables_in_onlineshop |
+----------------------+
| categories           |
| customers            |
| items                |
| orders               |
+----------------------+
4 rows in set (0.00 sec)

### Updating Data Values

mysql> use school;
Database changed
mysql> INSERT INTO students (firstname, lastname, class, age) VALUES
    -> ('John', 'Doe', 'First', 5),
    -> ('Mary', 'Smith', 'Third', 7),
    -> ('James', 'Brown', 'First', 5),
    -> ('Mike', 'Walker', 'Second', 6),
    -> ('Linda', 'Jones', 'Third', 7),
    -> ('John', 'Doe', 'Third', 7),
    -> ('James', 'Smith', 'First', 6),
    -> ('John', 'Brown', 'Second', 6),
    -> ('Daniel', 'Jones', 'First', 7),
    -> ('Paul', 'Anderson', 'Third', 5),
    -> ('Mark', 'Davis', 'Second', 6),
    -> ('Steven', 'Thomas', 'First', 7),
    -> ('Brian', 'King', 'Second', 5),
    -> ('Kevin', 'Hall', 'First', 6),
    -> ('Jason', 'Lee', 'Third', 5),
    -> ('Jose', 'Young', 'First', 6),
    -> ('Frank', 'Smith', 'First', 7),
    -> ('Eric', 'Jones', 'Second', 7),
    -> ('Jerry', 'Martin', 'Third', 5),
    -> ('Peter', 'King', 'First', 6),
    -> ('Henry', 'Clark', 'Second', 7),
    -> ('Carl', 'White', 'Second', 5),
    -> ('Joe', 'Thomas', 'First', 7),
    -> ('Jack', 'Smith', 'Third', 6),
    -> ('Roy', 'King', 'Second', 5),
    -> ('Adam', 'Hall', 'First', 6),
    -> ('Bobby', 'White', 'Second', 7),
    -> ('Johnny', 'Davis', 'First', 6),
    -> ('Jimmy', 'Jones', 'Third', 5),
    -> ('Emma', 'Walker', 'First', 5),
    -> ('Sophia', 'Walker', 'Third', 6),
    -> ('Ava', 'Jones', 'First', 7),
    -> ('Mia', 'Smith', 'Second', 6),
    -> ('Emily', 'Walker', 'Second', 5),
    -> ('Grace', 'King', 'First', 5),
    -> ('Lillian', 'Jones', 'Third', 7),
    -> ('Lily', 'King', 'Third', 6),
    -> ('Layla', 'Young', 'First', 5),
    -> ('Zoe', 'Thomas', 'Second', 7),
    -> ('Anna', 'Jones', 'Second', 5),
    -> ('Leah', 'Brown', 'Third', 6),
    -> ('Camila', 'Hall', 'First', 5),
    -> ('Riley', 'Martin', 'Third', 6),
    -> ('Nora', 'Smith', 'Second', 7),
    -> ('Hailey', 'Clark', 'Second', 7),
    -> ('Ellie', 'King', 'Third', 5),
    -> ('Lucy', 'Jones', 'Third', 6),
    -> ('Stella', 'White', 'First', 5),
    -> ('Bella', 'White', 'Second', 7),
    -> ('Mila', 'Smith', 'Third', 6),
    -> ('Maya', 'Brown', 'First', 5),
    -> ('Faith', 'Thomas', 'Third', 5),
    -> ('Eva', 'Brown', 'Second', 7),
    -> ('Julia', 'King', 'Third', 6),
    -> ('Ashley', 'Davis', 'First', 5),
    -> ('Ruby', 'Young', 'Third', 7),
    -> ('Alice', 'Jones', 'Second', 6),
    -> ('Jasmine', 'Hall', 'Third', 7);
Query OK, 58 rows affected (0.02 sec)
Records: 58  Duplicates: 0  Warnings: 0

mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> INSERT INTO teachers (name, phone) VALUES
    -> ('John Doe', '1234567890'),
    -> ('Caroline Smith', '0987654321'),
    -> ('Jason King', '1234512345'),
    -> ('Stella Brown', '0987612345'),
    -> ('Eric Hall', '0987609876');
Query OK, 5 rows affected (0.01 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM teachers;
+-----------+----------------+------------+
| teacherid | name           | phone      |
+-----------+----------------+------------+
|         1 | John Doe       | 1234567890 |
|         2 | Caroline Smith | 0987654321 |
|         3 | Jason King     | 1234512345 |
|         4 | Stella Brown   | 0987612345 |
|         5 | Eric Hall      | 0987609876 |
+-----------+----------------+------------+
5 rows in set (0.00 sec)

mysql> INSERT INTO subjects (title) VALUES ('English'), ('Mathematics'), ('Science'), ('Computer'), ('History'), ('Geography');
Query OK, 6 rows affected (0.01 sec)
Records: 6  Duplicates: 0  Warnings: 0

mysql> select * from subjects;
+-----------+-------------+
| subjectid | title       |
+-----------+-------------+
|         1 | English     |
|         2 | Mathematics |
|         3 | Science     |
|         4 | Computer    |
|         5 | History     |
|         6 | Geography   |
+-----------+-------------+
6 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> INSERT INTO employees (name, jobtitle, salary) VALUES
    -> ('John Doe', 'Web Developer', 3500.00),
    -> ('Mary Smith', 'Web Developer', 3500.00),
    -> ('James Brown', 'Web Developer', 3500.00),
    -> ('Mike Walker', 'Web Developer', 3500.00),
    -> ('Linda Jones', 'Web Developer', 3500.00),
    -> ('John Doe', 'Systems Administrator', 3400.00),
    -> ('James Smith', 'Systems Administrator', 3400.00),
    -> ('John Brown', 'Systems Administrator', 3400.00),
    -> ('Daniel Jones', 'Systems Administrator', 3400.00),
    -> ('Paul Anderson', 'Systems Administrator', 3400.00),
    -> ('Mark Davis', 'IT Support Manager', 3200.00),
    -> ('Steven Thomas', 'IT Support Manager', 3200.00),
    -> ('Brian King', 'IT Support Manager', 3200.00),
    -> ('Kevin Hall', 'IT Support Manager', 3200.00),
    -> ('Jason Lee', 'IT Support Manager', 3200.00),
    -> ('Jose Young', 'Database Administrator', 3700.00),
    -> ('Frank Smith', 'Database Administrator', 3700.00),
    -> ('Eric Jones', 'Database Administrator', 3700.00),
    -> ('Jerry Martin', 'Database Administrator', 3700.00),
    -> ('Peter King', 'Database Administrator', 3700.00),
    -> ('Henry Clark', 'Application Developer', 3800.00),
    -> ('Carl White', 'Application Developer', 3800.00),
    -> ('Joe Thomas', 'Application Developer', 3800.00),
    -> ('Jack Smith', 'Application Developer', 3800.00),
    -> ('Roy King', 'Application Developer', 3800.00);
Query OK, 25 rows affected (0.01 sec)
Records: 25  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM employees;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> INSERT INTO clients (name, phone, address) VALUES
    -> ('Jimmy Jones', '1234567890', 'Victoria Pavilion, Las Vegas, NV'),
    -> ('Henry Clark', '0987654321', '4125 Sydney Place, Miami, FL'),
    -> ('Ruby Young', '1234512345', '6170 Peshwar Place, Washington, DC'),
    -> ('Julia King', '0987612345', 'MountainView Hospital, Victoria, TX');
Query OK, 4 rows affected (0.01 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql>
mysql> select * from clients;
+----------+-------------+------------+-------------------------------------+
| clientid | name        | phone      | address                             |
+----------+-------------+------------+-------------------------------------+
|        1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|        2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|        3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|        4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
+----------+-------------+------------+-------------------------------------+
4 rows in set (0.00 sec)

mysql> INSERT INTO projects ( title, clientid, employeeid, startdate, enddate) VALUES
    -> ('Develop ecommerse website from scratch', 1, 3, NOW(), DATE_ADD(NOW(), INTERVAL 30 DAY)),
    -> ('WordPress website for our company', 1, 2, NOW(), DATE_ADD(NOW(), INTERVAL 45 DAY)),
    -> ('Manage our company servers', 2, 7, NOW(), DATE_ADD(NOW(), INTERVAL 45 DAY)),
    -> ('Hosting account is not working', 3, 9, NOW(), DATE_ADD(NOW(), INTERVAL 7 DAY)),
    -> ('MySQL database from my desktop application', 4, 17, NOW(), DATE_ADD(NOW(), INTERVAL 15 DAY)),
    -> ('Develop new WordPress plugin for my business website', 2, NULL, NOW(), DATE_ADD(NOW(), INTERVAL 10 DAY)),
    -> ('Migrate web application and database to new server', 2, NULL, NOW(), DATE_ADD(NOW(), INTERVAL 5 DAY)),
    -> ('Android Application development', 4, 23, NOW(), DATE_ADD(NOW(), INTERVAL 30 DAY));
Query OK, 8 rows affected (0.01 sec)
Records: 8  Duplicates: 0  Warnings: 0

mysql> select * from projects;
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
| projectid | title                                                | clientid | employeeid | startdate           | enddate             |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
|         1 | Develop ecommerse website from scratch               |        1 |          3 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
|         2 | WordPress website for our company                    |        1 |          2 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         3 | Manage our company servers                           |        2 |          7 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         4 | Hosting account is not working                       |        3 |          9 | 2020-05-20 11:33:43 | 2020-05-27 11:33:43 |
|         5 | MySQL database from my desktop application           |        4 |         17 | 2020-05-20 11:33:43 | 2020-06-04 11:33:43 |
|         6 | Develop new WordPress plugin for my business website |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-30 11:33:43 |
|         7 | Migrate web application and database to new server   |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-25 11:33:43 |
|         8 | Android Application development                      |        4 |         23 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
8 rows in set (0.00 sec)

mysql> USE onlineshop;
Database changed
mysql> INSERT INTO categories (title, status) VALUES ('Electronics', 1), ('Books', 1), ('Cloths', 1);
Query OK, 3 rows affected (0.05 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from categories;
+------------+-------------+--------+
| categoryid | title       | status |
+------------+-------------+--------+
|          1 | Electronics |      1 |
|          2 | Books       |      1 |
|          3 | Cloths      |      1 |
+------------+-------------+--------+
3 rows in set (0.00 sec)

mysql> INSERT INTO items (categoryid, name, price) VALUES
    -> (1, 'Android Mobile Phone', 250.00),
    -> (1, 'i7 processor, 8GB RAM Laptop', 1000.00),
    -> (2, 'How to train your cat', 25.00),
    -> (2, 'Healthy dog food recipes', 19.00),
    -> (2, 'Learn how to meditate for mental health', 30.00),
    -> (3, 'Beautiful Black T-Shirts', 99.00),
    -> (3, 'Blue Colored Jeans', 150.00);
Query OK, 7 rows affected (0.01 sec)
Records: 7  Duplicates: 0  Warnings: 0

mysql> select * from items;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+
7 rows in set (0.00 sec)

mysql> INSERT INTO customers (name, phone, address) VALUES
    -> ('Jimmy Jones', '1234567890', 'Victoria Pavilion, Las Vegas, NV'),
    -> ('Henry Clark', '0987654321', '4125 Sydney Place, Miami, FL'),
    -> ('Ruby Young', '1234512345', '6170 Peshwar Place, Washington, DC'),
    -> ('Julia King', '0987612345', 'MountainView Hospital, Victoria, TX'),
    -> ('Anna Jones', '0987609876', '1234 Obere Street, Miami, FL');
Query OK, 5 rows affected (0.01 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM customers;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.00 sec)

mysql> INSERT INTO orders (userid, items, total, orderdate) VALUES
    -> (2, 'i7 processor, 8GB RAM Laptop', 1000.00, NOW()),
    -> (1, 'Healthy dog food recipes', 19.00, NOW()),
    -> (25, 'Healthy dog food recipes', 19.00, NOW()),
    -> (1, 'How to train your cat', 25.00, NOW()),
    -> (3, 'Blue Colored Jeans', 150.00, NOW()),
    -> (15, 'Beautiful Black T-Shirts', 99.00, NOW()),
    -> (4, 'Beautiful Black T-Shirts', 99.00, NOW());
Query OK, 7 rows affected (0.01 sec)
Records: 7  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM orders;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

//// where clause and from clause importance in school and company databases;

### Handling Subqueries

mysql> select * from students where studentid=6;
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|         6 | John      | Doe      | Third |    7 |
+-----------+-----------+----------+-------+------+
1 row in set (0.00 sec)

mysql> select * from students where firstname='John';
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         6 | John      | Doe      | Third  |    7 |
|         8 | John      | Brown    | Second |    6 |
+-----------+-----------+----------+--------+------+
3 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees where jobtitle ='Application Developer';
+------------+-------------+-----------------------+--------+
| employeeid | name        | jobtitle              | salary |
+------------+-------------+-----------------------+--------+
|         21 | Henry Clark | Application Developer |   3800 |
|         22 | Carl White  | Application Developer |   3800 |
|         23 | Joe Thomas  | Application Developer |   3800 |
|         24 | Jack Smith  | Application Developer |   3800 |
|         25 | Roy King    | Application Developer |   3800 |
+------------+-------------+-----------------------+--------+
5 rows in set (0.00 sec)

/// where clause depends up on a condition which evaluates as either be true,false or unknown;

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select *  from students where studentid=6;
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|         6 | John      | Doe      | Third |    7 |
+-----------+-----------+----------+-------+------+
1 row in set (0.00 sec)

mysql> select *  from students where class='First';
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|         1 | John      | Doe      | First |    5 |
|         3 | James     | Brown    | First |    5 |
|         7 | James     | Smith    | First |    6 |
|         9 | Daniel    | Jones    | First |    7 |
|        12 | Steven    | Thomas   | First |    7 |
|        14 | Kevin     | Hall     | First |    6 |
|        16 | Jose      | Young    | First |    6 |
|        17 | Frank     | Smith    | First |    7 |
|        20 | Peter     | King     | First |    6 |
|        23 | Joe       | Thomas   | First |    7 |
|        26 | Adam      | Hall     | First |    6 |
|        28 | Johnny    | Davis    | First |    6 |
|        30 | Emma      | Walker   | First |    5 |
|        32 | Ava       | Jones    | First |    7 |
|        35 | Grace     | King     | First |    5 |
|        38 | Layla     | Young    | First |    5 |
|        42 | Camila    | Hall     | First |    5 |
|        48 | Stella    | White    | First |    5 |
|        51 | Maya      | Brown    | First |    5 |
|        55 | Ashley    | Davis    | First |    5 |
+-----------+-----------+----------+-------+------+
20 rows in set (0.00 sec)

mysql> use company ;
Database changed
mysql> select * from employees where salary =3700;
+------------+--------------+------------------------+--------+
| employeeid | name         | jobtitle               | salary |
+------------+--------------+------------------------+--------+
|         16 | Jose Young   | Database Administrator |   3700 |
|         17 | Frank Smith  | Database Administrator |   3700 |
|         18 | Eric Jones   | Database Administrator |   3700 |
|         19 | Jerry Martin | Database Administrator |   3700 |
|         20 | Peter King   | Database Administrator |   3700 |
+------------+--------------+------------------------+--------+
5 rows in set (0.00 sec)

/// where clause with false condition; 
/// <> not equal to and less than or greater than;

mysql> select * from students where NOT studentid =6;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
57 rows in set (0.00 sec)

mysql> select * from students where studentid <>6;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
57 rows in set (0.00 sec)

mysql> select * from students where class <> 'First';
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         2 | Mary      | Smith    | Third  |    7 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         8 | John      | Brown    | Second |    6 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        13 | Brian     | King     | Second |    5 |
|        15 | Jason     | Lee      | Third  |    5 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        27 | Bobby     | White    | Second |    7 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
38 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees where jobtitle <> 'Web Developer';
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
20 rows in set (0.00 sec)

///sql and operator;
'AND' AND '&&' AND WE ALSO USE 'AND NOT'
mysql> use school;
Database changed
mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> SELECT * FROM STUDENTS WHERE (CLASS='First'&& age=5);
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|         1 | John      | Doe      | First |    5 |
|         3 | James     | Brown    | First |    5 |
|        30 | Emma      | Walker   | First |    5 |
|        35 | Grace     | King     | First |    5 |
|        38 | Layla     | Young    | First |    5 |
|        42 | Camila    | Hall     | First |    5 |
|        48 | Stella    | White    | First |    5 |
|        51 | Maya      | Brown    | First |    5 |
|        55 | Ashley    | Davis    | First |    5 |
+-----------+-----------+----------+-------+------+
9 rows in set, 1 warning (0.00 sec)

mysql> SELECT * FROM STUDENTS WHERE (CLASS='First'AND age=5 && STUDENTID=3);
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|         3 | James     | Brown    | First |    5 |
+-----------+-----------+----------+-------+------+
1 row in set, 1 warning (0.00 sec)

mysql> SELECT * FROM STUDENTS WHERE (CLASS='First'AND NOT age=5);
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|         7 | James     | Smith    | First |    6 |
|         9 | Daniel    | Jones    | First |    7 |
|        12 | Steven    | Thomas   | First |    7 |
|        14 | Kevin     | Hall     | First |    6 |
|        16 | Jose      | Young    | First |    6 |
|        17 | Frank     | Smith    | First |    7 |
|        20 | Peter     | King     | First |    6 |
|        23 | Joe       | Thomas   | First |    7 |
|        26 | Adam      | Hall     | First |    6 |
|        28 | Johnny    | Davis    | First |    6 |
|        32 | Ava       | Jones    | First |    7 |
+-----------+-----------+----------+-------+------+
11 rows in set (0.00 sec)

mysql> SELECT * FROM STUDENTS WHERE (CLASS='First'AND age=5 && STUDENTID=4);
Empty set, 1 warning (0.00 sec)

mysql> USE ONLINESHOP'
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''' at line 1
mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM ITEMS;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM ITEMS WHERE (CATEGORYID=1 && PRICE=250);
+--------+------------+----------------------+-------+
| itemid | categoryid | name                 | price |
+--------+------------+----------------------+-------+
|      1 |          1 | Android Mobile Phone |   250 |
+--------+------------+----------------------+-------+
1 row in set, 1 warning (0.00 sec)

//OR OPERATOR 
 IF ANY CONDITION IS TRUE;
  'OR' AND '||'

mysql> USE SCHOOL;
Database changed
mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> SELECT * FROM STUDENTS WHERE (AGE=5 || AGE=7);
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        15 | Jason     | Lee      | Third  |    5 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        25 | Roy       | King     | Second |    5 |
|        27 | Bobby     | White    | Second |    7 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        32 | Ava       | Jones    | First  |    7 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        42 | Camila    | Hall     | First  |    5 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
39 rows in set, 1 warning (0.00 sec)

mysql> SELECT * FROM STUDENTS WHERE (AGE=10 || AGE=15);
Empty set, 1 warning (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT * FROM EMPLOYEES WHERE JOBTITLE='Web Developer'|| jobtitle='Application Developer';
+------------+-------------+-----------------------+--------+
| employeeid | name        | jobtitle              | salary |
+------------+-------------+-----------------------+--------+
|          1 | John Doe    | Web Developer         |   3500 |
|          2 | Mary Smith  | Web Developer         |   3500 |
|          3 | James Brown | Web Developer         |   3500 |
|          4 | Mike Walker | Web Developer         |   3500 |
|          5 | Linda Jones | Web Developer         |   3500 |
|         21 | Henry Clark | Application Developer |   3800 |
|         22 | Carl White  | Application Developer |   3800 |
|         23 | Joe Thomas  | Application Developer |   3800 |
|         24 | Jack Smith  | Application Developer |   3800 |
|         25 | Roy King    | Application Developer |   3800 |
+------------+-------------+-----------------------+--------+
10 rows in set, 1 warning (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM ITEMS;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM ITEMS where categoryid=1 || price=250;
+--------+------------+------------------------------+-------+
| itemid | categoryid | name                         | price |
+--------+------------+------------------------------+-------+
|      1 |          1 | Android Mobile Phone         |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop |  1000 |
+--------+------------+------------------------------+-------+
2 rows in set, 1 warning (0.00 sec)

// IN Operator
// written as word 'IN' FOLLOWED BY MUTLIPLE VALUES SEPERATED BY COMMA INSIDE BRACKETS;
//BETWEEN THE RANGE (MIN, MAX);
//BETWEEN THE RANGE (A,B,C,D); //GIVEN VALUES WILL BE DISPLAYED;

mysql> USE SCHOOL;
Database changed
mysql> SELECT * FROM STUDENTS WHERE AGE IN(5,6);
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        22 | Carl      | White    | Second |    5 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        57 | Alice     | Jones    | Second |    6 |
+-----------+-----------+----------+--------+------+
39 rows in set (0.00 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> SELECT * FROM STUDENTS WHERE AGE IN(7,8);
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         2 | Mary      | Smith    | Third  |    7 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         9 | Daniel    | Jones    | First  |    7 |
|        12 | Steven    | Thomas   | First  |    7 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        21 | Henry     | Clark    | Second |    7 |
|        23 | Joe       | Thomas   | First  |    7 |
|        27 | Bobby     | White    | Second |    7 |
|        32 | Ava       | Jones    | First  |    7 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        49 | Bella     | White    | Second |    7 |
|        53 | Eva       | Brown    | Second |    7 |
|        56 | Ruby      | Young    | Third  |    7 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
19 rows in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT * FROM EMPLOYEES WHERE SALARY IN(3200,3400);
+------------+---------------+-----------------------+--------+
| employeeid | name          | jobtitle              | salary |
+------------+---------------+-----------------------+--------+
|          6 | John Doe      | Systems Administrator |   3400 |
|          7 | James Smith   | Systems Administrator |   3400 |
|          8 | John Brown    | Systems Administrator |   3400 |
|          9 | Daniel Jones  | Systems Administrator |   3400 |
|         10 | Paul Anderson | Systems Administrator |   3400 |
|         11 | Mark Davis    | IT Support Manager    |   3200 |
|         12 | Steven Thomas | IT Support Manager    |   3200 |
|         13 | Brian King    | IT Support Manager    |   3200 |
|         14 | Kevin Hall    | IT Support Manager    |   3200 |
|         15 | Jason Lee     | IT Support Manager    |   3200 |
+------------+---------------+-----------------------+--------+
10 rows in set (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM ITEMS;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM ITEMS WHERE PRICE IN(19,25,30,99);
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
+--------+------------+-----------------------------------------+-------+
4 rows in set (0.00 sec)


THE EXISTS CONDITION IS VERY SIMILAR  TO 'IN ' CONDITION;
IN 'EXITS' WE CAN USE SUBQUERY WHILE 'IN' CONDITION HAVE CONSTANT VALUES TO EVALUATE;
IF THE SUBQUERY RETURN TRUE THE MAIN QUER IS FURTHER EVALUATED;


mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM PROJECTS;
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
| projectid | title                                                | clientid | employeeid | startdate           | enddate             |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
|         1 | Develop ecommerse website from scratch               |        1 |          3 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
|         2 | WordPress website for our company                    |        1 |          2 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         3 | Manage our company servers                           |        2 |          7 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         4 | Hosting account is not working                       |        3 |          9 | 2020-05-20 11:33:43 | 2020-05-27 11:33:43 |
|         5 | MySQL database from my desktop application           |        4 |         17 | 2020-05-20 11:33:43 | 2020-06-04 11:33:43 |
|         6 | Develop new WordPress plugin for my business website |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-30 11:33:43 |
|         7 | Migrate web application and database to new server   |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-25 11:33:43 |
|         8 | Android Application development                      |        4 |         23 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
8 rows in set (0.00 sec)

mysql> SELECT * FROM EMPLOYEES WHERE EXISTS (SELECT * FROM PROJECTS WHERE PROJECTS.EMPLOYEEID=EMPLOYEES.EMPLOYEEID)
    -> ;
+------------+--------------+------------------------+--------+
| employeeid | name         | jobtitle               | salary |
+------------+--------------+------------------------+--------+
|          3 | James Brown  | Web Developer          |   3500 |
|          2 | Mary Smith   | Web Developer          |   3500 |
|          7 | James Smith  | Systems Administrator  |   3400 |
|          9 | Daniel Jones | Systems Administrator  |   3400 |
|         17 | Frank Smith  | Database Administrator |   3700 |
|         23 | Joe Thomas   | Application Developer  |   3800 |
+------------+--------------+------------------------+--------+
6 rows in set (0.01 sec)

mysql> SELECT * FROM EMPLOYEES WHERE EXISTS (SELECT * FROM PROJECTS WHERE PROJECTS.EMPLOYEEID=EMPLOYEES.EMPLOYEEID AND PROJECTID=3);
+------------+-------------+-----------------------+--------+
| employeeid | name        | jobtitle              | salary |
+------------+-------------+-----------------------+--------+
|          7 | James Smith | Systems Administrator |   3400 |
+------------+-------------+-----------------------+--------+
1 row in set (0.00 sec)

mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM CUSTOMERS;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM ORDERS;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM CUSTOMERS WHERE EXISTS(SELECT * FROM ORDERS WHERE ORDERS.USERID=CUSTOMERS.USERID);
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
+--------+-------------+------------+-------------------------------------+
4 rows in set (0.00 sec)

mysql> SELECT * FROM CUSTOMERS WHERE EXISTS(SELECT * FROM ORDERS WHERE ORDERS.USERID=CUSTOMERS.USERID AND CUSTOMERID=7);
ERROR 1054 (42S22): Unknown column 'CUSTOMERID' in 'where clause'
mysql> SELECT * FROM CUSTOMERS WHERE EXISTS(SELECT * FROM ORDERS WHERE ORDERS.USERID=CUSTOMERS.USERID AND ORDERID=7);
+--------+------------+------------+-------------------------------------+
| userid | name       | phone      | address                             |
+--------+------------+------------+-------------------------------------+
|      4 | Julia King | 0987612345 | MountainView Hospital, Victoria, TX |
+--------+------------+------------+-------------------------------------+
1 row in set (0.00 sec)


// SQL NOT IN OR NOT EXISTS (NOT COMBINESS WITH IN AND EXISTS CONDITION) TO REVERT HE CONDITION;

NOT IN(A,B,C,D)
mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT * FROM EMPLOYEES WHERE SALARY NOT IN(3200,3500,3700,3800);
+------------+---------------+-----------------------+--------+
| employeeid | name          | jobtitle              | salary |
+------------+---------------+-----------------------+--------+
|          6 | John Doe      | Systems Administrator |   3400 |
|          7 | James Smith   | Systems Administrator |   3400 |
|          8 | John Brown    | Systems Administrator |   3400 |
|          9 | Daniel Jones  | Systems Administrator |   3400 |
|         10 | Paul Anderson | Systems Administrator |   3400 |
+------------+---------------+-----------------------+--------+
5 rows in set (0.00 sec)

///NOT EXISTS
mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM CUSTOMERS WHERE NOT EXISTS(SELECT * FROM ORDERS WHERE ORDERS.USERID=CUSTOMERS.USERID);
+--------+------------+------------+------------------------------+
| userid | name       | phone      | address                      |
+--------+------------+------------+------------------------------+
|      5 | Anna Jones | 0987609876 | 1234 Obere Street, Miami, FL |
+--------+------------+------------+------------------------------+
1 row in set (0.00 sec)

mysql> SELECT * FROM ORDERS;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM CUSTOMERS;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.00 sec)

//COMPARISON OPERATOR;
= EQUAL TO 
<> OR != Not Equal To;
< Less Than
> Greater Than
<= Less Than or Equal to
>= Greater Than or Equal to

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students where age<6;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         3 | James     | Brown    | First  |    5 |
|        10 | Paul      | Anderson | Third  |    5 |
|        13 | Brian     | King     | Second |    5 |
|        15 | Jason     | Lee      | Third  |    5 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        22 | Carl      | White    | Second |    5 |
|        25 | Roy       | King     | Second |    5 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        38 | Layla     | Young    | First  |    5 |
|        40 | Anna      | Jones    | Second |    5 |
|        42 | Camila    | Hall     | First  |    5 |
|        46 | Ellie     | King     | Third  |    5 |
|        48 | Stella    | White    | First  |    5 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        55 | Ashley    | Davis    | First  |    5 |
+-----------+-----------+----------+--------+------+
20 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> select * from employees where salary>3500;
+------------+--------------+------------------------+--------+
| employeeid | name         | jobtitle               | salary |
+------------+--------------+------------------------+--------+
|         16 | Jose Young   | Database Administrator |   3700 |
|         17 | Frank Smith  | Database Administrator |   3700 |
|         18 | Eric Jones   | Database Administrator |   3700 |
|         19 | Jerry Martin | Database Administrator |   3700 |
|         20 | Peter King   | Database Administrator |   3700 |
|         21 | Henry Clark  | Application Developer  |   3800 |
|         22 | Carl White   | Application Developer  |   3800 |
|         23 | Joe Thomas   | Application Developer  |   3800 |
|         24 | Jack Smith   | Application Developer  |   3800 |
|         25 | Roy King     | Application Developer  |   3800 |
+------------+--------------+------------------------+--------+
10 rows in set (0.00 sec)

mysql> use onlineshop;
Database changed
mysql> select * from items;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+
7 rows in set (0.00 sec)

mysql> select * from items where price <=30;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
+--------+------------+-----------------------------------------+-------+
3 rows in set (0.00 sec)

//like operator (Used with where clause to search for a specific pattern)

 The string pattern contains wildcars characters which represents missing characters
 % is wildcard character to assume the remaining character
 
 mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students where firstname like 'Jo%';
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         6 | John      | Doe      | Third  |    7 |
|         8 | John      | Brown    | Second |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        23 | Joe       | Thomas   | First  |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
+-----------+-----------+----------+--------+------+
6 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> select * from employees where name like '&s';
Empty set (0.00 sec)

mysql> select * from employees where name like '%s';
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          5 | Linda Jones   | Web Developer          |   3500 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
6 rows in set (0.00 sec)

mysql> use onlineshop;
Database changed
mysql> select * from customers where name like '%u%';
+--------+------------+------------+-------------------------------------+
| userid | name       | phone      | address                             |
+--------+------------+------------+-------------------------------------+
|      3 | Ruby Young | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King | 0987612345 | MountainView Hospital, Victoria, TX |
+--------+------------+------------+-------------------------------------+
2 rows in set (0.00 sec)

mysql> select * from customers where name not like '%u%';
+--------+-------------+------------+----------------------------------+
| userid | name        | phone      | address                          |
+--------+-------------+------------+----------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL     |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL     |
+--------+-------------+------------+----------------------------------+
3 rows in set (0.00 sec)


//between operator tests a range of values with a column value;

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students where age between 6 and 10;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         2 | Mary      | Smith    | Third  |    7 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        14 | Kevin     | Hall     | First  |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        41 | Leah      | Brown    | Third  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
38 rows in set (0.00 sec)

mysql> select * from students where age IN(6,10);
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         4 | Mike      | Walker   | Second |    6 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|        11 | Mark      | Davis    | Second |    6 |
|        14 | Kevin     | Hall     | First  |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        20 | Peter     | King     | First  |    6 |
|        24 | Jack      | Smith    | Third  |    6 |
|        26 | Adam      | Hall     | First  |    6 |
|        28 | Johnny    | Davis    | First  |    6 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        33 | Mia       | Smith    | Second |    6 |
|        37 | Lily      | King     | Third  |    6 |
|        41 | Leah      | Brown    | Third  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        50 | Mila      | Smith    | Third  |    6 |
|        54 | Julia     | King     | Third  |    6 |
|        57 | Alice     | Jones    | Second |    6 |
+-----------+-----------+----------+--------+------+
19 rows in set (0.00 sec)

mysql> select * from students where age IN(6,7);
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         2 | Mary      | Smith    | Third  |    7 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        14 | Kevin     | Hall     | First  |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        41 | Leah      | Brown    | Third  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
38 rows in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES WHERE SALARY BETWEEN (3000,3500);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> SELECT * FROM EMPLOYEES WHERE SALARY BETWEEN 3000 && 3500;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '&& 3500' at line 1
mysql> SELECT * FROM EMPLOYEES WHERE SALARY BETWEEN 3000 & 3500;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> SELECT * FROM EMPLOYEES WHERE SALARY BETWEEN 3000 AND 3500;
+------------+---------------+-----------------------+--------+
| employeeid | name          | jobtitle              | salary |
+------------+---------------+-----------------------+--------+
|          1 | John Doe      | Web Developer         |   3500 |
|          2 | Mary Smith    | Web Developer         |   3500 |
|          3 | James Brown   | Web Developer         |   3500 |
|          4 | Mike Walker   | Web Developer         |   3500 |
|          5 | Linda Jones   | Web Developer         |   3500 |
|          6 | John Doe      | Systems Administrator |   3400 |
|          7 | James Smith   | Systems Administrator |   3400 |
|          8 | John Brown    | Systems Administrator |   3400 |
|          9 | Daniel Jones  | Systems Administrator |   3400 |
|         10 | Paul Anderson | Systems Administrator |   3400 |
|         11 | Mark Davis    | IT Support Manager    |   3200 |
|         12 | Steven Thomas | IT Support Manager    |   3200 |
|         13 | Brian King    | IT Support Manager    |   3200 |
|         14 | Kevin Hall    | IT Support Manager    |   3200 |
|         15 | Jason Lee     | IT Support Manager    |   3200 |
+------------+---------------+-----------------------+--------+
15 rows in set (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM ITEMS WHERE PRICE BETWEEN 100 AND 1000;
+--------+------------+------------------------------+-------+
| itemid | categoryid | name                         | price |
+--------+------------+------------------------------+-------+
|      1 |          1 | Android Mobile Phone         |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop |  1000 |
|      7 |          3 | Blue Colored Jeans           |   150 |
+--------+------------+------------------------------+-------+
3 rows in set (0.00 sec)

//Numeric operator;
//(+)(-)(*)(/)

mysql> use school;
Database changed
mysql> select 10+15;
+-------+
| 10+15 |
+-------+
|    25 |
+-------+
1 row in set (0.00 sec)

mysql> select 10*15;
+-------+
| 10*15 |
+-------+
|   150 |
+-------+
1 row in set (0.00 sec)

mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select firstname,age+10 from students where age IN(5,6);
+-----------+--------+
| firstname | age+10 |
+-----------+--------+
| John      |     15 |
| James     |     15 |
| Mike      |     16 |
| James     |     16 |
| John      |     16 |
| Paul      |     15 |
| Mark      |     16 |
| Brian     |     15 |
| Kevin     |     16 |
| Jason     |     15 |
| Jose      |     16 |
| Jerry     |     15 |
| Peter     |     16 |
| Carl      |     15 |
| Jack      |     16 |
| Roy       |     15 |
| Adam      |     16 |
| Johnny    |     16 |
| Jimmy     |     15 |
| Emma      |     15 |
| Sophia    |     16 |
| Mia       |     16 |
| Emily     |     15 |
| Grace     |     15 |
| Lily      |     16 |
| Layla     |     15 |
| Anna      |     15 |
| Leah      |     16 |
| Camila    |     15 |
| Riley     |     16 |
| Ellie     |     15 |
| Lucy      |     16 |
| Stella    |     15 |
| Mila      |     16 |
| Maya      |     15 |
| Faith     |     15 |
| Julia     |     16 |
| Ashley    |     15 |
| Alice     |     16 |
+-----------+--------+
39 rows in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT * ,SALARY+50 FROM EMPLOYEES;
+------------+---------------+------------------------+--------+-----------+
| employeeid | name          | jobtitle               | salary | SALARY+50 |
+------------+---------------+------------------------+--------+-----------+
|          1 | John Doe      | Web Developer          |   3500 |      3550 |
|          2 | Mary Smith    | Web Developer          |   3500 |      3550 |
|          3 | James Brown   | Web Developer          |   3500 |      3550 |
|          4 | Mike Walker   | Web Developer          |   3500 |      3550 |
|          5 | Linda Jones   | Web Developer          |   3500 |      3550 |
|          6 | John Doe      | Systems Administrator  |   3400 |      3450 |
|          7 | James Smith   | Systems Administrator  |   3400 |      3450 |
|          8 | John Brown    | Systems Administrator  |   3400 |      3450 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |      3450 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |      3450 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |      3250 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |      3250 |
|         13 | Brian King    | IT Support Manager     |   3200 |      3250 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |      3250 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |      3250 |
|         16 | Jose Young    | Database Administrator |   3700 |      3750 |
|         17 | Frank Smith   | Database Administrator |   3700 |      3750 |
|         18 | Eric Jones    | Database Administrator |   3700 |      3750 |
|         19 | Jerry Martin  | Database Administrator |   3700 |      3750 |
|         20 | Peter King    | Database Administrator |   3700 |      3750 |
|         21 | Henry Clark   | Application Developer  |   3800 |      3850 |
|         22 | Carl White    | Application Developer  |   3800 |      3850 |
|         23 | Joe Thomas    | Application Developer  |   3800 |      3850 |
|         24 | Jack Smith    | Application Developer  |   3800 |      3850 |
|         25 | Roy King      | Application Developer  |   3800 |      3850 |
+------------+---------------+------------------------+--------+-----------+
25 rows in set (0.00 sec)
//conactenation operator;
// used only for strings
//"CONCAT" function

mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select concat(firstname,'',lastname) AS fullname from students;
+--------------+
| fullname     |
+--------------+
| JohnDoe      |
| MarySmith    |
| JamesBrown   |
| MikeWalker   |
| LindaJones   |
| JohnDoe      |
| JamesSmith   |
| JohnBrown    |
| DanielJones  |
| PaulAnderson |
| MarkDavis    |
| StevenThomas |
| BrianKing    |
| KevinHall    |
| JasonLee     |
| JoseYoung    |
| FrankSmith   |
| EricJones    |
| JerryMartin  |
| PeterKing    |
| HenryClark   |
| CarlWhite    |
| JoeThomas    |
| JackSmith    |
| RoyKing      |
| AdamHall     |
| BobbyWhite   |
| JohnnyDavis  |
| JimmyJones   |
| EmmaWalker   |
| SophiaWalker |
| AvaJones     |
| MiaSmith     |
| EmilyWalker  |
| GraceKing    |
| LillianJones |
| LilyKing     |
| LaylaYoung   |
| ZoeThomas    |
| AnnaJones    |
| LeahBrown    |
| CamilaHall   |
| RileyMartin  |
| NoraSmith    |
| HaileyClark  |
| EllieKing    |
| LucyJones    |
| StellaWhite  |
| BellaWhite   |
| MilaSmith    |
| MayaBrown    |
| FaithThomas  |
| EvaBrown     |
| JuliaKing    |
| AshleyDavis  |
| RubyYoung    |
| AliceJones   |
| JasmineHall  |
+--------------+
58 rows in set (0.00 sec)

//temporal operator 
//intervals are used while using date and time in sql

mysql> select current_date + interval 7 day as week;
+------------+
| week       |
+------------+
| 2020-05-27 |
+------------+
1 row in set (0.00 sec)

mysql> select current_date + interval 1 day as week;
+------------+
| week       |
+------------+
| 2020-05-21 |
+------------+
1 row in set (0.00 sec)

mysql> select current_date + interval 1 day as tommorow;
+------------+
| tommorow   |
+------------+
| 2020-05-21 |
+------------+
1 row in set (0.00 sec)

//Group By Clause
//group by clause groups the data together

//The from and where clause creates intermediate tabular result set and group by clause systematically 
groups the data
// The Group by clause can group the result set by onec or more columns
mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select class , count(*) from students group by class;
+--------+----------+
| class  | count(*) |
+--------+----------+
| First  |       20 |
| Third  |       20 |
| Second |       18 |
+--------+----------+
3 rows in set (0.01 sec)

mysql> select class , count(*) from students where class ='First' and group by class;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'group by class' at line 1
mysql> select class , count(*) from students where class ='First'  group by class;
+-------+----------+
| class | count(*) |
+-------+----------+
| First |       20 |
+-------+----------+
1 row in set (0.00 sec)

mysql> select age,count(*) from students group by age;
+------+----------+
| age  | count(*) |
+------+----------+
|    5 |       20 |
|    7 |       19 |
|    6 |       19 |
+------+----------+
3 rows in set (0.00 sec)

mysql> select age,count(*) from students GROUP BY age;
+------+----------+
| age  | count(*) |
+------+----------+
|    5 |       20 |
|    7 |       19 |
|    6 |       19 |
+------+----------+
3 rows in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT JOBTITLE,COUNT(*) FROM EMPLOYEES WHERE JOBTITLE='Web Developer' Group By JOBTITLE;
+---------------+----------+
| JOBTITLE      | COUNT(*) |
+---------------+----------+
| Web Developer |        5 |
+---------------+----------+
1 row in set (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM ITEMS;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+
7 rows in set (0.00 sec)

mysql> SELECT CATEGORYID,COUNT(*) AS 'TOTAL ITEMS' FROM ITEMS GROUP BY CATEGORYID;
+------------+-------------+
| CATEGORYID | TOTAL ITEMS |
+------------+-------------+
|          1 |           2 |
|          2 |           3 |
|          3 |           2 |
+------------+-------------+
3 rows in set (0.00 sec)

mysql> SELECT CATEGORYID,COUNT(*) AS 'TOTAL ITEMS' FROM ITEMS GROUP BY categoryid;
+------------+-------------+
| CATEGORYID | TOTAL ITEMS |
+------------+-------------+
|          1 |           2 |
|          2 |           3 |
|          3 |           2 |
+------------+-------------+
3 rows in set (0.00 sec)

//HAVING CLAUSE;
Having clause is added to sql as where could not be used with aggregated data rows;
Having clause to filter the group rows produced by the group by clause;
where clause filter the intermediate data rows while having clause operates on group rows;
the having clause uses conditions and operators to build complex sql statements
Since the having clause acts acts as a filter on group rows the only possible column in group rows are columns specified in the group by clause;

mysql> use school;
Database changed
mysql> select class,count(*) from students group by class;
+--------+----------+
| class  | count(*) |
+--------+----------+
| First  |       20 |
| Third  |       20 |
| Second |       18 |
+--------+----------+
3 rows in set (0.00 sec)

mysql> select class,count(*) from students group by class having count(*)<20;
+--------+----------+
| class  | count(*) |
+--------+----------+
| Second |       18 |
+--------+----------+
1 row in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> select jobtitle,salary,count(*) from employees group by salary;
+------------------------+--------+----------+
| jobtitle               | salary | count(*) |
+------------------------+--------+----------+
| Web Developer          |   3500 |        5 |
| Systems Administrator  |   3400 |        5 |
| IT Support Manager     |   3200 |        5 |
| Database Administrator |   3700 |        5 |
| Application Developer  |   3800 |        5 |
+------------------------+--------+----------+
5 rows in set (0.00 sec)

mysql> select jobtitle,salary,count(*) from employees group by salary having salary>3500;
+------------------------+--------+----------+
| jobtitle               | salary | count(*) |
+------------------------+--------+----------+
| Database Administrator |   3700 |        5 |
| Application Developer  |   3800 |        5 |
+------------------------+--------+----------+
2 rows in set (0.00 sec)

//order by clause and its functions
order by claus is used to sort or order the data rows in a result set.
The order by clause sorts the records in ascending order;
asc keyword for ascending while desc keyword for descending

mysql> select * from students;
ERROR 1146 (42S02): Table 'company.students' doesn't exist
mysql> use school;
Database changed

mysql> select * from students order by firstname;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|        26 | Adam      | Hall     | First  |    6 |
|        57 | Alice     | Jones    | Second |    6 |
|        40 | Anna      | Jones    | Second |    5 |
|        55 | Ashley    | Davis    | First  |    5 |
|        32 | Ava       | Jones    | First  |    7 |
|        49 | Bella     | White    | Second |    7 |
|        27 | Bobby     | White    | Second |    7 |
|        13 | Brian     | King     | Second |    5 |
|        42 | Camila    | Hall     | First  |    5 |
|        22 | Carl      | White    | Second |    5 |
|         9 | Daniel    | Jones    | First  |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        34 | Emily     | Walker   | Second |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        18 | Eric      | Jones    | Second |    7 |
|        53 | Eva       | Brown    | Second |    7 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        17 | Frank     | Smith    | First  |    7 |
|        35 | Grace     | King     | First  |    5 |
|        45 | Hailey    | Clark    | Second |    7 |
|        21 | Henry     | Clark    | Second |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|         3 | James     | Brown    | First  |    5 |
|         7 | James     | Smith    | First  |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        15 | Jason     | Lee      | Third  |    5 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|         1 | John      | Doe      | First  |    5 |
|         6 | John      | Doe      | Third  |    7 |
|         8 | John      | Brown    | Second |    6 |
|        28 | Johnny    | Davis    | First  |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        54 | Julia     | King     | Third  |    6 |
|        14 | Kevin     | Hall     | First  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        11 | Mark      | Davis    | Second |    6 |
|         2 | Mary      | Smith    | Third  |    7 |
|        51 | Maya      | Brown    | First  |    5 |
|        33 | Mia       | Smith    | Second |    6 |
|         4 | Mike      | Walker   | Second |    6 |
|        50 | Mila      | Smith    | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        12 | Steven    | Thomas   | First  |    7 |
|        39 | Zoe       | Thomas   | Second |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students order by firstname,lastname;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|        26 | Adam      | Hall     | First  |    6 |
|        57 | Alice     | Jones    | Second |    6 |
|        40 | Anna      | Jones    | Second |    5 |
|        55 | Ashley    | Davis    | First  |    5 |
|        32 | Ava       | Jones    | First  |    7 |
|        49 | Bella     | White    | Second |    7 |
|        27 | Bobby     | White    | Second |    7 |
|        13 | Brian     | King     | Second |    5 |
|        42 | Camila    | Hall     | First  |    5 |
|        22 | Carl      | White    | Second |    5 |
|         9 | Daniel    | Jones    | First  |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        34 | Emily     | Walker   | Second |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        18 | Eric      | Jones    | Second |    7 |
|        53 | Eva       | Brown    | Second |    7 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        17 | Frank     | Smith    | First  |    7 |
|        35 | Grace     | King     | First  |    5 |
|        45 | Hailey    | Clark    | Second |    7 |
|        21 | Henry     | Clark    | Second |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|         3 | James     | Brown    | First  |    5 |
|         7 | James     | Smith    | First  |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        15 | Jason     | Lee      | Third  |    5 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|         8 | John      | Brown    | Second |    6 |
|         1 | John      | Doe      | First  |    5 |
|         6 | John      | Doe      | Third  |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        54 | Julia     | King     | Third  |    6 |
|        14 | Kevin     | Hall     | First  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        11 | Mark      | Davis    | Second |    6 |
|         2 | Mary      | Smith    | Third  |    7 |
|        51 | Maya      | Brown    | First  |    5 |
|        33 | Mia       | Smith    | Second |    6 |
|         4 | Mike      | Walker   | Second |    6 |
|        50 | Mila      | Smith    | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        12 | Steven    | Thomas   | First  |    7 |
|        39 | Zoe       | Thomas   | Second |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students order by age desc;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|        32 | Ava       | Jones    | First  |    7 |
|         2 | Mary      | Smith    | Third  |    7 |
|        56 | Ruby      | Young    | Third  |    7 |
|        21 | Henry     | Clark    | Second |    7 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|         9 | Daniel    | Jones    | First  |    7 |
|        53 | Eva       | Brown    | Second |    7 |
|        23 | Joe       | Thomas   | First  |    7 |
|        12 | Steven    | Thomas   | First  |    7 |
|        49 | Bella     | White    | Second |    7 |
|        27 | Bobby     | White    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        44 | Nora      | Smith    | Second |    7 |
|         8 | John      | Brown    | Second |    6 |
|         4 | Mike      | Walker   | Second |    6 |
|         7 | James     | Smith    | First  |    6 |
|        11 | Mark      | Davis    | Second |    6 |
|        14 | Kevin     | Hall     | First  |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        20 | Peter     | King     | First  |    6 |
|        24 | Jack      | Smith    | Third  |    6 |
|        26 | Adam      | Hall     | First  |    6 |
|        28 | Johnny    | Davis    | First  |    6 |
|        37 | Lily      | King     | Third  |    6 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        33 | Mia       | Smith    | Second |    6 |
|        41 | Leah      | Brown    | Third  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        50 | Mila      | Smith    | Third  |    6 |
|        54 | Julia     | King     | Third  |    6 |
|        57 | Alice     | Jones    | Second |    6 |
|        22 | Carl      | White    | Second |    5 |
|        40 | Anna      | Jones    | Second |    5 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        42 | Camila    | Hall     | First  |    5 |
|        34 | Emily     | Walker   | Second |    5 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        15 | Jason     | Lee      | Third  |    5 |
|        46 | Ellie     | King     | Third  |    5 |
|        35 | Grace     | King     | First  |    5 |
|        48 | Stella    | White    | First  |    5 |
|        13 | Brian     | King     | Second |    5 |
|        25 | Roy       | King     | Second |    5 |
|         1 | John      | Doe      | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        10 | Paul      | Anderson | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        55 | Ashley    | Davis    | First  |    5 |
|         3 | James     | Brown    | First  |    5 |
|        38 | Layla     | Young    | First  |    5 |
|        51 | Maya      | Brown    | First  |    5 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees order by salary asc;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

//sql limit or top clause
 
the limit or top clause is useful to specify number of data rows to return

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students limit 5;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
+-----------+-----------+----------+--------+------+
5 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees limit 10;
+------------+---------------+-----------------------+--------+
| employeeid | name          | jobtitle              | salary |
+------------+---------------+-----------------------+--------+
|          1 | John Doe      | Web Developer         |   3500 |
|          2 | Mary Smith    | Web Developer         |   3500 |
|          3 | James Brown   | Web Developer         |   3500 |
|          4 | Mike Walker   | Web Developer         |   3500 |
|          5 | Linda Jones   | Web Developer         |   3500 |
|          6 | John Doe      | Systems Administrator |   3400 |
|          7 | James Smith   | Systems Administrator |   3400 |
|          8 | John Brown    | Systems Administrator |   3400 |
|          9 | Daniel Jones  | Systems Administrator |   3400 |
|         10 | Paul Anderson | Systems Administrator |   3400 |
+------------+---------------+-----------------------+--------+
10 rows in set (0.00 sec)
///Wild cards characters is used asa substitute for any other characters in a string;
the wildcars are used to search for a data in a given column;
the wildcards are used with like operator;
the percent(%) means zero or more characters and the (_) underscore means exactly one character;
mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students where firstname like 'Jo%';
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         6 | John      | Doe      | Third  |    7 |
|         8 | John      | Brown    | Second |    6 |
|        16 | Jose      | Young    | First  |    6 |
|        23 | Joe       | Thomas   | First  |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
+-----------+-----------+----------+--------+------+
6 rows in set (0.00 sec)

mysql> select * from students where firstname like 'Jo_';
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|        23 | Joe       | Thomas   | First |    7 |
+-----------+-----------+----------+-------+------+
1 row in set (0.00 sec)

mysql> select * from students where firstname like 'Jo_';
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|        23 | Joe       | Thomas   | First |    7 |
+-----------+-----------+----------+-------+------+
1 row in set (0.00 sec)

mysql> select * from students where firstname like '%y';
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         2 | Mary      | Smith    | Third  |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        21 | Henry     | Clark    | Second |    7 |
|        25 | Roy       | King     | Second |    5 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        34 | Emily     | Walker   | Second |    5 |
|        37 | Lily      | King     | Third  |    6 |
|        43 | Riley     | Martin   | Third  |    6 |
|        45 | Hailey    | Clark    | Second |    7 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
+-----------+-----------+----------+--------+------+
14 rows in set (0.00 sec)

mysql> select * from students where firstname like '%o%'
    -> ;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         6 | John      | Doe      | Third  |    7 |
|         8 | John      | Brown    | Second |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        23 | Joe       | Thomas   | First  |    7 |
|        25 | Roy       | King     | Second |    5 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        44 | Nora      | Smith    | Second |    7 |
+-----------+-----------+----------+--------+------+
12 rows in set (0.00 sec)

//sql aliases 
alias means a temporary name given to a table or a column
aliases makes table or column names more readable 
aliases are useful using multiple columns or tables in a single query or table names or coulumn names are big or not readable
the AS KEYWORD IS USED TO DEFINE THE ALIAS IN SQL STATEMENTS

mysql> use school;
Database changed
mysql> select s.firstname,s.lastname from students AS s;
+-----------+----------+
| firstname | lastname |
+-----------+----------+
| John      | Doe      |
| Mary      | Smith    |
| James     | Brown    |
| Mike      | Walker   |
| Linda     | Jones    |
| John      | Doe      |
| James     | Smith    |
| John      | Brown    |
| Daniel    | Jones    |
| Paul      | Anderson |
| Mark      | Davis    |
| Steven    | Thomas   |
| Brian     | King     |
| Kevin     | Hall     |
| Jason     | Lee      |
| Jose      | Young    |
| Frank     | Smith    |
| Eric      | Jones    |
| Jerry     | Martin   |
| Peter     | King     |
| Henry     | Clark    |
| Carl      | White    |
| Joe       | Thomas   |
| Jack      | Smith    |
| Roy       | King     |
| Adam      | Hall     |
| Bobby     | White    |
| Johnny    | Davis    |
| Jimmy     | Jones    |
| Emma      | Walker   |
| Sophia    | Walker   |
| Ava       | Jones    |
| Mia       | Smith    |
| Emily     | Walker   |
| Grace     | King     |
| Lillian   | Jones    |
| Lily      | King     |
| Layla     | Young    |
| Zoe       | Thomas   |
| Anna      | Jones    |
| Leah      | Brown    |
| Camila    | Hall     |
| Riley     | Martin   |
| Nora      | Smith    |
| Hailey    | Clark    |
| Ellie     | King     |
| Lucy      | Jones    |
| Stella    | White    |
| Bella     | White    |
| Mila      | Smith    |
| Maya      | Brown    |
| Faith     | Thomas   |
| Eva       | Brown    |
| Julia     | King     |
| Ashley    | Davis    |
| Ruby      | Young    |
| Alice     | Jones    |
| Jasmine   | Hall     |
+-----------+----------+
58 rows in set (0.00 sec)

mysql> select count(*) from students;
+----------+
| count(*) |
+----------+
|       58 |
+----------+
1 row in set (0.01 sec)

mysql> select count(*) as 'Total Students' from students;
+----------------+
| Total Students |
+----------------+
|             58 |
+----------------+
1 row in set (0.00 sec)

mysql> select concat(firstname,'',lastname) from students;
+-------------------------------+
| concat(firstname,'',lastname) |
+-------------------------------+
| JohnDoe                       |
| MarySmith                     |
| JamesBrown                    |
| MikeWalker                    |
| LindaJones                    |
| JohnDoe                       |
| JamesSmith                    |
| JohnBrown                     |
| DanielJones                   |
| PaulAnderson                  |
| MarkDavis                     |
| StevenThomas                  |
| BrianKing                     |
| KevinHall                     |
| JasonLee                      |
| JoseYoung                     |
| FrankSmith                    |
| EricJones                     |
| JerryMartin                   |
| PeterKing                     |
| HenryClark                    |
| CarlWhite                     |
| JoeThomas                     |
| JackSmith                     |
| RoyKing                       |
| AdamHall                      |
| BobbyWhite                    |
| JohnnyDavis                   |
| JimmyJones                    |
| EmmaWalker                    |
| SophiaWalker                  |
| AvaJones                      |
| MiaSmith                      |
| EmilyWalker                   |
| GraceKing                     |
| LillianJones                  |
| LilyKing                      |
| LaylaYoung                    |
| ZoeThomas                     |
| AnnaJones                     |
| LeahBrown                     |
| CamilaHall                    |
| RileyMartin                   |
| NoraSmith                     |
| HaileyClark                   |
| EllieKing                     |
| LucyJones                     |
| StellaWhite                   |
| BellaWhite                    |
| MilaSmith                     |
| MayaBrown                     |
| FaithThomas                   |
| EvaBrown                      |
| JuliaKing                     |
| AshleyDavis                   |
| RubyYoung                     |
| AliceJones                    |
| JasmineHall                   |
+-------------------------------+
58 rows in set (0.00 sec)

mysql> select concat(firstname,'',lastname) as Fullname from students;
+--------------+
| Fullname     |
+--------------+
| JohnDoe      |
| MarySmith    |
| JamesBrown   |
| MikeWalker   |
| LindaJones   |
| JohnDoe      |
| JamesSmith   |
| JohnBrown    |
| DanielJones  |
| PaulAnderson |
| MarkDavis    |
| StevenThomas |
| BrianKing    |
| KevinHall    |
| JasonLee     |
| JoseYoung    |
| FrankSmith   |
| EricJones    |
| JerryMartin  |
| PeterKing    |
| HenryClark   |
| CarlWhite    |
| JoeThomas    |
| JackSmith    |
| RoyKing      |
| AdamHall     |
| BobbyWhite   |
| JohnnyDavis  |
| JimmyJones   |
| EmmaWalker   |
| SophiaWalker |
| AvaJones     |
| MiaSmith     |
| EmilyWalker  |
| GraceKing    |
| LillianJones |
| LilyKing     |
| LaylaYoung   |
| ZoeThomas    |
| AnnaJones    |
| LeahBrown    |
| CamilaHall   |
| RileyMartin  |
| NoraSmith    |
| HaileyClark  |
| EllieKing    |
| LucyJones    |
| StellaWhite  |
| BellaWhite   |
| MilaSmith    |
| MayaBrown    |
| FaithThomas  |
| EvaBrown     |
| JuliaKing    |
| AshleyDavis  |
| RubyYoung    |
| AliceJones   |
| JasmineHall  |
+--------------+
58 rows in set (0.00 sec)

//sql dates 
// sql have built in date functions for working with dates;
sql have now(),curdate(),curtime() 


mysql> select now();
+---------------------+
| now()               |
+---------------------+
| 2020-05-20 16:39:39 |
+---------------------+
1 row in set (0.00 sec)

mysql> select curdate();
+------------+
| curdate()  |
+------------+
| 2020-05-20 |
+------------+
1 row in set (0.00 sec)

mysql> select curtime();
+-----------+
| curtime() |
+-----------+
| 16:39:59  |
+-----------+
1 row in set (0.00 sec)

mysql> use onlineshop;
Database changed
mysql> select * from orders;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

mysql> select * from orders where orderdate ='2020-05-20 11:35:39';
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

///the insert into statement is used to insert or add new values new data items in a table;
two methods 
 INSERT INTO tablename VALUES(value1,value2,value3)
 INSERT INTO tablename (column1,column2,column3) VALUES(value1,value2,value3)
 
 mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from teachers;
+-----------+----------------+------------+
| teacherid | name           | phone      |
+-----------+----------------+------------+
|         1 | John Doe       | 1234567890 |
|         2 | Caroline Smith | 0987654321 |
|         3 | Jason King     | 1234512345 |
|         4 | Stella Brown   | 0987612345 |
|         5 | Eric Hall      | 0987609876 |
+-----------+----------------+------------+
5 rows in set (0.00 sec)

mysql> insert into teachers values(null,'Peter Brown',123435454);
Query OK, 1 row affected (0.01 sec)

mysql> select * from teachers;
+-----------+----------------+------------+
| teacherid | name           | phone      |
+-----------+----------------+------------+
|         1 | John Doe       | 1234567890 |
|         2 | Caroline Smith | 0987654321 |
|         3 | Jason King     | 1234512345 |
|         4 | Stella Brown   | 0987612345 |
|         5 | Eric Hall      | 0987609876 |
|         6 | Peter Brown    | 123435454  |
+-----------+----------------+------------+
6 rows in set (0.00 sec)
///INSERT INTO STUDENT2 SELECT * FROM STUDENTS;
///insert into select;


mysql> use school;
Database changed
mysql> create table students2(
    -> studentid INT PRIMARY KEY AUTO_INCREMENT,
    -> firstname VARCHAR(40) NOT NULL,
    -> lastname VARCHAR(40) NOT NULL,
    -> class VARCHAR(20),
    -> age INT,
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ')' at line 7
mysql> create table students2 (
    -> studentid INT PRIMARY KEY AUTO_INCREMENT,
    -> firstname VARCHAR(40) NOT NULL,
    -> lastname VARCHAR(40) NOT NULL,
    -> class VARCHAR(20),
    -> age INT);
Query OK, 0 rows affected (0.15 sec)

mysql> DESC STUDENTS2;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| studentid | int         | NO   | PRI | NULL    | auto_increment |
| firstname | varchar(40) | NO   |     | NULL    |                |
| lastname  | varchar(40) | NO   |     | NULL    |                |
| class     | varchar(20) | YES  |     | NULL    |                |
| age       | int         | YES  |     | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
5 rows in set (0.01 sec)

mysql> INSERT INTO STUDENTS2 SELECT * FROM STUDENTS;
Query OK, 58 rows affected (0.01 sec)
Records: 58  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM STUDENTS2;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> DELETE FROM STUDENTS2;
Query OK, 58 rows affected (0.01 sec)

mysql> INSERT INTO STUDENTS2 (FIRSTNAME,LASTNAME) SELECT FIRSTNAME,LASTNAME FROM STUDENTS;
Query OK, 58 rows affected (0.01 sec)
Records: 58  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM STUDENTS2;
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|        59 | John      | Doe      | NULL  | NULL |
|        60 | Mary      | Smith    | NULL  | NULL |
|        61 | James     | Brown    | NULL  | NULL |
|        62 | Mike      | Walker   | NULL  | NULL |
|        63 | Linda     | Jones    | NULL  | NULL |
|        64 | John      | Doe      | NULL  | NULL |
|        65 | James     | Smith    | NULL  | NULL |
|        66 | John      | Brown    | NULL  | NULL |
|        67 | Daniel    | Jones    | NULL  | NULL |
|        68 | Paul      | Anderson | NULL  | NULL |
|        69 | Mark      | Davis    | NULL  | NULL |
|        70 | Steven    | Thomas   | NULL  | NULL |
|        71 | Brian     | King     | NULL  | NULL |
|        72 | Kevin     | Hall     | NULL  | NULL |
|        73 | Jason     | Lee      | NULL  | NULL |
|        74 | Jose      | Young    | NULL  | NULL |
|        75 | Frank     | Smith    | NULL  | NULL |
|        76 | Eric      | Jones    | NULL  | NULL |
|        77 | Jerry     | Martin   | NULL  | NULL |
|        78 | Peter     | King     | NULL  | NULL |
|        79 | Henry     | Clark    | NULL  | NULL |
|        80 | Carl      | White    | NULL  | NULL |
|        81 | Joe       | Thomas   | NULL  | NULL |
|        82 | Jack      | Smith    | NULL  | NULL |
|        83 | Roy       | King     | NULL  | NULL |
|        84 | Adam      | Hall     | NULL  | NULL |
|        85 | Bobby     | White    | NULL  | NULL |
|        86 | Johnny    | Davis    | NULL  | NULL |
|        87 | Jimmy     | Jones    | NULL  | NULL |
|        88 | Emma      | Walker   | NULL  | NULL |
|        89 | Sophia    | Walker   | NULL  | NULL |
|        90 | Ava       | Jones    | NULL  | NULL |
|        91 | Mia       | Smith    | NULL  | NULL |
|        92 | Emily     | Walker   | NULL  | NULL |
|        93 | Grace     | King     | NULL  | NULL |
|        94 | Lillian   | Jones    | NULL  | NULL |
|        95 | Lily      | King     | NULL  | NULL |
|        96 | Layla     | Young    | NULL  | NULL |
|        97 | Zoe       | Thomas   | NULL  | NULL |
|        98 | Anna      | Jones    | NULL  | NULL |
|        99 | Leah      | Brown    | NULL  | NULL |
|       100 | Camila    | Hall     | NULL  | NULL |
|       101 | Riley     | Martin   | NULL  | NULL |
|       102 | Nora      | Smith    | NULL  | NULL |
|       103 | Hailey    | Clark    | NULL  | NULL |
|       104 | Ellie     | King     | NULL  | NULL |
|       105 | Lucy      | Jones    | NULL  | NULL |
|       106 | Stella    | White    | NULL  | NULL |
|       107 | Bella     | White    | NULL  | NULL |
|       108 | Mila      | Smith    | NULL  | NULL |
|       109 | Maya      | Brown    | NULL  | NULL |
|       110 | Faith     | Thomas   | NULL  | NULL |
|       111 | Eva       | Brown    | NULL  | NULL |
|       112 | Julia     | King     | NULL  | NULL |
|       113 | Ashley    | Davis    | NULL  | NULL |
|       114 | Ruby      | Young    | NULL  | NULL |
|       115 | Alice     | Jones    | NULL  | NULL |
|       116 | Jasmine   | Hall     | NULL  | NULL |
+-----------+-----------+----------+-------+------+
58 rows in set (0.00 sec)

//UPDATE statement 

Update statement is used to update the data rows in a table;
where clause is used to specify the data row to be updated;


mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | First  |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> update students set class='Second' WHERE studentid=1 and FIRSTNAME='John' and LASTNAME='Doe';
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> select * from students2;
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|        59 | John      | Doe      | NULL  | NULL |
|        60 | Mary      | Smith    | NULL  | NULL |
|        61 | James     | Brown    | NULL  | NULL |
|        62 | Mike      | Walker   | NULL  | NULL |
|        63 | Linda     | Jones    | NULL  | NULL |
|        64 | John      | Doe      | NULL  | NULL |
|        65 | James     | Smith    | NULL  | NULL |
|        66 | John      | Brown    | NULL  | NULL |
|        67 | Daniel    | Jones    | NULL  | NULL |
|        68 | Paul      | Anderson | NULL  | NULL |
|        69 | Mark      | Davis    | NULL  | NULL |
|        70 | Steven    | Thomas   | NULL  | NULL |
|        71 | Brian     | King     | NULL  | NULL |
|        72 | Kevin     | Hall     | NULL  | NULL |
|        73 | Jason     | Lee      | NULL  | NULL |
|        74 | Jose      | Young    | NULL  | NULL |
|        75 | Frank     | Smith    | NULL  | NULL |
|        76 | Eric      | Jones    | NULL  | NULL |
|        77 | Jerry     | Martin   | NULL  | NULL |
|        78 | Peter     | King     | NULL  | NULL |
|        79 | Henry     | Clark    | NULL  | NULL |
|        80 | Carl      | White    | NULL  | NULL |
|        81 | Joe       | Thomas   | NULL  | NULL |
|        82 | Jack      | Smith    | NULL  | NULL |
|        83 | Roy       | King     | NULL  | NULL |
|        84 | Adam      | Hall     | NULL  | NULL |
|        85 | Bobby     | White    | NULL  | NULL |
|        86 | Johnny    | Davis    | NULL  | NULL |
|        87 | Jimmy     | Jones    | NULL  | NULL |
|        88 | Emma      | Walker   | NULL  | NULL |
|        89 | Sophia    | Walker   | NULL  | NULL |
|        90 | Ava       | Jones    | NULL  | NULL |
|        91 | Mia       | Smith    | NULL  | NULL |
|        92 | Emily     | Walker   | NULL  | NULL |
|        93 | Grace     | King     | NULL  | NULL |
|        94 | Lillian   | Jones    | NULL  | NULL |
|        95 | Lily      | King     | NULL  | NULL |
|        96 | Layla     | Young    | NULL  | NULL |
|        97 | Zoe       | Thomas   | NULL  | NULL |
|        98 | Anna      | Jones    | NULL  | NULL |
|        99 | Leah      | Brown    | NULL  | NULL |
|       100 | Camila    | Hall     | NULL  | NULL |
|       101 | Riley     | Martin   | NULL  | NULL |
|       102 | Nora      | Smith    | NULL  | NULL |
|       103 | Hailey    | Clark    | NULL  | NULL |
|       104 | Ellie     | King     | NULL  | NULL |
|       105 | Lucy      | Jones    | NULL  | NULL |
|       106 | Stella    | White    | NULL  | NULL |
|       107 | Bella     | White    | NULL  | NULL |
|       108 | Mila      | Smith    | NULL  | NULL |
|       109 | Maya      | Brown    | NULL  | NULL |
|       110 | Faith     | Thomas   | NULL  | NULL |
|       111 | Eva       | Brown    | NULL  | NULL |
|       112 | Julia     | King     | NULL  | NULL |
|       113 | Ashley    | Davis    | NULL  | NULL |
|       114 | Ruby      | Young    | NULL  | NULL |
|       115 | Alice     | Jones    | NULL  | NULL |
|       116 | Jasmine   | Hall     | NULL  | NULL |
+-----------+-----------+----------+-------+------+
58 rows in set (0.00 sec)

mysql> use company;
Database changed
mysql> select * from employees;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Systems Administrator  |   3400 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> update employees set jobtitle='Application Developer',salary=3800 where employeeid=6;
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from employees;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Application Developer  |   3800 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

///Delete Statement

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> delete from students2 where studentid=60;
Query OK, 1 row affected (0.01 sec)

mysql> select * from students2;
+-----------+-----------+----------+-------+------+
| studentid | firstname | lastname | class | age  |
+-----------+-----------+----------+-------+------+
|        59 | John      | Doe      | NULL  | NULL |
|        61 | James     | Brown    | NULL  | NULL |
|        62 | Mike      | Walker   | NULL  | NULL |
|        63 | Linda     | Jones    | NULL  | NULL |
|        64 | John      | Doe      | NULL  | NULL |
|        65 | James     | Smith    | NULL  | NULL |
|        66 | John      | Brown    | NULL  | NULL |
|        67 | Daniel    | Jones    | NULL  | NULL |
|        68 | Paul      | Anderson | NULL  | NULL |
|        69 | Mark      | Davis    | NULL  | NULL |
|        70 | Steven    | Thomas   | NULL  | NULL |
|        71 | Brian     | King     | NULL  | NULL |
|        72 | Kevin     | Hall     | NULL  | NULL |
|        73 | Jason     | Lee      | NULL  | NULL |
|        74 | Jose      | Young    | NULL  | NULL |
|        75 | Frank     | Smith    | NULL  | NULL |
|        76 | Eric      | Jones    | NULL  | NULL |
|        77 | Jerry     | Martin   | NULL  | NULL |
|        78 | Peter     | King     | NULL  | NULL |
|        79 | Henry     | Clark    | NULL  | NULL |
|        80 | Carl      | White    | NULL  | NULL |
|        81 | Joe       | Thomas   | NULL  | NULL |
|        82 | Jack      | Smith    | NULL  | NULL |
|        83 | Roy       | King     | NULL  | NULL |
|        84 | Adam      | Hall     | NULL  | NULL |
|        85 | Bobby     | White    | NULL  | NULL |
|        86 | Johnny    | Davis    | NULL  | NULL |
|        87 | Jimmy     | Jones    | NULL  | NULL |
|        88 | Emma      | Walker   | NULL  | NULL |
|        89 | Sophia    | Walker   | NULL  | NULL |
|        90 | Ava       | Jones    | NULL  | NULL |
|        91 | Mia       | Smith    | NULL  | NULL |
|        92 | Emily     | Walker   | NULL  | NULL |
|        93 | Grace     | King     | NULL  | NULL |
|        94 | Lillian   | Jones    | NULL  | NULL |
|        95 | Lily      | King     | NULL  | NULL |
|        96 | Layla     | Young    | NULL  | NULL |
|        97 | Zoe       | Thomas   | NULL  | NULL |
|        98 | Anna      | Jones    | NULL  | NULL |
|        99 | Leah      | Brown    | NULL  | NULL |
|       100 | Camila    | Hall     | NULL  | NULL |
|       101 | Riley     | Martin   | NULL  | NULL |
|       102 | Nora      | Smith    | NULL  | NULL |
|       103 | Hailey    | Clark    | NULL  | NULL |
|       104 | Ellie     | King     | NULL  | NULL |
|       105 | Lucy      | Jones    | NULL  | NULL |
|       106 | Stella    | White    | NULL  | NULL |
|       107 | Bella     | White    | NULL  | NULL |
|       108 | Mila      | Smith    | NULL  | NULL |
|       109 | Maya      | Brown    | NULL  | NULL |
|       110 | Faith     | Thomas   | NULL  | NULL |
|       111 | Eva       | Brown    | NULL  | NULL |
|       112 | Julia     | King     | NULL  | NULL |
|       113 | Ashley    | Davis    | NULL  | NULL |
|       114 | Ruby      | Young    | NULL  | NULL |
|       115 | Alice     | Jones    | NULL  | NULL |
|       116 | Jasmine   | Hall     | NULL  | NULL |
+-----------+-----------+----------+-------+------+
57 rows in set (0.00 sec)

mysql> delete from students2;
Query OK, 57 rows affected (0.01 sec)

mysql> select * from students2;
Empty set (0.00 sec)


//SQL INJECTIONS IS A METHOD WHERE A MALICIOUS USER CAN INJECT SOME SQL COMMANDS TO DISPLAY OTHER 
INFORMATION OR DESTROY THE DATABASE USING FORM FIELDS ON WEB PAGE OR Application

///SQL INJECTIONS Statement ARE USED TO MANAGE THE DATABASE FROM A WEB PAGE APPLICATION . 
USERS INTERACT WITH THE DATABASE USING FORM FIELDS .SQL Statement ARE TEXT KEYWORDS AND CAN BE CHANGED DYNAMICALLY;

BY USING SQL INJECTIONS A HACKER MAY GET ACCESS TO OTHER USERS PASSWORD AND OTHER INFORMATION;

MAINLY 3 TYPES SQL INJECTIONS;
1) SQL INJECTION USING 1=1
2)SQL INJECTION USNIG "="
3)SQL INJECTIONS USING BATCHED SQL INJECTIONS 

///SINGLE QUOTE FOR STRING AND NO QUOTES FOR NUMERICAL VALUES;

Always protecting database from sql injections is extremely easy
Always filter the input via form fields;

>Use mysqli_real_escape_string function to escape the sql statements;
>$id=mysqli_real_escape_string($_POST[id]);

/////JOINS IN SQL 
A join combines two or more tables to produce a singular tabular structure.
In SQL THE JOINS ARE CREATED USING THE JOIN CLAUSE;

THERE ARE 3 MAIN TYPES OF JOINS 
1.INNER JOIN 
2.OUTER JOIN
3.CROSS JOIN

INNER JOIN : CREATED WITH INNER JOIN KEYWORD . IT RETURN ALL DATA ROWS WHEN THERE IS AT LEAST ONE MATCH IN BOTH THE TABLES;

OUTER JOIN : CREATED WITH OUTER JOIN KEYWORD.IT CAN RETURN MATCHED AS WELL AS UNMATHCED DATA Rows
THE OUTER JOIN HAVE 3 TYPES. LEFT OUTER JOINS ,RIGHT OUTER JOIN,FULL OUTER JOINS

CROSS JOIN: CREATED WITH CROSS JOIN KEYWORD.IT RETURNS ALL ROWS WHEN THERE IS A MATCH IN ONE OF THE TABLES;

mysql> CREATE DATABASE JOINS;
Query OK, 1 row affected (0.02 sec)

mysql> USE JOINS;
Database changed
mysql> CREATE TABLE TABLE1(COLUMN1 INT);
Query OK, 0 rows affected (0.06 sec)

mysql> CREATE TABLE TABLE2(COLUMN2 INT);
Query OK, 0 rows affected (0.13 sec)

mysql> SHOW TABLES;
+-----------------+
| Tables_in_joins |
+-----------------+
| table1          |
| table2          |
+-----------------+
2 rows in set (0.01 sec)

mysql> INSERT INTO TABLE1 VALUES (11),(12),(13),(14),(15);
Query OK, 5 rows affected (0.06 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> INSERT INTO TABLE1 VALUES (12),(15),(50);
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      12 |
|      13 |
|      14 |
|      15 |
|      12 |
|      15 |
|      50 |
+---------+
8 rows in set (0.00 sec)

mysql> select * from TABLE2;
Empty set (0.00 sec)

mysql> DELETE COLUMN1 FROM TABLE1 WHERE COLUMN1=12 AND COLUMN1=15 AND COLUMN1=50;
ERROR 1109 (42S02): Unknown table 'column1' in MULTI DELETE
mysql> DELETE COLUMN1 FROM TABLE1 WHERE COLUMN1=12;
ERROR 1109 (42S02): Unknown table 'column1' in MULTI DELETE
mysql> DELETE FROM TABLE1 WHERE COLUMN1=12;
Query OK, 2 rows affected (0.01 sec)

mysql> DELETE  FROM TABLE1 WHERE COLUMN1=12 AND COLUMN1=15 AND COLUMN1=50;
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      15 |
|      15 |
|      50 |
+---------+
6 rows in set (0.00 sec)

mysql> DELETE  FROM TABLE1 WHERE COLUMN1=50;
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      15 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> DELETE  FROM TABLE1 WHERE COLUMN1=15 ;
Query OK, 2 rows affected (0.01 sec)

mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
+---------+
3 rows in set (0.00 sec)

mysql> INSERT INTO TABLE1 VALUES (12),(15);
Query OK, 2 rows affected (0.01 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> INSERT INTO TABLE2 VALUES (12),(15),(50);
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE2;
+---------+
| COLUMN2 |
+---------+
|      12 |
|      15 |
|      50 |
+---------+
3 rows in set (0.00 sec)

//INNER JOINS IS USED BY USING INNER JOIN KEYWORD 
//AN INNER JOIN IS THE MOST COMMON TYPE OF JOIN;
//IN INNER JOIN THE ON CLAUSE DEFINES THE COLUMNS AND CONDITONS TO BE EVALUATED;


mysql>  USE JOINS;
Database changed
mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE2;
+---------+
| COLUMN2 |
+---------+
|      12 |
|      15 |
|      50 |
+---------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1 INNER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2;
+---------+---------+
| COLUMN1 | COLUMN2 |
+---------+---------+
|      12 |      12 |
|      15 |      15 |
+---------+---------+
2 rows in set (0.00 sec)

mysql> USE COMPANY;
Database changed

mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Application Developer  |   3800 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT * PROJECTS;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'PROJECTS' at line 1
mysql> SELECT * FROM PROJECTS;
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
| projectid | title                                                | clientid | employeeid | startdate           | enddate             |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
|         1 | Develop ecommerse website from scratch               |        1 |          3 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
|         2 | WordPress website for our company                    |        1 |          2 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         3 | Manage our company servers                           |        2 |          7 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         4 | Hosting account is not working                       |        3 |          9 | 2020-05-20 11:33:43 | 2020-05-27 11:33:43 |
|         5 | MySQL database from my desktop application           |        4 |         17 | 2020-05-20 11:33:43 | 2020-06-04 11:33:43 |
|         6 | Develop new WordPress plugin for my business website |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-30 11:33:43 |
|         7 | Migrate web application and database to new server   |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-25 11:33:43 |
|         8 | Android Application development                      |        4 |         23 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
8 rows in set (0.00 sec)

mysql> SELECT NAME,JOBTITLE,TITLE FROM EMPLOYEES INNER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID;
+--------------+------------------------+--------------------------------------------+
| NAME         | JOBTITLE               | TITLE                                      |
+--------------+------------------------+--------------------------------------------+
| James Brown  | Web Developer          | Develop ecommerse website from scratch     |
| Mary Smith   | Web Developer          | WordPress website for our company          |
| James Smith  | Systems Administrator  | Manage our company servers                 |
| Daniel Jones | Systems Administrator  | Hosting account is not working             |
| Frank Smith  | Database Administrator | MySQL database from my desktop application |
| Joe Thomas   | Application Developer  | Android Application development            |
+--------------+------------------------+--------------------------------------------+
6 rows in set (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM CUSTOMERS;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM ORDERS;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)


mysql> SELECT userid,NAME,PHONE,ITEMS,TOTAL FROM CUSTOMERS INNER JOIN ORDERS ON CUSTOMERS.userid=ORDERS.userid;
ERROR 1052 (23000): Column 'userid' in field list is ambiguous
mysql> SELECT * FROM CUSTOMERS INNER JOIN ORDERS ON CUSTOMERS.userid=ORDERS.userid;
+--------+-------------+------------+-------------------------------------+---------+--------+------------------------------+-------+---------------------+
| userid | name        | phone      | address                             | orderid | userid | items                        | total | orderdate           |
+--------+-------------+------------+-------------------------------------+---------+--------+------------------------------+-------+---------------------+
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+--------+-------------+------------+-------------------------------------+---------+--------+------------------------------+-------+---------------------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM CUSTOMERS INNER JOIN ORDERS ON CUSTOMERS.USERID=ORDERS.USERID;
+--------+-------------+------------+-------------------------------------+---------+--------+------------------------------+-------+---------------------+
| userid | name        | phone      | address                             | orderid | userid | items                        | total | orderdate           |
+--------+-------------+------------+-------------------------------------+---------+--------+------------------------------+-------+---------------------+
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+--------+-------------+------------+-------------------------------------+---------+--------+------------------------------+-------+---------------------+
5 rows in set (0.00 sec)

mysql> SELECT USERID,NAME,PHONE,ITEMS,TOTAL FROM CUSTOMERS INNER JOIN ORDERS ON CUSTOMERS.USERID=ORDERS.USERID;
ERROR 1052 (23000): Column 'USERID' in field list is ambiguous
mysql> SELECT userid,NAME,PHONE,ITEMS,TOTAL FROM CUSTOMERS INNER JOIN ORDERS ON CUSTOMERS.USERID=ORDERS.USERID;
ERROR 1052 (23000): Column 'userid' in field list is ambiguous
mysql> SELECT NAME,PHONE,ITEMS,TOTAL FROM CUSTOMERS INNER JOIN ORDERS ON CUSTOMERS.USERID=ORDERS.USERID;
+-------------+------------+------------------------------+-------+
| NAME        | PHONE      | ITEMS                        | TOTAL |
+-------------+------------+------------------------------+-------+
| Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
| Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
| Jimmy Jones | 1234567890 | How to train your cat        |    25 |
| Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
| Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
+-------------+------------+------------------------------+-------+
5 rows in set (0.00 sec)

mysql> SELECT CUSTOMERS.USERID,NAME,PHONE,ITEMS,TOTAL FROM CUSTOMERS INNER JOIN ORDERS ON CUSTOMERS.USERID=ORDERS.USERID;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
+--------+-------------+------------+------------------------------+-------+
5 rows in set (0.00 sec)
mysql> SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM CUSTOMERS AS C INNER JOIN ORDERS AS O ON C.USERID=O.USERID;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
+--------+-------------+------------+------------------------------+-------+
5 rows in set (0.00 sec)


//LEFT OUTER JOIN
//THE OUTER JOIN IS CREATED BY USING OUTER JOIN KEYWORD;
//THE OUTER JOIN RETURN MATCHED DATA AND ROWS AS WELL AS UNMATCHED DATA AND ROW FROM THE TABLES;
//IN LEFT OUTER JOIN ALL THE DATA ROWS FROM THE LEFT TABLE ARE RETURNED;

mysql> USE JOINS;
Database changed
mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE2;
+---------+
| COLUMN2 |
+---------+
|      12 |
|      15 |
|      50 |
+---------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1 LEFT OUTER JOIN ON TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'ON TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2' at line 1
mysql> SELECT * FROM TABLE1 LEFT OUTER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2;
+---------+---------+
| COLUMN1 | COLUMN2 |
+---------+---------+
|      11 |    NULL |
|      13 |    NULL |
|      14 |    NULL |
|      12 |      12 |
|      15 |      15 |
+---------+---------+
5 rows in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Application Developer  |   3800 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT * FROM PROJECTS;
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
| projectid | title                                                | clientid | employeeid | startdate           | enddate             |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
|         1 | Develop ecommerse website from scratch               |        1 |          3 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
|         2 | WordPress website for our company                    |        1 |          2 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         3 | Manage our company servers                           |        2 |          7 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         4 | Hosting account is not working                       |        3 |          9 | 2020-05-20 11:33:43 | 2020-05-27 11:33:43 |
|         5 | MySQL database from my desktop application           |        4 |         17 | 2020-05-20 11:33:43 | 2020-06-04 11:33:43 |
|         6 | Develop new WordPress plugin for my business website |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-30 11:33:43 |
|         7 | Migrate web application and database to new server   |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-25 11:33:43 |
|         8 | Android Application development                      |        4 |         23 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
8 rows in set (0.00 sec)

mysql> SELECT NAME,JOBTITLE,TITLE FROM EMPLOYEES LEFT OUTER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID;
+---------------+------------------------+--------------------------------------------+
| NAME          | JOBTITLE               | TITLE                                      |
+---------------+------------------------+--------------------------------------------+
| John Doe      | Web Developer          | NULL                                       |
| Mary Smith    | Web Developer          | WordPress website for our company          |
| James Brown   | Web Developer          | Develop ecommerse website from scratch     |
| Mike Walker   | Web Developer          | NULL                                       |
| Linda Jones   | Web Developer          | NULL                                       |
| John Doe      | Application Developer  | NULL                                       |
| James Smith   | Systems Administrator  | Manage our company servers                 |
| John Brown    | Systems Administrator  | NULL                                       |
| Daniel Jones  | Systems Administrator  | Hosting account is not working             |
| Paul Anderson | Systems Administrator  | NULL                                       |
| Mark Davis    | IT Support Manager     | NULL                                       |
| Steven Thomas | IT Support Manager     | NULL                                       |
| Brian King    | IT Support Manager     | NULL                                       |
| Kevin Hall    | IT Support Manager     | NULL                                       |
| Jason Lee     | IT Support Manager     | NULL                                       |
| Jose Young    | Database Administrator | NULL                                       |
| Frank Smith   | Database Administrator | MySQL database from my desktop application |
| Eric Jones    | Database Administrator | NULL                                       |
| Jerry Martin  | Database Administrator | NULL                                       |
| Peter King    | Database Administrator | NULL                                       |
| Henry Clark   | Application Developer  | NULL                                       |
| Carl White    | Application Developer  | NULL                                       |
| Joe Thomas    | Application Developer  | Android Application development            |
| Jack Smith    | Application Developer  | NULL                                       |
| Roy King      | Application Developer  | NULL                                       |
+---------------+------------------------+--------------------------------------------+
25 rows in set (0.00 sec)

mysql> SELECT NAME,JOBTITLE,TITLE FROM EMPLOYEES LEFT OUTER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID ORDERBY TITLE;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'ORDERBY TITLE' at line 1
mysql> SELECT NAME,JOBTITLE,TITLE FROM EMPLOYEES LEFT OUTER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID ORDER BY TITLE;
+---------------+------------------------+--------------------------------------------+
| NAME          | JOBTITLE               | TITLE                                      |
+---------------+------------------------+--------------------------------------------+
| John Doe      | Web Developer          | NULL                                       |
| Mike Walker   | Web Developer          | NULL                                       |
| Linda Jones   | Web Developer          | NULL                                       |
| John Doe      | Application Developer  | NULL                                       |
| John Brown    | Systems Administrator  | NULL                                       |
| Paul Anderson | Systems Administrator  | NULL                                       |
| Mark Davis    | IT Support Manager     | NULL                                       |
| Steven Thomas | IT Support Manager     | NULL                                       |
| Brian King    | IT Support Manager     | NULL                                       |
| Kevin Hall    | IT Support Manager     | NULL                                       |
| Jason Lee     | IT Support Manager     | NULL                                       |
| Jose Young    | Database Administrator | NULL                                       |
| Eric Jones    | Database Administrator | NULL                                       |
| Jerry Martin  | Database Administrator | NULL                                       |
| Peter King    | Database Administrator | NULL                                       |
| Henry Clark   | Application Developer  | NULL                                       |
| Carl White    | Application Developer  | NULL                                       |
| Jack Smith    | Application Developer  | NULL                                       |
| Roy King      | Application Developer  | NULL                                       |
| Joe Thomas    | Application Developer  | Android Application development            |
| James Brown   | Web Developer          | Develop ecommerse website from scratch     |
| Daniel Jones  | Systems Administrator  | Hosting account is not working             |
| James Smith   | Systems Administrator  | Manage our company servers                 |
| Frank Smith   | Database Administrator | MySQL database from my desktop application |
| Mary Smith    | Web Developer          | WordPress website for our company          |
+---------------+------------------------+--------------------------------------------+
25 rows in set (0.00 sec)

mysql> SELECT NAME,JOBTITLE,TITLE FROM EMPLOYEES LEFT OUTER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID ORDER BY TITLE DESC;
+---------------+------------------------+--------------------------------------------+
| NAME          | JOBTITLE               | TITLE                                      |
+---------------+------------------------+--------------------------------------------+
| Mary Smith    | Web Developer          | WordPress website for our company          |
| Frank Smith   | Database Administrator | MySQL database from my desktop application |
| James Smith   | Systems Administrator  | Manage our company servers                 |
| Daniel Jones  | Systems Administrator  | Hosting account is not working             |
| James Brown   | Web Developer          | Develop ecommerse website from scratch     |
| Joe Thomas    | Application Developer  | Android Application development            |
| John Doe      | Web Developer          | NULL                                       |
| Mike Walker   | Web Developer          | NULL                                       |
| Linda Jones   | Web Developer          | NULL                                       |
| John Doe      | Application Developer  | NULL                                       |
| John Brown    | Systems Administrator  | NULL                                       |
| Paul Anderson | Systems Administrator  | NULL                                       |
| Mark Davis    | IT Support Manager     | NULL                                       |
| Steven Thomas | IT Support Manager     | NULL                                       |
| Brian King    | IT Support Manager     | NULL                                       |
| Kevin Hall    | IT Support Manager     | NULL                                       |
| Jason Lee     | IT Support Manager     | NULL                                       |
| Jose Young    | Database Administrator | NULL                                       |
| Eric Jones    | Database Administrator | NULL                                       |
| Jerry Martin  | Database Administrator | NULL                                       |
| Peter King    | Database Administrator | NULL                                       |
| Henry Clark   | Application Developer  | NULL                                       |
| Carl White    | Application Developer  | NULL                                       |
| Jack Smith    | Application Developer  | NULL                                       |
| Roy King      | Application Developer  | NULL                                       |
+---------------+------------------------+--------------------------------------------+
25 rows in set (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM CUSTOMERS;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM ORDERS;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

mysql> SELECT C.USERID,C.NAME,O.ITEMS,O.TOTAL FROM CUSTOMERS AS C LEFT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID;
+--------+-------------+------------------------------+-------+
| USERID | NAME        | ITEMS                        | TOTAL |
+--------+-------------+------------------------------+-------+
|      1 | Jimmy Jones | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | How to train your cat        |    25 |
|      2 | Henry Clark | i7 processor, 8GB RAM Laptop |  1000 |
|      3 | Ruby Young  | Blue Colored Jeans           |   150 |
|      4 | Julia King  | Beautiful Black T-Shirts     |    99 |
|      5 | Anna Jones  | NULL                         |  NULL |
+--------+-------------+------------------------------+-------+

6 rows in set (0.00 sec)


//RIGHT OUTER JOIN
//THE OUTER JOIN IS CREATED BY USING OUTER JOIN KEYWORD;
//THE OUTER JOIN RETURN MATCHED DATA AND ROWS AS WELL AS UNMATCHED DATA AND ROW FROM THE TABLES;
//IN RIGHT OUTER JOIN ALL THE DATA ROWS FROM THE RIGHT TABLE ARE RETURNED;
mysql> USE JOINS;
Database changed
mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.04 sec)

mysql> SELECT * FROM TABLE2;
+---------+
| COLUMN2 |
+---------+
|      12 |
|      15 |
|      50 |
+---------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1 RIGHT OUTER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2;
+---------+---------+
| COLUMN1 | COLUMN2 |
+---------+---------+
|      12 |      12 |
|      15 |      15 |
|    NULL |      50 |
+---------+---------+
3 rows in set (0.02 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Application Developer  |   3800 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.01 sec)

mysql> SELECT * FROM PROJECTS;
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
| projectid | title                                                | clientid | employeeid | startdate           | enddate             |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
|         1 | Develop ecommerse website from scratch               |        1 |          3 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
|         2 | WordPress website for our company                    |        1 |          2 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         3 | Manage our company servers                           |        2 |          7 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         4 | Hosting account is not working                       |        3 |          9 | 2020-05-20 11:33:43 | 2020-05-27 11:33:43 |
|         5 | MySQL database from my desktop application           |        4 |         17 | 2020-05-20 11:33:43 | 2020-06-04 11:33:43 |
|         6 | Develop new WordPress plugin for my business website |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-30 11:33:43 |
|         7 | Migrate web application and database to new server   |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-25 11:33:43 |
|         8 | Android Application development                      |        4 |         23 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
8 rows in set (0.00 sec)

mysql> SELECT NAME,JOBTITLE,TITLE FROM EMPLOYEES RIGHT OUTER JOIN PROJECTS ON EMPLOYEES.EMPLOYYEEID=PROJECTS.EMPLOYEESID;
ERROR 1054 (42S22): Unknown column 'EMPLOYEES.EMPLOYYEEID' in 'on clause'
mysql> SELECT NAME,JOBTITLE,TITLE FROM EMPLOYEES RIGHT OUTER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID;
+--------------+------------------------+------------------------------------------------------+
| NAME         | JOBTITLE               | TITLE                                                |
+--------------+------------------------+------------------------------------------------------+
| James Brown  | Web Developer          | Develop ecommerse website from scratch               |
| Mary Smith   | Web Developer          | WordPress website for our company                    |
| James Smith  | Systems Administrator  | Manage our company servers                           |
| Daniel Jones | Systems Administrator  | Hosting account is not working                       |
| Frank Smith  | Database Administrator | MySQL database from my desktop application           |
| NULL         | NULL                   | Develop new WordPress plugin for my business website |
| NULL         | NULL                   | Migrate web application and database to new server   |
| Joe Thomas   | Application Developer  | Android Application development                      |
+--------------+------------------------+------------------------------------------------------+
8 rows in set (0.01 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM CUSTOMERS;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM ORDERS;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

mysql> SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM  CUSTOMERS AS C RIGHT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|   NULL | NULL        | NULL       | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|   NULL | NULL        | NULL       | Beautiful Black T-Shirts     |    99 |
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
+--------+-------------+------------+------------------------------+-------+
7 rows in set (0.00 sec)

mysql> SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM  CUSTOMERS AS C RIGHT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID ORDER BY C.USERID;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|   NULL | NULL        | NULL       | Healthy dog food recipes     |    19 |
|   NULL | NULL        | NULL       | Beautiful Black T-Shirts     |    99 |
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
+--------+-------------+------------+------------------------------+-------+
7 rows in set (0.01 sec)

mysql> SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM  CUSTOMERS AS C RIGHT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID ORDER BY C.USERID ASC;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|   NULL | NULL        | NULL       | Healthy dog food recipes     |    19 |
|   NULL | NULL        | NULL       | Beautiful Black T-Shirts     |    99 |
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
+--------+-------------+------------+------------------------------+-------+
7 rows in set (0.00 sec)

mysql> SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM  CUSTOMERS AS C RIGHT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID ORDER BY C.USERID DESC;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|   NULL | NULL        | NULL       | Healthy dog food recipes     |    19 |
|   NULL | NULL        | NULL       | Beautiful Black T-Shirts     |    99 |
+--------+-------------+------------+------------------------------+-------+
7 rows in set (0.00 sec)

//FULL OUTER JOIN
//THE OUTER JOIN IS CREATED BY USING OUTER JOIN KEYWORD;
//THE OUTER JOIN RETURN MATCHED DATA AND ROWS AS WELL AS UNMATCHED DATA AND ROW FROM THE TABLES;
//IN FULL OUTER JOIN ALL THE DATA ROWS FROM THE RIGHT TABLE AND THE LEFT TABLE ARE RETURNED;
//MYY SQL DOESNT SUPORT FULL OUTER JOINN WE WILL EMULATE USING UNION OPERATOR;
mysql> USE  JOINS;
Database changed
mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1 LEFT OUTER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2 UNION SELECT * FROM TABLE1 RIGHT OUTER JOIN TABLE2 ON TABL1.COLUMN1=TABLE2.COLUMN2;
ERROR 1054 (42S22): Unknown column 'TABL1.COLUMN1' in 'on clause'
mysql> SELECT * FROM TABLE1 LEFT OUTER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2 UNION SELECT * FROM TABLE1 RIGHT OUTER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2;

+---------+---------+
| COLUMN1 | COLUMN2 |
+---------+---------+
|      11 |    NULL |
|      13 |    NULL |
|      14 |    NULL |
|      12 |      12 |
|      15 |      15 |
|    NULL |      50 |
+---------+---------+
6 rows in set (0.01 sec)


//CROSS JOIN;
// CROSS DOESNT CONTAIN ON CLAUSE;
//UNLIKE INNER JOIN CROSS JOIN RETURNS MATHCED AND UNMATCHED DATA
mysql> USE JOINS;
Database changed
mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE2;
+---------+
| COLUMN2 |
+---------+
|      12 |
|      15 |
|      50 |
+---------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1 CROSS JOIN TABLE2;
+---------+---------+
| COLUMN1 | COLUMN2 |
+---------+---------+
|      11 |      12 |
|      11 |      15 |
|      11 |      50 |
|      13 |      12 |
|      13 |      15 |
|      13 |      50 |
|      14 |      12 |
|      14 |      15 |
|      14 |      50 |
|      12 |      12 |
|      12 |      15 |
|      12 |      50 |
|      15 |      12 |
|      15 |      15 |
|      15 |      50 |
+---------+---------+
15 rows in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Application Developer  |   3800 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT * FROM PROJECTS;
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
| projectid | title                                                | clientid | employeeid | startdate           | enddate             |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
|         1 | Develop ecommerse website from scratch               |        1 |          3 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
|         2 | WordPress website for our company                    |        1 |          2 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         3 | Manage our company servers                           |        2 |          7 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         4 | Hosting account is not working                       |        3 |          9 | 2020-05-20 11:33:43 | 2020-05-27 11:33:43 |
|         5 | MySQL database from my desktop application           |        4 |         17 | 2020-05-20 11:33:43 | 2020-06-04 11:33:43 |
|         6 | Develop new WordPress plugin for my business website |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-30 11:33:43 |
|         7 | Migrate web application and database to new server   |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-25 11:33:43 |
|         8 | Android Application development                      |        4 |         23 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
8 rows in set (0.00 sec)


mysql> SELECT EMPLOYEES.NAME, EMPLOYEES.JOBTITLE,PROJECTS.JOBTITLE FROM EMPLOYEES CROSS JOIN PROJECTS;
ERROR 1054 (42S22): Unknown column 'PROJECTS.JOBTITLE' in 'field list'
mysql> SELECT EMPLOYEES.NAME, EMPLOYEES.JOBTITLE,PROJECTS.TITLE FROM EMPLOYEES CROSS JOIN PROJECTS;
+---------------+------------------------+------------------------------------------------------+
| NAME          | JOBTITLE               | TITLE                                                |
+---------------+------------------------+------------------------------------------------------+
| John Doe      | Web Developer          | Develop ecommerse website from scratch               |
| John Doe      | Web Developer          | WordPress website for our company                    |
| John Doe      | Web Developer          | Manage our company servers                           |
| John Doe      | Web Developer          | Hosting account is not working                       |
| John Doe      | Web Developer          | MySQL database from my desktop application           |
| John Doe      | Web Developer          | Develop new WordPress plugin for my business website |
| John Doe      | Web Developer          | Migrate web application and database to new server   |
| John Doe      | Web Developer          | Android Application development                      |
| Mary Smith    | Web Developer          | Develop ecommerse website from scratch               |
| Mary Smith    | Web Developer          | WordPress website for our company                    |
| Mary Smith    | Web Developer          | Manage our company servers                           |
| Mary Smith    | Web Developer          | Hosting account is not working                       |
| Mary Smith    | Web Developer          | MySQL database from my desktop application           |
| Mary Smith    | Web Developer          | Develop new WordPress plugin for my business website |
| Mary Smith    | Web Developer          | Migrate web application and database to new server   |
| Mary Smith    | Web Developer          | Android Application development                      |
| James Brown   | Web Developer          | Develop ecommerse website from scratch               |
| James Brown   | Web Developer          | WordPress website for our company                    |
| James Brown   | Web Developer          | Manage our company servers                           |
| James Brown   | Web Developer          | Hosting account is not working                       |
| James Brown   | Web Developer          | MySQL database from my desktop application           |
| James Brown   | Web Developer          | Develop new WordPress plugin for my business website |
| James Brown   | Web Developer          | Migrate web application and database to new server   |
| James Brown   | Web Developer          | Android Application development                      |
| Mike Walker   | Web Developer          | Develop ecommerse website from scratch               |
| Mike Walker   | Web Developer          | WordPress website for our company                    |
| Mike Walker   | Web Developer          | Manage our company servers                           |
| Mike Walker   | Web Developer          | Hosting account is not working                       |
| Mike Walker   | Web Developer          | MySQL database from my desktop application           |
| Mike Walker   | Web Developer          | Develop new WordPress plugin for my business website |
| Mike Walker   | Web Developer          | Migrate web application and database to new server   |
| Mike Walker   | Web Developer          | Android Application development                      |
| Linda Jones   | Web Developer          | Develop ecommerse website from scratch               |
| Linda Jones   | Web Developer          | WordPress website for our company                    |
| Linda Jones   | Web Developer          | Manage our company servers                           |
| Linda Jones   | Web Developer          | Hosting account is not working                       |
| Linda Jones   | Web Developer          | MySQL database from my desktop application           |
| Linda Jones   | Web Developer          | Develop new WordPress plugin for my business website |
| Linda Jones   | Web Developer          | Migrate web application and database to new server   |
| Linda Jones   | Web Developer          | Android Application development                      |
| John Doe      | Application Developer  | Develop ecommerse website from scratch               |
| John Doe      | Application Developer  | WordPress website for our company                    |
| John Doe      | Application Developer  | Manage our company servers                           |
| John Doe      | Application Developer  | Hosting account is not working                       |
| John Doe      | Application Developer  | MySQL database from my desktop application           |
| John Doe      | Application Developer  | Develop new WordPress plugin for my business website |
| John Doe      | Application Developer  | Migrate web application and database to new server   |
| John Doe      | Application Developer  | Android Application development                      |
| James Smith   | Systems Administrator  | Develop ecommerse website from scratch               |
| James Smith   | Systems Administrator  | WordPress website for our company                    |
| James Smith   | Systems Administrator  | Manage our company servers                           |
| James Smith   | Systems Administrator  | Hosting account is not working                       |
| James Smith   | Systems Administrator  | MySQL database from my desktop application           |
| James Smith   | Systems Administrator  | Develop new WordPress plugin for my business website |
| James Smith   | Systems Administrator  | Migrate web application and database to new server   |
| James Smith   | Systems Administrator  | Android Application development                      |
| John Brown    | Systems Administrator  | Develop ecommerse website from scratch               |
| John Brown    | Systems Administrator  | WordPress website for our company                    |
| John Brown    | Systems Administrator  | Manage our company servers                           |
| John Brown    | Systems Administrator  | Hosting account is not working                       |
| John Brown    | Systems Administrator  | MySQL database from my desktop application           |
| John Brown    | Systems Administrator  | Develop new WordPress plugin for my business website |
| John Brown    | Systems Administrator  | Migrate web application and database to new server   |
| John Brown    | Systems Administrator  | Android Application development                      |
| Daniel Jones  | Systems Administrator  | Develop ecommerse website from scratch               |
| Daniel Jones  | Systems Administrator  | WordPress website for our company                    |
| Daniel Jones  | Systems Administrator  | Manage our company servers                           |
| Daniel Jones  | Systems Administrator  | Hosting account is not working                       |
| Daniel Jones  | Systems Administrator  | MySQL database from my desktop application           |
| Daniel Jones  | Systems Administrator  | Develop new WordPress plugin for my business website |
| Daniel Jones  | Systems Administrator  | Migrate web application and database to new server   |
| Daniel Jones  | Systems Administrator  | Android Application development                      |
| Paul Anderson | Systems Administrator  | Develop ecommerse website from scratch               |
| Paul Anderson | Systems Administrator  | WordPress website for our company                    |
| Paul Anderson | Systems Administrator  | Manage our company servers                           |
| Paul Anderson | Systems Administrator  | Hosting account is not working                       |
| Paul Anderson | Systems Administrator  | MySQL database from my desktop application           |
| Paul Anderson | Systems Administrator  | Develop new WordPress plugin for my business website |
| Paul Anderson | Systems Administrator  | Migrate web application and database to new server   |
| Paul Anderson | Systems Administrator  | Android Application development                      |
| Mark Davis    | IT Support Manager     | Develop ecommerse website from scratch               |
| Mark Davis    | IT Support Manager     | WordPress website for our company                    |
| Mark Davis    | IT Support Manager     | Manage our company servers                           |
| Mark Davis    | IT Support Manager     | Hosting account is not working                       |
| Mark Davis    | IT Support Manager     | MySQL database from my desktop application           |
| Mark Davis    | IT Support Manager     | Develop new WordPress plugin for my business website |
| Mark Davis    | IT Support Manager     | Migrate web application and database to new server   |
| Mark Davis    | IT Support Manager     | Android Application development                      |
| Steven Thomas | IT Support Manager     | Develop ecommerse website from scratch               |
| Steven Thomas | IT Support Manager     | WordPress website for our company                    |
| Steven Thomas | IT Support Manager     | Manage our company servers                           |
| Steven Thomas | IT Support Manager     | Hosting account is not working                       |
| Steven Thomas | IT Support Manager     | MySQL database from my desktop application           |
| Steven Thomas | IT Support Manager     | Develop new WordPress plugin for my business website |
| Steven Thomas | IT Support Manager     | Migrate web application and database to new server   |
| Steven Thomas | IT Support Manager     | Android Application development                      |
| Brian King    | IT Support Manager     | Develop ecommerse website from scratch               |
| Brian King    | IT Support Manager     | WordPress website for our company                    |
| Brian King    | IT Support Manager     | Manage our company servers                           |
| Brian King    | IT Support Manager     | Hosting account is not working                       |
| Brian King    | IT Support Manager     | MySQL database from my desktop application           |
| Brian King    | IT Support Manager     | Develop new WordPress plugin for my business website |
| Brian King    | IT Support Manager     | Migrate web application and database to new server   |
| Brian King    | IT Support Manager     | Android Application development                      |
| Kevin Hall    | IT Support Manager     | Develop ecommerse website from scratch               |
| Kevin Hall    | IT Support Manager     | WordPress website for our company                    |
| Kevin Hall    | IT Support Manager     | Manage our company servers                           |
| Kevin Hall    | IT Support Manager     | Hosting account is not working                       |
| Kevin Hall    | IT Support Manager     | MySQL database from my desktop application           |
| Kevin Hall    | IT Support Manager     | Develop new WordPress plugin for my business website |
| Kevin Hall    | IT Support Manager     | Migrate web application and database to new server   |
| Kevin Hall    | IT Support Manager     | Android Application development                      |
| Jason Lee     | IT Support Manager     | Develop ecommerse website from scratch               |
| Jason Lee     | IT Support Manager     | WordPress website for our company                    |
| Jason Lee     | IT Support Manager     | Manage our company servers                           |
| Jason Lee     | IT Support Manager     | Hosting account is not working                       |
| Jason Lee     | IT Support Manager     | MySQL database from my desktop application           |
| Jason Lee     | IT Support Manager     | Develop new WordPress plugin for my business website |
| Jason Lee     | IT Support Manager     | Migrate web application and database to new server   |
| Jason Lee     | IT Support Manager     | Android Application development                      |
| Jose Young    | Database Administrator | Develop ecommerse website from scratch               |
| Jose Young    | Database Administrator | WordPress website for our company                    |
| Jose Young    | Database Administrator | Manage our company servers                           |
| Jose Young    | Database Administrator | Hosting account is not working                       |
| Jose Young    | Database Administrator | MySQL database from my desktop application           |
| Jose Young    | Database Administrator | Develop new WordPress plugin for my business website |
| Jose Young    | Database Administrator | Migrate web application and database to new server   |
| Jose Young    | Database Administrator | Android Application development                      |
| Frank Smith   | Database Administrator | Develop ecommerse website from scratch               |
| Frank Smith   | Database Administrator | WordPress website for our company                    |
| Frank Smith   | Database Administrator | Manage our company servers                           |
| Frank Smith   | Database Administrator | Hosting account is not working                       |
| Frank Smith   | Database Administrator | MySQL database from my desktop application           |
| Frank Smith   | Database Administrator | Develop new WordPress plugin for my business website |
| Frank Smith   | Database Administrator | Migrate web application and database to new server   |
| Frank Smith   | Database Administrator | Android Application development                      |
| Eric Jones    | Database Administrator | Develop ecommerse website from scratch               |
| Eric Jones    | Database Administrator | WordPress website for our company                    |
| Eric Jones    | Database Administrator | Manage our company servers                           |
| Eric Jones    | Database Administrator | Hosting account is not working                       |
| Eric Jones    | Database Administrator | MySQL database from my desktop application           |
| Eric Jones    | Database Administrator | Develop new WordPress plugin for my business website |
| Eric Jones    | Database Administrator | Migrate web application and database to new server   |
| Eric Jones    | Database Administrator | Android Application development                      |
| Jerry Martin  | Database Administrator | Develop ecommerse website from scratch               |
| Jerry Martin  | Database Administrator | WordPress website for our company                    |
| Jerry Martin  | Database Administrator | Manage our company servers                           |
| Jerry Martin  | Database Administrator | Hosting account is not working                       |
| Jerry Martin  | Database Administrator | MySQL database from my desktop application           |
| Jerry Martin  | Database Administrator | Develop new WordPress plugin for my business website |
| Jerry Martin  | Database Administrator | Migrate web application and database to new server   |
| Jerry Martin  | Database Administrator | Android Application development                      |
| Peter King    | Database Administrator | Develop ecommerse website from scratch               |
| Peter King    | Database Administrator | WordPress website for our company                    |
| Peter King    | Database Administrator | Manage our company servers                           |
| Peter King    | Database Administrator | Hosting account is not working                       |
| Peter King    | Database Administrator | MySQL database from my desktop application           |
| Peter King    | Database Administrator | Develop new WordPress plugin for my business website |
| Peter King    | Database Administrator | Migrate web application and database to new server   |
| Peter King    | Database Administrator | Android Application development                      |
| Henry Clark   | Application Developer  | Develop ecommerse website from scratch               |
| Henry Clark   | Application Developer  | WordPress website for our company                    |
| Henry Clark   | Application Developer  | Manage our company servers                           |
| Henry Clark   | Application Developer  | Hosting account is not working                       |
| Henry Clark   | Application Developer  | MySQL database from my desktop application           |
| Henry Clark   | Application Developer  | Develop new WordPress plugin for my business website |
| Henry Clark   | Application Developer  | Migrate web application and database to new server   |
| Henry Clark   | Application Developer  | Android Application development                      |
| Carl White    | Application Developer  | Develop ecommerse website from scratch               |
| Carl White    | Application Developer  | WordPress website for our company                    |
| Carl White    | Application Developer  | Manage our company servers                           |
| Carl White    | Application Developer  | Hosting account is not working                       |
| Carl White    | Application Developer  | MySQL database from my desktop application           |
| Carl White    | Application Developer  | Develop new WordPress plugin for my business website |
| Carl White    | Application Developer  | Migrate web application and database to new server   |
| Carl White    | Application Developer  | Android Application development                      |
| Joe Thomas    | Application Developer  | Develop ecommerse website from scratch               |
| Joe Thomas    | Application Developer  | WordPress website for our company                    |
| Joe Thomas    | Application Developer  | Manage our company servers                           |
| Joe Thomas    | Application Developer  | Hosting account is not working                       |
| Joe Thomas    | Application Developer  | MySQL database from my desktop application           |
| Joe Thomas    | Application Developer  | Develop new WordPress plugin for my business website |
| Joe Thomas    | Application Developer  | Migrate web application and database to new server   |
| Joe Thomas    | Application Developer  | Android Application development                      |
| Jack Smith    | Application Developer  | Develop ecommerse website from scratch               |
| Jack Smith    | Application Developer  | WordPress website for our company                    |
| Jack Smith    | Application Developer  | Manage our company servers                           |
| Jack Smith    | Application Developer  | Hosting account is not working                       |
| Jack Smith    | Application Developer  | MySQL database from my desktop application           |
| Jack Smith    | Application Developer  | Develop new WordPress plugin for my business website |
| Jack Smith    | Application Developer  | Migrate web application and database to new server   |
| Jack Smith    | Application Developer  | Android Application development                      |
| Roy King      | Application Developer  | Develop ecommerse website from scratch               |
| Roy King      | Application Developer  | WordPress website for our company                    |
| Roy King      | Application Developer  | Manage our company servers                           |
| Roy King      | Application Developer  | Hosting account is not working                       |
| Roy King      | Application Developer  | MySQL database from my desktop application           |
| Roy King      | Application Developer  | Develop new WordPress plugin for my business website |
| Roy King      | Application Developer  | Migrate web application and database to new server   |
| Roy King      | Application Developer  | Android Application development                      |
+---------------+------------------------+------------------------------------------------------+
200 rows in set (0.00 sec)

//UNION OPERATOR 
COMBINE THE RESULT SET OF TWO OR MORE SELECT STATEMENTS;
EVERY SELECT STATEMENT MUST HAVE SIMILAR NUMBER OF COLUMNS;
THE COLUMNS IN SELECT MUST BE IN THE SAME ORDER AND HABE ALL THE SIMILAR DATA TYPES;
THE UNION OPERATOR SELECTS ONLY DISTINCT VALUES.THE UNION ALL OPERATOR IS USED TO SELECT DUPLICATE VALUE;

mysql> USE SCHOOL;
Database changed
mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.01 sec)

mysql> SELECT * FROM TEACHERS;
+-----------+----------------+------------+
| teacherid | name           | phone      |
+-----------+----------------+------------+
|         1 | John Doe       | 1234567890 |
|         2 | Caroline Smith | 0987654321 |
|         3 | Jason King     | 1234512345 |
|         4 | Stella Brown   | 0987612345 |
|         5 | Eric Hall      | 0987609876 |
|         6 | Peter Brown    | 123435454  |
+-----------+----------------+------------+
6 rows in set (0.00 sec)

mysql> SELECT * FROM STUDENTS UNION SELECT * FROM TEACHERS;
ERROR 1222 (21000): The used SELECT statements have a different number of columns
mysql> USE JOINS;
Database changed
mysql> SELECT * FROM TABLE1;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
+---------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE2;
+---------+
| COLUMN2 |
+---------+
|      12 |
|      15 |
|      50 |
+---------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1 UNION SELECT * FROM TABLE2;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
|      50 |
+---------+
6 rows in set (0.00 sec)

mysql> SELECT * FROM TABLE1 UNION ALL SELECT * FROM TABLE2;
+---------+
| COLUMN1 |
+---------+
|      11 |
|      13 |
|      14 |
|      12 |
|      15 |
|      12 |
|      15 |
|      50 |
+---------+
8 rows in set (0.00 sec)

///SQL VIEWS;
VIEW IS A DATABASE OBJECT THAT CAN BE CREATED LIKE A TABLE;
A VIEW IS A SIMILAR TO A VIRTUAL TABLE UNLIKE TABLE VIEWS DONT ACTUALLY STORE DATA
VIEWS ARE COMPLEX SELECT STATEMENT USED ASA VIRTUAL TABLES FOR EASE OF REFERENCE AND REUSE;
THE VIEWS ARE USEFUL FRO STORING COMPLEX SQL STATEMENTS AS VIRTUAL TABLES AND THE REQUEST THE VIES AS SINGLE TABLE INSTEAD OF COMPLEX SUBQUERY;
WE CAN RESTRICT USERS FROM ACCESSING UNDELYING TABLES AND INSTEAD GIVE ACCESS TO VIEWS WITH LIMITED COLUMNS;
SINCE EVERY TIME USER REQUEST VIEW ,DATABASE ENGINE RECREATE RESULT SET WHICH IS ALWAYS RETURNS UP TO DATE ROWS FROM VIEWS;

mysql> USE COMPANY;
Database changed
mysql> CREATE VIEW ACTIVE_PROJECTS AS SELECT  EMPLOYEES.NAME,EMPLOYEES.JOBTITLE,PROJECTS.TITLE FROM EMPLOYEES INNER JOIN PROHECTS OJN EMPLYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID;

mysql> CREATE VIEW ACTIVE_PROJECTS AS SELECT  EMPLOYEES.NAME,EMPLOYEES.JOBTITLE,PROJECTS.TITLE FROM EMPLOYEES INNER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID;
Query OK, 0 rows affected (0.07 sec)

mysql> SELECT & FROM ACTIVE_PROJECTS;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '& FROM ACTIVE_PROJECTS' at line 1
mysql> SELECT * FROM ACTIVE_PROJECTS;
+--------------+------------------------+--------------------------------------------+
| NAME         | JOBTITLE               | TITLE                                      |
+--------------+------------------------+--------------------------------------------+
| James Brown  | Web Developer          | Develop ecommerse website from scratch     |
| Mary Smith   | Web Developer          | WordPress website for our company          |
| James Smith  | Systems Administrator  | Manage our company servers                 |
| Daniel Jones | Systems Administrator  | Hosting account is not working             |
| Frank Smith  | Database Administrator | MySQL database from my desktop application |
| Joe Thomas   | Application Developer  | Android Application development            |
+--------------+------------------------+--------------------------------------------+
6 rows in set (0.01 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> CREATE VIEW PURCHASED_HISTORY AS SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM CUSTOMERS AS C LEFT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID;
Query OK, 0 rows affected (0.01 sec)

mysql> SELECT * FROM PURCHASED_HISTORY;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
|      5 | Anna Jones  | 0987609876 | NULL                         |  NULL |
+--------+-------------+------------+------------------------------+-------+
6 rows in set (0.00 sec)

mysql> CREATE OR REPLACE VIEW VIEW PURCHASED_HISTORY AS SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM CUSTOMERS AS C RIGHT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'PURCHASED_HISTORY AS SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM CUSTOME' at line 1
mysql> CREATE OR REPLACE VIEW  PURCHASED_HISTORY AS SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM CUSTOMERS AS C RIGHT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID;
Query OK, 0 rows affected (0.02 sec)

mysql> SELECT * FROM PURCHASED_HISTORY;
+--------+-------------+------------+------------------------------+-------+
| USERID | NAME        | PHONE      | ITEMS                        | TOTAL |
+--------+-------------+------------+------------------------------+-------+
|      2 | Henry Clark | 0987654321 | i7 processor, 8GB RAM Laptop |  1000 |
|      1 | Jimmy Jones | 1234567890 | Healthy dog food recipes     |    19 |
|   NULL | NULL        | NULL       | Healthy dog food recipes     |    19 |
|      1 | Jimmy Jones | 1234567890 | How to train your cat        |    25 |
|      3 | Ruby Young  | 1234512345 | Blue Colored Jeans           |   150 |
|   NULL | NULL        | NULL       | Beautiful Black T-Shirts     |    99 |
|      4 | Julia King  | 0987612345 | Beautiful Black T-Shirts     |    99 |
+--------+-------------+------------+------------------------------+-------+
7 rows in set (0.00 sec)

mysql> DROP VIEW PURCHASED_HISTORY;
Query OK, 0 rows affected (0.01 sec)

mysql> SELECT * FROM PURCHASED_HISTORY;
ERROR 1146 (42S02): Table 'onlineshop.purchased_history' doesn't exist


///DERIVED TABLES AND INLINE VIEWS
EVERY DERIVED TABLE IS A SUBQUERY IN PARENTHESIS FROM WHICH WE CAN SELECT THE DATA COLUMNS IN THE MAIN QUERY;
THE SUBQUERY IN PARETHESIS FORMS TABULAR STRUCTURE WHICH IS A SOURCE OF DATA FOR OUTER OR MAIN QUERY;
EVERY DERIVED TABLES MUST HAVE A NAME USING THE AS KEYWORD;
UNLIKE VIEWS IN DERIVED TABLES THE INTERMEDIATE TABLES ARE CREATED USING DIRECTLY INLINE OR WITHIN SQL STATEMENTS

mysql> USE COMPANY;
Database changed
mysql> SELECT NAME,TITLE FROM (SELECT EMPLOYEES.NAME,EMPLOYEES.JOBTITLE,PROJECTS.TITLE FROM EMPLOYEES INNER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID) AS ACTIVE PROJECTS;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'PROJECTS' at line 1
mysql> SELECT NAME,TITLE FROM (SELECT EMPLOYEES.NAME,EMPLOYEES.JOBTITLE,PROJECTS.TITLE FROM EMPLOYEES INNER JOIN PROJECTS ON EMPLOYEES.EMPLOYEEID=PROJECTS.EMPLOYEEID) AS ACTIVE_PROJECTS;
+--------------+--------------------------------------------+
| NAME         | TITLE                                      |
+--------------+--------------------------------------------+
| James Brown  | Develop ecommerse website from scratch     |
| Mary Smith   | WordPress website for our company          |
| James Smith  | Manage our company servers                 |
| Daniel Jones | Hosting account is not working             |
| Frank Smith  | MySQL database from my desktop application |
| Joe Thomas   | Android Application development            |
+--------------+--------------------------------------------+
6 rows in set (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT NAME,ITEMS,TOTAL FROM (SELECT C.USERID,C.NAME,C.PHONE,O.ITEMS,O.TOTAL FROM CUSTOMERS AS C LEFT OUTER JOIN ORDERS AS O ON C.USERID=O.USERID) AS PURCHASED_HISTORY;
+-------------+------------------------------+-------+
| NAME        | ITEMS                        | TOTAL |
+-------------+------------------------------+-------+
| Jimmy Jones | Healthy dog food recipes     |    19 |
| Jimmy Jones | How to train your cat        |    25 |
| Henry Clark | i7 processor, 8GB RAM Laptop |  1000 |
| Ruby Young  | Blue Colored Jeans           |   150 |
| Julia King  | Beautiful Black T-Shirts     |    99 |
| Anna Jones  | NULL                         |  NULL |
+-------------+------------------------------+-------+
6 rows in set (0.00 sec)

///SQL FUNCTIONS
TWO TYPES OF FUNCTIONS 
AGGREGATE FUNCTIONS AND SCALAR FUNCTIONS

AGGREGATE FUNCTIONS:
ONLY WORK ON GROUP OF Rows TO RETURN A SINGLE AGGREGATE RESULT VALUE;
EX: COUNT,MIN,MAX,SUM,AVG

SCALAR FUNCTIONS:
ONLY WORK ON INPUT VALUES TO RETURN SINGLE RESULT VALUE
EX: LEN,ROUND,SUBSTRING,CASE,NOW


//SQL COUNT : IT DOES NOT COUNT NULL VALUES

mysql> USE SCHOOL;
Database changed
mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> SELECT COUNT(*) FROM STUDENTS;
+----------+
| COUNT(*) |
+----------+
|       58 |
+----------+
1 row in set (0.02 sec)

mysql> SELECT COUNT(*) AS 'TOTAL ROWS' FROM STUDENTS;
+------------+
| TOTAL ROWS |
+------------+
|         58 |
+------------+
1 row in set (0.00 sec)

mysql> SELECT COUNT(DISTINCT CLASS)FROM STUDENTS;
+-----------------------+
| COUNT(DISTINCT CLASS) |
+-----------------------+
|                     3 |
+-----------------------+
1 row in set (0.01 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT E.EMPLOYEEID ,E.NAME,E.JOBTITLE,P.TITLE FROM EMPLOYEES AS E LEFT OUTER JOIN PROJECTS AS P ON E.EMPLOYEEID=P.EMPLOYEEID;
+------------+---------------+------------------------+--------------------------------------------+
| EMPLOYEEID | NAME          | JOBTITLE               | TITLE                                      |
+------------+---------------+------------------------+--------------------------------------------+
|          1 | John Doe      | Web Developer          | NULL                                       |
|          2 | Mary Smith    | Web Developer          | WordPress website for our company          |
|          3 | James Brown   | Web Developer          | Develop ecommerse website from scratch     |
|          4 | Mike Walker   | Web Developer          | NULL                                       |
|          5 | Linda Jones   | Web Developer          | NULL                                       |
|          6 | John Doe      | Application Developer  | NULL                                       |
|          7 | James Smith   | Systems Administrator  | Manage our company servers                 |
|          8 | John Brown    | Systems Administrator  | NULL                                       |
|          9 | Daniel Jones  | Systems Administrator  | Hosting account is not working             |
|         10 | Paul Anderson | Systems Administrator  | NULL                                       |
|         11 | Mark Davis    | IT Support Manager     | NULL                                       |
|         12 | Steven Thomas | IT Support Manager     | NULL                                       |
|         13 | Brian King    | IT Support Manager     | NULL                                       |
|         14 | Kevin Hall    | IT Support Manager     | NULL                                       |
|         15 | Jason Lee     | IT Support Manager     | NULL                                       |
|         16 | Jose Young    | Database Administrator | NULL                                       |
|         17 | Frank Smith   | Database Administrator | MySQL database from my desktop application |
|         18 | Eric Jones    | Database Administrator | NULL                                       |
|         19 | Jerry Martin  | Database Administrator | NULL                                       |
|         20 | Peter King    | Database Administrator | NULL                                       |
|         21 | Henry Clark   | Application Developer  | NULL                                       |
|         22 | Carl White    | Application Developer  | NULL                                       |
|         23 | Joe Thomas    | Application Developer  | Android Application development            |
|         24 | Jack Smith    | Application Developer  | NULL                                       |
|         25 | Roy King      | Application Developer  | NULL                                       |
+------------+---------------+------------------------+--------------------------------------------+
25 rows in set (0.00 sec)

mysql> SELECT E.EMPLOYEEID ,E.NAME,E.JOBTITLE,P.TITLE FROM EMPLOYEES AS E LEFT OUTER JOIN PROJECTS AS P ON E.EMPLOYEEID=P.EMPLOYEEID ORFER BY TITLE;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'ORFER BY TITLE' at line 1
mysql> SELECT E.EMPLOYEEID ,E.NAME,E.JOBTITLE,P.TITLE FROM EMPLOYEES AS E LEFT OUTER JOIN PROJECTS AS P ON E.EMPLOYEEID=P.EMPLOYEEID ORDER BY TITLE;
+------------+---------------+------------------------+--------------------------------------------+
| EMPLOYEEID | NAME          | JOBTITLE               | TITLE                                      |
+------------+---------------+------------------------+--------------------------------------------+
|          1 | John Doe      | Web Developer          | NULL                                       |
|          4 | Mike Walker   | Web Developer          | NULL                                       |
|          5 | Linda Jones   | Web Developer          | NULL                                       |
|          6 | John Doe      | Application Developer  | NULL                                       |
|          8 | John Brown    | Systems Administrator  | NULL                                       |
|         10 | Paul Anderson | Systems Administrator  | NULL                                       |
|         11 | Mark Davis    | IT Support Manager     | NULL                                       |
|         12 | Steven Thomas | IT Support Manager     | NULL                                       |
|         13 | Brian King    | IT Support Manager     | NULL                                       |
|         14 | Kevin Hall    | IT Support Manager     | NULL                                       |
|         15 | Jason Lee     | IT Support Manager     | NULL                                       |
|         16 | Jose Young    | Database Administrator | NULL                                       |
|         18 | Eric Jones    | Database Administrator | NULL                                       |
|         19 | Jerry Martin  | Database Administrator | NULL                                       |
|         20 | Peter King    | Database Administrator | NULL                                       |
|         21 | Henry Clark   | Application Developer  | NULL                                       |
|         22 | Carl White    | Application Developer  | NULL                                       |
|         24 | Jack Smith    | Application Developer  | NULL                                       |
|         25 | Roy King      | Application Developer  | NULL                                       |
|         23 | Joe Thomas    | Application Developer  | Android Application development            |
|          3 | James Brown   | Web Developer          | Develop ecommerse website from scratch     |
|          9 | Daniel Jones  | Systems Administrator  | Hosting account is not working             |
|          7 | James Smith   | Systems Administrator  | Manage our company servers                 |
|         17 | Frank Smith   | Database Administrator | MySQL database from my desktop application |
|          2 | Mary Smith    | Web Developer          | WordPress website for our company          |
+------------+---------------+------------------------+--------------------------------------------+
25 rows in set (0.00 sec)

mysql> SELECT COUNT(P.TITLE) FROM EMPLOYEES AS E LEFT OUTER JOIN PROJECTS AS P ON E.EMPLOYEEID=P.EMPLOYEEID ORDER BY TITLE;
+----------------+
| COUNT(P.TITLE) |
+----------------+
|              6 |
+----------------+
1 row in set (0.00 sec)

///SQL FIRST ONLY SUPPORTED IN MS ACCESS
mysql> USE SCHOOL;
Database changed
mysql> SELECT FIRSTNAME FROM STUDENTS LIMIT 1;
+-----------+
| FIRSTNAME |
+-----------+
| John      |
+-----------+
1 row in set (0.00 sec)

mysql> SELECT LASTNAME FROM STUDENTS LIMIT 1;
+----------+
| LASTNAME |
+----------+
| Doe      |
+----------+
1 row in set (0.00 sec)

mysql>

///SQL LAST ONLY SUPPORTED IN MS ACCESS
///SQL SUM TOTAL ONLY WORK ON NUMERIC COLUMNS AND FOR STRING VALUE IT GIVES OR RETURNS 0;
//SQL MIN FUNCTIONS WORKS ON NUMERIC AND STRING COLUMNS
//SQL MAX FUNCTIONS WORKS ON NUMERIC AND STRING COLUMNS
///SQL AVG TOTAL ONLY WORK ON NUMERIC COLUMNS AND FOR STRING VALUE IT GIVES OR RETURNS 0;
/// SQL UCASE/LCASE FUNCTION STRING DATA VALUES IN UPPER CASE AND WORKS ONLY STRING FUNCTIONS
/// SQL MID FUNCTION EXTRACTS CHARACTERS FROM THE GIVEN STRING DATA AND ONLY WORKS ON STRING COLUMNS;
///SQL LEN LENGTH ONLY WORK ON STRING COLUMNS AND DOESN NOT WORK IN MYSQL;
//SQL ROUND ONLY WORK IN NUMERIC COLUMN AND IS USED TO ROUND A FLOATING POINT NUMBER 
//SQL FROMAT ONLY WORK IN NUMERIC COLUMN AND IS USED TO ROUND A FLOATING POINT NUMBER TO A GIVEN DECIMAL NUMBER
/// SQL SUBSTRING FUNCTION EXTRACTS CHARACTERS FROM THE GIVEN STRING DATA AND ONLY WORKS ON STRING COLUMNS;
/// SQL COALESCE FUNCTION RETURNS THE FIRST NON NULL VALUE FROM THE GIVEN THE LIST ;
IF THERE ARE NO NON NULL VALUES THE COALESCE FUNCTIONS RETURNS NULL
//SQL CHAR LENGTH RETURN THE LENGTH OF THE LENGTH OF THE GIVEN STRING LENGTH AND FUNCTIONS WORKS ON NUMERIC AND STRING COLUMNS
//SQL CAST FUNTION IS USED TO CHANGE THE DATA TYPE OF A VALUE;IS VERY USEFUL WHILE IMPORTIN AND EXPORTING THE DATA TYPE OF A VALUE;
///THE CASE FUNCTION RETURN VALUE OR NULL BY EVALUATING SERIES OF CONDITIONS;
//THE CASE FUNCTION CONDITIONS ARE MADE UP OF KEWORDS WHEN,THEN, ELSE AND END;
//THE CASE FUNCTION WORKS SIMILAR TO IF ELSE CONSTION IN PROGRAMMING LANGUAGEB
// THE CASE FUNCTION EVALUATES STRING AS WELL AS NUMERIC VALUES;
IN SAMPLE CASE AS AN EXPRESSION IS COMPARED TO STATIC VALUES WHILE IN SEARCHED CASE AN EXPRESSION IS COMPARED TO MUTLIPLE LOGICAL CONDITONS;
//SQL NULLIF THE NULLIFY RETURNS NULL VALUE IF THE TWO PARAMETERS VALUES ARE EQUAL .IF THE FUNCTION EVALUATES STRING ASA WELL AS NUMERIC VALUES;

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> SELECT LASTNAME FROM STUDENTS  ORDER BY LASTNAME DESC LIMIT 1;
+----------+
| LASTNAME |
+----------+
| Young    |
+----------+
1 row in set (0.00 sec)

mysql> SELECT FIRSTNAME FROM STUDENTS  ORDER BY FIRSTNAME DESC LIMIT 1;
+-----------+
| FIRSTNAME |
+-----------+
| Zoe       |
+-----------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT SUM(AGE) FROM STUDENTS;
+----------+
| SUM(AGE) |
+----------+
|      347 |
+----------+
1 row in set (0.00 sec)

mysql> SELECT SUM(FIRSTNAME) FROM STUDENTS;
+----------------+
| SUM(FIRSTNAME) |
+----------------+
|              0 |
+----------------+
1 row in set, 58 warnings (0.00 sec)

mysql> SELECT SUM(FIRSTNAME) AS TOTAL FROM STUDENTS;
+-------+
| TOTAL |
+-------+
|     0 |
+-------+
1 row in set, 58 warnings (0.00 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM ORDERS;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.00 sec)

mysql> SELECT SUM(TOTAL) AS 'Total' from orders;
+-------+
| Total |
+-------+
|  1411 |
+-------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT MIN(AGE) FROM STUDENTS;
+----------+
| MIN(AGE) |
+----------+
|        5 |
+----------+
1 row in set (0.00 sec)

mysql> SELECT MIN(FIRSTNAME) FROM STUDENTS;
+----------------+
| MIN(FIRSTNAME) |
+----------------+
| Adam           |
+----------------+
1 row in set (0.00 sec)

mysql> SELECT MIN(LASTNAME) FROM STUDENTS;
+---------------+
| MIN(LASTNAME) |
+---------------+
| Anderson      |
+---------------+
1 row in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM EMPLOYEES;
+------------+---------------+------------------------+--------+
| employeeid | name          | jobtitle               | salary |
+------------+---------------+------------------------+--------+
|          1 | John Doe      | Web Developer          |   3500 |
|          2 | Mary Smith    | Web Developer          |   3500 |
|          3 | James Brown   | Web Developer          |   3500 |
|          4 | Mike Walker   | Web Developer          |   3500 |
|          5 | Linda Jones   | Web Developer          |   3500 |
|          6 | John Doe      | Application Developer  |   3800 |
|          7 | James Smith   | Systems Administrator  |   3400 |
|          8 | John Brown    | Systems Administrator  |   3400 |
|          9 | Daniel Jones  | Systems Administrator  |   3400 |
|         10 | Paul Anderson | Systems Administrator  |   3400 |
|         11 | Mark Davis    | IT Support Manager     |   3200 |
|         12 | Steven Thomas | IT Support Manager     |   3200 |
|         13 | Brian King    | IT Support Manager     |   3200 |
|         14 | Kevin Hall    | IT Support Manager     |   3200 |
|         15 | Jason Lee     | IT Support Manager     |   3200 |
|         16 | Jose Young    | Database Administrator |   3700 |
|         17 | Frank Smith   | Database Administrator |   3700 |
|         18 | Eric Jones    | Database Administrator |   3700 |
|         19 | Jerry Martin  | Database Administrator |   3700 |
|         20 | Peter King    | Database Administrator |   3700 |
|         21 | Henry Clark   | Application Developer  |   3800 |
|         22 | Carl White    | Application Developer  |   3800 |
|         23 | Joe Thomas    | Application Developer  |   3800 |
|         24 | Jack Smith    | Application Developer  |   3800 |
|         25 | Roy King      | Application Developer  |   3800 |
+------------+---------------+------------------------+--------+
25 rows in set (0.00 sec)

mysql> SELECT MIN(SALARY) AS 'Minimum Salary' from EMPLOYEES;
+----------------+
| Minimum Salary |
+----------------+
|           3200 |
+----------------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT MAX(AGE) FROM STUDENTS;
+----------+
| MAX(AGE) |
+----------+
|        7 |
+----------+
1 row in set (0.00 sec)

mysql> SELECT MAX(FIRSTNAME) FROM STUDENTS;
+----------------+
| MAX(FIRSTNAME) |
+----------------+
| Zoe            |
+----------------+
1 row in set (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT MAX(SALARY) AS 'Minimum Salary' from EMPLOYEES;
+----------------+
| Minimum Salary |
+----------------+
|           3800 |
+----------------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT AVG(AGE) FROM STUDENTS;
+----------+
| AVG(AGE) |
+----------+
|   5.9828 |
+----------+
1 row in set (0.00 sec)

mysql> SELECT AVG(FIRSTNAME) FROM STUDENTS;
+----------------+
| AVG(FIRSTNAME) |
+----------------+
|              0 |
+----------------+
1 row in set, 58 warnings (0.00 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT AVG(SALARY) AS 'Average Salary' from EMPLOYEES;
+----------------+
| Average Salary |
+----------------+
|           3536 |
+----------------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT UCASE(FIRSTNAME) FROM STUDENTS;
+------------------+
| UCASE(FIRSTNAME) |
+------------------+
| JOHN             |
| MARY             |
| JAMES            |
| MIKE             |
| LINDA            |
| JOHN             |
| JAMES            |
| JOHN             |
| DANIEL           |
| PAUL             |
| MARK             |
| STEVEN           |
| BRIAN            |
| KEVIN            |
| JASON            |
| JOSE             |
| FRANK            |
| ERIC             |
| JERRY            |
| PETER            |
| HENRY            |
| CARL             |
| JOE              |
| JACK             |
| ROY              |
| ADAM             |
| BOBBY            |
| JOHNNY           |
| JIMMY            |
| EMMA             |
| SOPHIA           |
| AVA              |
| MIA              |
| EMILY            |
| GRACE            |
| LILLIAN          |
| LILY             |
| LAYLA            |
| ZOE              |
| ANNA             |
| LEAH             |
| CAMILA           |
| RILEY            |
| NORA             |
| HAILEY           |
| ELLIE            |
| LUCY             |
| STELLA           |
| BELLA            |
| MILA             |
| MAYA             |
| FAITH            |
| EVA              |
| JULIA            |
| ASHLEY           |
| RUBY             |
| ALICE            |
| JASMINE          |
+------------------+
58 rows in set (0.01 sec)

mysql> USE COMPANY;
Database changed
mysql> SELECT UCASE(NAME) from EMPLOYEES;
+---------------+
| UCASE(NAME)   |
+---------------+
| JOHN DOE      |
| MARY SMITH    |
| JAMES BROWN   |
| MIKE WALKER   |
| LINDA JONES   |
| JOHN DOE      |
| JAMES SMITH   |
| JOHN BROWN    |
| DANIEL JONES  |
| PAUL ANDERSON |
| MARK DAVIS    |
| STEVEN THOMAS |
| BRIAN KING    |
| KEVIN HALL    |
| JASON LEE     |
| JOSE YOUNG    |
| FRANK SMITH   |
| ERIC JONES    |
| JERRY MARTIN  |
| PETER KING    |
| HENRY CLARK   |
| CARL WHITE    |
| JOE THOMAS    |
| JACK SMITH    |
| ROY KING      |
+---------------+
25 rows in set (0.00 sec)

mysql> SELECT LCASE(NAME) from EMPLOYEES;
+---------------+
| LCASE(NAME)   |
+---------------+
| john doe      |
| mary smith    |
| james brown   |
| mike walker   |
| linda jones   |
| john doe      |
| james smith   |
| john brown    |
| daniel jones  |
| paul anderson |
| mark davis    |
| steven thomas |
| brian king    |
| kevin hall    |
| jason lee     |
| jose young    |
| frank smith   |
| eric jones    |
| jerry martin  |
| peter king    |
| henry clark   |
| carl white    |
| joe thomas    |
| jack smith    |
| roy king      |
+---------------+
25 rows in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT LCASE(FIRSTNAME) FROM STUDENTS;
+------------------+
| LCASE(FIRSTNAME) |
+------------------+
| john             |
| mary             |
| james            |
| mike             |
| linda            |
| john             |
| james            |
| john             |
| daniel           |
| paul             |
| mark             |
| steven           |
| brian            |
| kevin            |
| jason            |
| jose             |
| frank            |
| eric             |
| jerry            |
| peter            |
| henry            |
| carl             |
| joe              |
| jack             |
| roy              |
| adam             |
| bobby            |
| johnny           |
| jimmy            |
| emma             |
| sophia           |
| ava              |
| mia              |
| emily            |
| grace            |
| lillian          |
| lily             |
| layla            |
| zoe              |
| anna             |
| leah             |
| camila           |
| riley            |
| nora             |
| hailey           |
| ellie            |
| lucy             |
| stella           |
| bella            |
| mila             |
| maya             |
| faith            |
| eva              |
| julia            |
| ashley           |
| ruby             |
| alice            |
| jasmine          |
+------------------+
58 rows in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT MID(FIRSTNAME,1,3) FROM STUDENTS;
+--------------------+
| MID(FIRSTNAME,1,3) |
+--------------------+
| Joh                |
| Mar                |
| Jam                |
| Mik                |
| Lin                |
| Joh                |
| Jam                |
| Joh                |
| Dan                |
| Pau                |
| Mar                |
| Ste                |
| Bri                |
| Kev                |
| Jas                |
| Jos                |
| Fra                |
| Eri                |
| Jer                |
| Pet                |
| Hen                |
| Car                |
| Joe                |
| Jac                |
| Roy                |
| Ada                |
| Bob                |
| Joh                |
| Jim                |
| Emm                |
| Sop                |
| Ava                |
| Mia                |
| Emi                |
| Gra                |
| Lil                |
| Lil                |
| Lay                |
| Zoe                |
| Ann                |
| Lea                |
| Cam                |
| Ril                |
| Nor                |
| Hai                |
| Ell                |
| Luc                |
| Ste                |
| Bel                |
| Mil                |
| May                |
| Fai                |
| Eva                |
| Jul                |
| Ash                |
| Rub                |
| Ali                |
| Jas                |
+--------------------+
58 rows in set (0.00 sec)

mysql> SELECT MID(FIRSTNAME,2) FROM STUDENTS;
+------------------+
| MID(FIRSTNAME,2) |
+------------------+
| ohn              |
| ary              |
| ames             |
| ike              |
| inda             |
| ohn              |
| ames             |
| ohn              |
| aniel            |
| aul              |
| ark              |
| teven            |
| rian             |
| evin             |
| ason             |
| ose              |
| rank             |
| ric              |
| erry             |
| eter             |
| enry             |
| arl              |
| oe               |
| ack              |
| oy               |
| dam              |
| obby             |
| ohnny            |
| immy             |
| mma              |
| ophia            |
| va               |
| ia               |
| mily             |
| race             |
| illian           |
| ily              |
| ayla             |
| oe               |
| nna              |
| eah              |
| amila            |
| iley             |
| ora              |
| ailey            |
| llie             |
| ucy              |
| tella            |
| ella             |
| ila              |
| aya              |
| aith             |
| va               |
| ulia             |
| shley            |
| uby              |
| lice             |
| asmine           |
+------------------+
58 rows in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT FIRSTNAME,LENGTH(FIRSTNAME) AS 'String length' from Students;
+-----------+---------------+
| FIRSTNAME | String length |
+-----------+---------------+
| John      |             4 |
| Mary      |             4 |
| James     |             5 |
| Mike      |             4 |
| Linda     |             5 |
| John      |             4 |
| James     |             5 |
| John      |             4 |
| Daniel    |             6 |
| Paul      |             4 |
| Mark      |             4 |
| Steven    |             6 |
| Brian     |             5 |
| Kevin     |             5 |
| Jason     |             5 |
| Jose      |             4 |
| Frank     |             5 |
| Eric      |             4 |
| Jerry     |             5 |
| Peter     |             5 |
| Henry     |             5 |
| Carl      |             4 |
| Joe       |             3 |
| Jack      |             4 |
| Roy       |             3 |
| Adam      |             4 |
| Bobby     |             5 |
| Johnny    |             6 |
| Jimmy     |             5 |
| Emma      |             4 |
| Sophia    |             6 |
| Ava       |             3 |
| Mia       |             3 |
| Emily     |             5 |
| Grace     |             5 |
| Lillian   |             7 |
| Lily      |             4 |
| Layla     |             5 |
| Zoe       |             3 |
| Anna      |             4 |
| Leah      |             4 |
| Camila    |             6 |
| Riley     |             5 |
| Nora      |             4 |
| Hailey    |             6 |
| Ellie     |             5 |
| Lucy      |             4 |
| Stella    |             6 |
| Bella     |             5 |
| Mila      |             4 |
| Maya      |             4 |
| Faith     |             5 |
| Eva       |             3 |
| Julia     |             5 |
| Ashley    |             6 |
| Ruby      |             4 |
| Alice     |             5 |
| Jasmine   |             7 |
+-----------+---------------+
58 rows in set (0.00 sec)

mysql> SELECT (10.4353545);
+------------+
| 10.4353545 |
+------------+
| 10.4353545 |
+------------+
1 row in set (0.00 sec)

mysql> SELECT ROUND(10.4353545,2);
+---------------------+
| ROUND(10.4353545,2) |
+---------------------+
|               10.44 |
+---------------------+
1 row in set (0.00 sec)

mysql> SELECT ROUND(10.456789,5);
+--------------------+
| ROUND(10.456789,5) |
+--------------------+
|           10.45679 |
+--------------------+
1 row in set (0.00 sec)

mysql> SELECT FROMAT(10.456789,5);
ERROR 1305 (42000): FUNCTION school.FROMAT does not exist
mysql> SELECT FORMAT(10.456789,5);
+---------------------+
| FORMAT(10.456789,5) |
+---------------------+
| 10.45679            |
+---------------------+
1 row in set (0.00 sec)

mysql> SELECT FORMAT(10.456,2);
+------------------+
| FORMAT(10.456,2) |
+------------------+
| 10.46            |
+------------------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT SUBSTRING(FIRSTNAME,1,3) FROM STUDENTS;
+--------------------------+
| SUBSTRING(FIRSTNAME,1,3) |
+--------------------------+
| Joh                      |
| Mar                      |
| Jam                      |
| Mik                      |
| Lin                      |
| Joh                      |
| Jam                      |
| Joh                      |
| Dan                      |
| Pau                      |
| Mar                      |
| Ste                      |
| Bri                      |
| Kev                      |
| Jas                      |
| Jos                      |
| Fra                      |
| Eri                      |
| Jer                      |
| Pet                      |
| Hen                      |
| Car                      |
| Joe                      |
| Jac                      |
| Roy                      |
| Ada                      |
| Bob                      |
| Joh                      |
| Jim                      |
| Emm                      |
| Sop                      |
| Ava                      |
| Mia                      |
| Emi                      |
| Gra                      |
| Lil                      |
| Lil                      |
| Lay                      |
| Zoe                      |
| Ann                      |
| Lea                      |
| Cam                      |
| Ril                      |
| Nor                      |
| Hai                      |
| Ell                      |
| Luc                      |
| Ste                      |
| Bel                      |
| Mil                      |
| May                      |
| Fai                      |
| Eva                      |
| Jul                      |
| Ash                      |
| Rub                      |
| Ali                      |
| Jas                      |
+--------------------------+
58 rows in set (0.00 sec)

mysql> SELECT SUBSTRING(FIRSTNAME FROM 1 FOR 3) FROM STUDENTS;
+-----------------------------------+
| SUBSTRING(FIRSTNAME FROM 1 FOR 3) |
+-----------------------------------+
| Joh                               |
| Mar                               |
| Jam                               |
| Mik                               |
| Lin                               |
| Joh                               |
| Jam                               |
| Joh                               |
| Dan                               |
| Pau                               |
| Mar                               |
| Ste                               |
| Bri                               |
| Kev                               |
| Jas                               |
| Jos                               |
| Fra                               |
| Eri                               |
| Jer                               |
| Pet                               |
| Hen                               |
| Car                               |
| Joe                               |
| Jac                               |
| Roy                               |
| Ada                               |
| Bob                               |
| Joh                               |
| Jim                               |
| Emm                               |
| Sop                               |
| Ava                               |
| Mia                               |
| Emi                               |
| Gra                               |
| Lil                               |
| Lil                               |
| Lay                               |
| Zoe                               |
| Ann                               |
| Lea                               |
| Cam                               |
| Ril                               |
| Nor                               |
| Hai                               |
| Ell                               |
| Luc                               |
| Ste                               |
| Bel                               |
| Mil                               |
| May                               |
| Fai                               |
| Eva                               |
| Jul                               |
| Ash                               |
| Rub                               |
| Ali                               |
| Jas                               |
+-----------------------------------+
58 rows in set (0.00 sec)

mysql> SELECT SUBSTRING(FIRSTNAME FROM 2 FOR 2) FROM STUDENTS;
+-----------------------------------+
| SUBSTRING(FIRSTNAME FROM 2 FOR 2) |
+-----------------------------------+
| oh                                |
| ar                                |
| am                                |
| ik                                |
| in                                |
| oh                                |
| am                                |
| oh                                |
| an                                |
| au                                |
| ar                                |
| te                                |
| ri                                |
| ev                                |
| as                                |
| os                                |
| ra                                |
| ri                                |
| er                                |
| et                                |
| en                                |
| ar                                |
| oe                                |
| ac                                |
| oy                                |
| da                                |
| ob                                |
| oh                                |
| im                                |
| mm                                |
| op                                |
| va                                |
| ia                                |
| mi                                |
| ra                                |
| il                                |
| il                                |
| ay                                |
| oe                                |
| nn                                |
| ea                                |
| am                                |
| il                                |
| or                                |
| ai                                |
| ll                                |
| uc                                |
| te                                |
| el                                |
| il                                |
| ay                                |
| ai                                |
| va                                |
| ul                                |
| sh                                |
| ub                                |
| li                                |
| as                                |
+-----------------------------------+
58 rows in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT COALESCE(1,2,3)
    -> ;
+-----------------+
| COALESCE(1,2,3) |
+-----------------+
|               1 |
+-----------------+
1 row in set (0.00 sec)

mysql> SELECT COALESCE(NULL,2,3);
+--------------------+
| COALESCE(NULL,2,3) |
+--------------------+
|                  2 |
+--------------------+
1 row in set (0.00 sec)

mysql> SELECT COALESCE(NULL,NULL,3);
+-----------------------+
| COALESCE(NULL,NULL,3) |
+-----------------------+
|                     3 |
+-----------------------+
1 row in set (0.00 sec)

mysql> SELECT COALESCE(NULL,NULL,NULL);
+--------------------------+
| COALESCE(NULL,NULL,NULL) |
+--------------------------+
|                     NULL |
+--------------------------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql>
mysql> ^C
mysql> SELECT * FROM STUDENTSL
    -> ^C
mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | firstname | lastname | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> SELECT FIRSTNAME , CHAR_LENGTH(FIRSTNAME) AS 'Character length' from students;
+-----------+------------------+
| FIRSTNAME | Character length |
+-----------+------------------+
| John      |                4 |
| Mary      |                4 |
| James     |                5 |
| Mike      |                4 |
| Linda     |                5 |
| John      |                4 |
| James     |                5 |
| John      |                4 |
| Daniel    |                6 |
| Paul      |                4 |
| Mark      |                4 |
| Steven    |                6 |
| Brian     |                5 |
| Kevin     |                5 |
| Jason     |                5 |
| Jose      |                4 |
| Frank     |                5 |
| Eric      |                4 |
| Jerry     |                5 |
| Peter     |                5 |
| Henry     |                5 |
| Carl      |                4 |
| Joe       |                3 |
| Jack      |                4 |
| Roy       |                3 |
| Adam      |                4 |
| Bobby     |                5 |
| Johnny    |                6 |
| Jimmy     |                5 |
| Emma      |                4 |
| Sophia    |                6 |
| Ava       |                3 |
| Mia       |                3 |
| Emily     |                5 |
| Grace     |                5 |
| Lillian   |                7 |
| Lily      |                4 |
| Layla     |                5 |
| Zoe       |                3 |
| Anna      |                4 |
| Leah      |                4 |
| Camila    |                6 |
| Riley     |                5 |
| Nora      |                4 |
| Hailey    |                6 |
| Ellie     |                5 |
| Lucy      |                4 |
| Stella    |                6 |
| Bella     |                5 |
| Mila      |                4 |
| Maya      |                4 |
| Faith     |                5 |
| Eva       |                3 |
| Julia     |                5 |
| Ashley    |                6 |
| Ruby      |                4 |
| Alice     |                5 |
| Jasmine   |                7 |
+-----------+------------------+
58 rows in set (0.00 sec)

mysql> SELECT studentid , CHAR_LENGTH(studentid) AS 'Character length' from students;
+-----------+------------------+
| studentid | Character length |
+-----------+------------------+
|         1 |                1 |
|         2 |                1 |
|         3 |                1 |
|         4 |                1 |
|         5 |                1 |
|         6 |                1 |
|         7 |                1 |
|         8 |                1 |
|         9 |                1 |
|        10 |                2 |
|        11 |                2 |
|        12 |                2 |
|        13 |                2 |
|        14 |                2 |
|        15 |                2 |
|        16 |                2 |
|        17 |                2 |
|        18 |                2 |
|        19 |                2 |
|        20 |                2 |
|        21 |                2 |
|        22 |                2 |
|        23 |                2 |
|        24 |                2 |
|        25 |                2 |
|        26 |                2 |
|        27 |                2 |
|        28 |                2 |
|        29 |                2 |
|        30 |                2 |
|        31 |                2 |
|        32 |                2 |
|        33 |                2 |
|        34 |                2 |
|        35 |                2 |
|        36 |                2 |
|        37 |                2 |
|        38 |                2 |
|        39 |                2 |
|        40 |                2 |
|        41 |                2 |
|        42 |                2 |
|        43 |                2 |
|        44 |                2 |
|        45 |                2 |
|        46 |                2 |
|        47 |                2 |
|        48 |                2 |
|        49 |                2 |
|        50 |                2 |
|        51 |                2 |
|        52 |                2 |
|        53 |                2 |
|        54 |                2 |
|        55 |                2 |
|        56 |                2 |
|        57 |                2 |
|        58 |                2 |
+-----------+------------------+
58 rows in set (0.00 sec)

mysql> SELECT (10.4353);
+---------+
| 10.4353 |
+---------+
| 10.4353 |
+---------+
1 row in set (0.00 sec)

mysql> SELECT CAST(10.4353 AS SIGNED);
+-------------------------+
| CAST(10.4353 AS SIGNED) |
+-------------------------+
|                      10 |
+-------------------------+
1 row in set (0.00 sec)

mysql> SELECT CAST(10.8353 AS DECIMAL);
+--------------------------+
| CAST(10.8353 AS DECIMAL) |
+--------------------------+
|                       11 |
+--------------------------+
1 row in set (0.00 sec)

mysql> SELECT CAST(10.8353 AS DECIMAL(4,2));
+-------------------------------+
| CAST(10.8353 AS DECIMAL(4,2)) |
+-------------------------------+
|                         10.84 |
+-------------------------------+
1 row in set (0.00 sec)

mysql> SELECT CAST(10.8353 AS CHAR(4));
+--------------------------+
| CAST(10.8353 AS CHAR(4)) |
+--------------------------+
| 10.8                     |
+--------------------------+
1 row in set, 1 warning (0.00 sec)

mysql> SELECT NULLIFY(10,20);
ERROR 1305 (42000): FUNCTION school.NULLIFY does not exist
mysql> SELECT NULLIF(10,20);
+---------------+
| NULLIF(10,20) |
+---------------+
|            10 |
+---------------+
1 row in set (0.00 sec)

mysql> SELECT NULLIF(20,10);
+---------------+
| NULLIF(20,10) |
+---------------+
|            20 |
+---------------+
1 row in set (0.00 sec)

mysql> SELECT NULLIF(NULL,10);
+-----------------+
| NULLIF(NULL,10) |
+-----------------+
|            NULL |
+-----------------+
1 row in set (0.00 sec)

mysql> SELECT NULLIF(10,10);
+---------------+
| NULLIF(10,10) |
+---------------+
|          NULL |
+---------------+
1 row in set (0.00 sec)

mysql> SELECT NULLIF('ABC','XYZ');
+---------------------+
| NULLIF('ABC','XYZ') |
+---------------------+
| ABC                 |
+---------------------+
1 row in set (0.00 sec)

mysql> SELECT NULLIF('XYZ','XYZ');
+---------------------+
| NULLIF('XYZ','XYZ') |
+---------------------+
| NULL                |
+---------------------+
1 row in set (0.00 sec)

mysql> USE JOINS;
Database changed
mysql> SELECT TABLE1.COLUMN1,TABLE2.COLUMN2 FROM TABLE1 LEFT OUTER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2;
+---------+---------+
| COLUMN1 | COLUMN2 |
+---------+---------+
|      11 |    NULL |
|      13 |    NULL |
|      14 |    NULL |
|      12 |      12 |
|      15 |      15 |
+---------+---------+
5 rows in set (0.00 sec)

mysql> SELECT TABLE1.COLUMN1,TABLE2.COLUMN2, NULLIF(TABLE1.COLUMN1,TABLE2.COLUMN2) FROM TABLE1 LEFT OUTER JOIN TABLE2 ON TABLE1.COLUMN1=TABLE2.COLUMN2;
+---------+---------+---------------------------------------+
| COLUMN1 | COLUMN2 | NULLIF(TABLE1.COLUMN1,TABLE2.COLUMN2) |
+---------+---------+---------------------------------------+
|      11 |    NULL |                                    11 |
|      13 |    NULL |                                    13 |
|      14 |    NULL |                                    14 |
|      12 |      12 |                                  NULL |
|      15 |      15 |                                  NULL |
+---------+---------+---------------------------------------+
5 rows in set (0.00 sec)


mysql> SELECT CASE(3)
    -> WHEN 1 THEN 'ONE'
    -> WHEN 2 THEN 'TWO'
    -> WHEN 3 THEN 'THREE'
    -> WHEN 4 THEN 'FOUR'
    -> WHEN 5 THEN 'FIVE'
    -> ELSE 'NO MATCH'
    -> END;
+---------------------------------------------------------------------------------------------------------------------------+
| CASE(3)
WHEN 1 THEN 'ONE'
WHEN 2 THEN 'TWO'
WHEN 3 THEN 'THREE'
WHEN 4 THEN 'FOUR'
WHEN 5 THEN 'FIVE'
ELSE 'NO MATCH'
END |
+---------------------------------------------------------------------------------------------------------------------------+
| THREE                                                                                                                     |
+---------------------------------------------------------------------------------------------------------------------------+
1 row in set (0.00 sec)

mysql> USE SCHOOL;
Database changed
mysql> SELECT FIRSTNAME,AGE,CASE
    -> WHEN(AGE=5)THEN 'Five'
    -> WHEN(AGE=6)THEN 'SIX'
    -> WHEN(AGE=7)THEN 'SEVEN'
    -> ELSE NULL
    -> END
    -> AS 'Age as Text'
    -> FROM students;
+-----------+------+-------------+
| FIRSTNAME | AGE  | Age as Text |
+-----------+------+-------------+
| John      |    5 | Five        |
| Mary      |    7 | SEVEN       |
| James     |    5 | Five        |
| Mike      |    6 | SIX         |
| Linda     |    7 | SEVEN       |
| John      |    7 | SEVEN       |
| James     |    6 | SIX         |
| John      |    6 | SIX         |
| Daniel    |    7 | SEVEN       |
| Paul      |    5 | Five        |
| Mark      |    6 | SIX         |
| Steven    |    7 | SEVEN       |
| Brian     |    5 | Five        |
| Kevin     |    6 | SIX         |
| Jason     |    5 | Five        |
| Jose      |    6 | SIX         |
| Frank     |    7 | SEVEN       |
| Eric      |    7 | SEVEN       |
| Jerry     |    5 | Five        |
| Peter     |    6 | SIX         |
| Henry     |    7 | SEVEN       |
| Carl      |    5 | Five        |
| Joe       |    7 | SEVEN       |
| Jack      |    6 | SIX         |
| Roy       |    5 | Five        |
| Adam      |    6 | SIX         |
| Bobby     |    7 | SEVEN       |
| Johnny    |    6 | SIX         |
| Jimmy     |    5 | Five        |
| Emma      |    5 | Five        |
| Sophia    |    6 | SIX         |
| Ava       |    7 | SEVEN       |
| Mia       |    6 | SIX         |
| Emily     |    5 | Five        |
| Grace     |    5 | Five        |
| Lillian   |    7 | SEVEN       |
| Lily      |    6 | SIX         |
| Layla     |    5 | Five        |
| Zoe       |    7 | SEVEN       |
| Anna      |    5 | Five        |
| Leah      |    6 | SIX         |
| Camila    |    5 | Five        |
| Riley     |    6 | SIX         |
| Nora      |    7 | SEVEN       |
| Hailey    |    7 | SEVEN       |
| Ellie     |    5 | Five        |
| Lucy      |    6 | SIX         |
| Stella    |    5 | Five        |
| Bella     |    7 | SEVEN       |
| Mila      |    6 | SIX         |
| Maya      |    5 | Five        |
| Faith     |    5 | Five        |
| Eva       |    7 | SEVEN       |
| Julia     |    6 | SIX         |
| Ashley    |    5 | Five        |
| Ruby      |    7 | SEVEN       |
| Alice     |    6 | SIX         |
| Jasmine   |    7 | SEVEN       |
+-----------+------+-------------+
58 rows in set (0.00 sec)

///DATATYPES IN SQL
THREE TYPES OF MAINLY DATA TYPES. NUMERICA DTAT TYPES , CHARACTER DATA TYPES AND TEMPORAL DATA TYPES;
NUMERICAL DATA TYPES ARE INTEGERS NUMBERS, FIXED POINT NUMBERS AND FLOATING POINT NUMBERS
CHARACTER DATA TYPES CAN STORE ALPHABETS,SYMBOLS AND ALSO NUMBERS;
TEMPORAL DATA TYPES STORE DATE , TIME , DATA TIME TOGETHER;
///INTEGER NUMBER DATA TYPES; INT , INTEGER , SMALL, TINYINT,MEDIUMINT, AND BIGINT;

FIXED POINT NUMBERS
FIXED POINT NUMBERS OR EXACT VALUES ARE LIKE NUMBERS LIKE 0.01,10.25,123.456 AND SO ON
THE FIXED POINT NUMBERS NUMBERS ARE THE VALUE SLIKE CURRENCY , SMALL CALCULATION AND MEASURMENT DATA WITH DECIMAL POINTS;
THE FIXED POINT NUMBERS CAN BE POSITIVE,NEGATIVE AND ZERO VALUES WITH DECIMALS POINTS

THE DECIMAL AND NUMERIC ARE THE DATA TYPES WHICH STORE FIXED POINT NUMBERS OR EXACT VALUES;
 DECIMAL(5,2) OR NUMERIC(5,2)
 Precision: 5(the total number of digits)
 Scale(option):2(The number of digits to the right to decimal points)if not defined,default is 0;
 
THE FLOAT REAL AND DOUBLE PRECISION 
FLOAT(M,D) OR REAL(M,D) OR DOUBLE PRECISION(M,D)
M IS TOTAL NUMBER DIGITS OF WHICH D DIGITS MAY BE THE AFTER THE DECIMAL POINTS
FLOAT(7,4) CAN STORE THE VALUE UP TO 999.999.VALUE 123.000089 WILL BE STORED AS 123.0001

FOR MAXIMUM PROBABILITY THE FLOATING POINT NUMBER DATA TYPES SHOULD BE DEFINED AS FLOAT OR DOUBLE
PRECISION WITH NO DEFINITION OF PRECISION

THE CHAR OR CHRACTER DATA TYPES STORES FIXED WIDTH CHARACTER COLUMNS
IT IS REQUIRED TO ENTER EOLUMN WIDTH. EXAMPLE CHAR(5),CHAR(50)

IF INSERTED CHARACTER LENGTH IS LESS THAN THE DEFINED COLUMN WIDTH THW VALUE IS POSITIONED TO THE LEFT
AND PADDED WITH SPACES ON THE RIGHT UNTIL CHARACTER LENGTH IS EQUAL TO THE DEFINED COLUMN WIDTH

IN INSTANCE CHAR(20) STRING 'JOHN' WILL BE APPENDED WITH 16 SPACES

THE DATA STORAGE SPACE BYTES ARE EXACTLY SIMILAR TO THE CHARACTER LENGTH DEFINED IN DATA TYPES
EXAMPLE: IN CHAR(20) THE DATA VALUE 'JOHN' WILL TAKE 20 BYTES OF STORAGE SPACE

THE VARCHAR OR VARYING CHARACTER STORE DYNAMIC WIDTH CHARACTER COLUMNS

IN VARCHAR THE DEFINED WIDTH IS , THE MAXIMUM WIDTH OF THE VALUE ALLOWED IN THE DATA COLUMN
EXAMPLE : IN VARCHAR(30) AND VARCHAR(250) THE MAXIMUM WIDTH OF THE DATA VALUE ALLOWED IN THE DATA COLUMN WILL BE 30 AND 250 RESPECTIVLEY;

THE INSERTED DATA CHRACTER LENGTH WILL BE EXACTLY SIMILAR TO THE DATA CHARACTER LENGTH ITSELF
EXAMPLE IN VARCHAR(20), DATA COLUMNS WILL STORE ONLY 4 CHARACTER FOR THE VALUE 'John'

IN VARCHAR DATA TYPE, THE DATA TYPE, THE DATA STORAGE SPACES ARE THE DATA STRING LENGTH PLUS ONE BYTE.
EXAMPLE: FOR INSERTING 'JOHN', THE DATA STRING LENGTH 4+1BYTE =TOTAL 5 BYTES STORE SPACE IS REQUIRED.

THE NCHAR AND NVARCHAR MEANS NATIONAL CHARACTER AND NATIONAL VARIABLE CHARACTER
THE NCHAR AND NVARCHAR STORE FIXED WIDTH CHARACTER COLUMNS BUT IT US LARGER CHARACTER SET 
THE NCHAR AND NVARCHAR STORE FIXED CHARACTER COLUMNS BUT USE LARGER LARGER CHARACTER SET
THE NCHAR AND NVARCHAR USE UNICODE CHARACTER USE UNICODE CHARACTERS SETS LIKE UTF-8 FOR INTERNATIONALIZATION. THE UNICODE CHARACTER SETS ARE REQUIRED TO STORE FOREIGN LANGUAGES

IN CHAR AND VARCHAR,1 BYTE STORAGE IS REQUIRED TO STORE EACH CHARACTER WHILE IN NCHAR AND NVARCHAR
IT REQUIRES 2 BYTES STORAGE SPACE FOR EACH CHARACTER

THE CLOB AND BLOB MEANS CHARACTER LARGE OBJECT AND BINARY LARGE OBJECT RESPECTIVLEY

THE CLOB AND BLOB DATA TYPE IS USED TO STORE VERY LARGE DATA THAT CAN NOT BE STORED IN CHAR OR VARCHAR 

THE CLOB IS USED TO STORE CHARACTER DATA WHILE THE BLOB IS USED TO STORE BINARY DATA LIKE IMAGES, AUDIO 
AND VIDEO

IN MYSQL TEXT DATA TYPE IS SIMILAR TO CLOB
EACH DATABASES SYSTEM HAS ITS OWN RULES FOR STORING AND DISPLAYING DATE VALUES.THE DATE FORMATS DIFFERS FROM DATABASE SYSTEM TO ANOTHER.

THE MOST POPULAR DATE FORMAT IS YYYY-MM-DD WHERE 4Y MEANS YEAR ,2M MEANS MONTH AND 2D FOR THE DAY

MY SQL RETRIEVES AND DISPLAY TIME VALUES IN 'HH:MM:SS'.THE TIME VALUES FORMATS MAY DIFFER FROM ONE DATABASE SYSTEM TO ANOTHER.

THE TIMESTAMP DATA TYPE CAN STORE DATE AS WELL AS TIME COMPONENTS

////DATA DEFINITION LANGUAGES:
//DATABASES AND MY DATABASE
mysql> USE SCHOOL;
Database changed
mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| company            |
| information_schema |
| joins              |
| mysql              |
| onlineshop         |
| performance_schema |
| school             |
| sys                |
+--------------------+
8 rows in set (0.04 sec)

mysql> CREATE DATABASE MY_DATABASE;
Query OK, 1 row affected (0.01 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| company            |
| information_schema |
| joins              |
| my_database        |
| mysql              |
| onlineshop         |
| performance_schema |
| school             |
| sys                |
+--------------------+
9 rows in set (0.00 sec)

mysql> CREATE DATABASE 1234;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '1234' at line 1
mysql> CREATE DATABASE 1234D;
Query OK, 1 row affected (0.01 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| 1234d              |
| company            |
| information_schema |
| joins              |
| my_database        |
| mysql              |
| onlineshop         |
| performance_schema |
| school             |
| sys                |
+--------------------+
10 rows in set (0.00 sec)


///LEARN HOW TO CREATE THE DATABASE TABLE USING RIGHT METHOD
mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| students2        |
| subjects         |
| teachers         |
+------------------+
4 rows in set (0.01 sec)

mysql> CREATE TABLE STUDENTS3 (
    -> STUDENTID SMALLINT(5),
    -> FIRSTNAME VARCHAR(20),
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ')' at line 4
mysql> CREATE TABLE STUDENTS3 (
    -> STUDENTID SMALLINT(5),
    -> FIRSTNAME VARCHAR(20));
Query OK, 0 rows affected, 1 warning (0.06 sec)

mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| students2        |
| students3        |
| subjects         |
| teachers         |
+------------------+
5 rows in set (0.00 sec)

mysql> DESCRIBE STUDENTS3;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| STUDENTID | smallint    | YES  |     | NULL    |       |
| FIRSTNAME | varchar(20) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> DESC STUDENTS3;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| STUDENTID | smallint    | YES  |     | NULL    |       |
| FIRSTNAME | varchar(20) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
2 rows in set (0.00 sec)

mysql> EXPLAIN STUDENTS3;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| STUDENTID | smallint    | YES  |     | NULL    |       |
| FIRSTNAME | varchar(20) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
2 rows in set (0.00 sec)

/// MODIFY OR UPDATE THE DATABASE TABLE DETAILS;

mysql> USE SCHOOL;
Database changed
mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| students2        |
| students3        |
| subjects         |
| teachers         |
+------------------+
5 rows in set (0.00 sec)

mysql> ALTER TABLE STUDENTS3 RENAME STUDENTS4;
Query OK, 0 rows affected (0.04 sec)

mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| students2        |
| students4        |
| subjects         |
| teachers         |
+------------------+
5 rows in set (0.00 sec)

mysql> DESC STUDENTS4;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| STUDENTID | smallint    | YES  |     | NULL    |       |
| FIRSTNAME | varchar(20) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> ALTER TABLE STUDENTS4 ADD LASTNAME VARCHAR(10);
Query OK, 0 rows affected (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> DESC STUDENTS4;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| STUDENTID | smallint    | YES  |     | NULL    |       |
| FIRSTNAME | varchar(20) | YES  |     | NULL    |       |
| LASTNAME  | varchar(10) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> ALTER TABLE STUDENTS4 MODIFY COLUMN LASTNAME VARCHAR(20);
Query OK, 0 rows affected (0.02 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> DESC STUDENTS4;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| STUDENTID | smallint    | YES  |     | NULL    |       |
| FIRSTNAME | varchar(20) | YES  |     | NULL    |       |
| LASTNAME  | varchar(20) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> ALTER TABLE STUDENTS4 DROP COLUMN LASTNAME;
Query OK, 0 rows affected (0.07 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> DESC STUDENTS4;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| STUDENTID | smallint    | YES  |     | NULL    |       |
| FIRSTNAME | varchar(20) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

// REMOVE OR DELETE TABLE 
mysql> USE SCHOOL;
Database changed
mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| students2        |
| students4        |
| subjects         |
| teachers         |
+------------------+
5 rows in set (0.00 sec)

mysql> DROP TABLE STUDENTS4;
Query OK, 0 rows affected (0.03 sec)

mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| students2        |
| subjects         |
| teachers         |
+------------------+
4 rows in set (0.00 sec)

////SQL CONSTRAINTS
///WHILE INSERTING UPDATING OR DELETING THE DATA ROWS , IF THE CONSTRAINTS RULES ARE NOT FOLLOWED , THE SYSTEM WILL 
DISPLAY AN ERROR MESSAGE AND ACTION WILL BE TERMINATED 

///THE SQL CONSTRAINTS ARE DEFINED WHILE CREATING THE NEW TABLE.WE CAN  ALSE ALTER THE TABLE AND ADD NEW SQL CONSTRAINTS
///THE STANDARD SQL SUPPORTS SIX SQL CONSTRAINTS :
NOT NULL
mysql> USE SCHOOL;
Database changed
mysql> DESC STUDENTS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| studentid | int         | NO   | PRI | NULL    | auto_increment |
| firstname | varchar(40) | NO   |     | NULL    |                |
| lastname  | varchar(40) | NO   |     | NULL    |                |
| class     | varchar(20) | YES  |     | NULL    |                |
| age       | int         | YES  |     | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> ALTER TABLE STUDENTS MODIFY COLUMN FIRSTNAME VARCHAR(40) NULL,MODIFY COLUMN LASTNAME VARCHARE(40) NULL;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'VARCHARE(40) NULL' at line 1
mysql> ALTER TABLE STUDENTS MODIFY COLUMN FIRSTNAME VARCHAR(40) NULL,MODIFY COLUMN LASTNAME VARCHAR(40) NULL;
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> DESC STUDENTS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| studentid | int         | NO   | PRI | NULL    | auto_increment |
| FIRSTNAME | varchar(40) | YES  |     | NULL    |                |
| LASTNAME  | varchar(40) | YES  |     | NULL    |                |
| class     | varchar(20) | YES  |     | NULL    |                |
| age       | int         | YES  |     | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> INSERT INTO STUDENTS (FIRSTNAME,LASTNAME,CLASS,AGE) VALUES(NULL,NULL,NULL,NULL);
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        59 | NULL      | NULL     | NULL   | NULL |
+-----------+-----------+----------+--------+------+
59 rows in set (0.00 sec)

mysql> DELETE FROM STUDENTS WHERE FIRSTNAME=NULL;
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        59 | NULL      | NULL     | NULL   | NULL |
+-----------+-----------+----------+--------+------+
59 rows in set (0.00 sec)

mysql> DELETE FROM STUDENTS WHERE FIRSTNAME IS NULL;
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> ALTER TABLE STUDENTS MODIFY COLUMN FIRSTNAME VARCHAR(40) NOT NULL,MODIFY COLUMN LASTNAME VARCHAR(40) NOT NULL;
Query OK, 0 rows affected (0.08 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> DESC STUDENTS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| studentid | int         | NO   | PRI | NULL    | auto_increment |
| FIRSTNAME | varchar(40) | NO   |     | NULL    |                |
| LASTNAME  | varchar(40) | NO   |     | NULL    |                |
| class     | varchar(20) | YES  |     | NULL    |                |
| age       | int         | YES  |     | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> INSERT INTO STUDENTS (FIRSTNAME,LASTNAME,CLASS,AGE) VALUES(NULL,NULL,NULL,NULL);
ERROR 1048 (23000): Column 'FIRSTNAME' cannot be null

UNIQUE (MUTLIPLE COLUMNS IN A SINGLE TABLE CAN HAVE UNIQUE CONSTRAINTS):
mysql> USE SCHOOL;
Database changed
mysql> DESC SUBJECTS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| subjectid | int         | NO   | PRI | NULL    | auto_increment |
| title     | varchar(50) | NO   |     | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)

mysql> SELECT * FROM SUBJECTSL
    -> ^C
mysql> SELECT * FROM SUBJECTS;
+-----------+-------------+
| subjectid | title       |
+-----------+-------------+
|         1 | English     |
|         2 | Mathematics |
|         3 | Science     |
|         4 | Computer    |
|         5 | History     |
|         6 | Geography   |
+-----------+-------------+
6 rows in set (0.01 sec)

mysql> INSERT INTO SUBJECTS (TITLE) VALUES ('English');
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM SUBJECTS;
+-----------+-------------+
| subjectid | title       |
+-----------+-------------+
|         1 | English     |
|         2 | Mathematics |
|         3 | Science     |
|         4 | Computer    |
|         5 | History     |
|         6 | Geography   |
|         7 | English     |
+-----------+-------------+
7 rows in set (0.00 sec)

mysql> DELETE FROM SUBJECTS WHERE SUBJECTID=7;
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM SUBJECTS;
+-----------+-------------+
| subjectid | title       |
+-----------+-------------+
|         1 | English     |
|         2 | Mathematics |
|         3 | Science     |
|         4 | Computer    |
|         5 | History     |
|         6 | Geography   |
+-----------+-------------+
6 rows in set (0.00 sec)

mysql> ALTER TABLE SUBJECTS MODIFY COLUMN TITLE VARCHAR(50) UNIQUE;
Query OK, 0 rows affected (0.11 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> INSERT INTO SUBJECTS (TITLE) VALUES ('English');
ERROR 1062 (23000): Duplicate entry 'English' for key 'subjects.TITLE'
mysql> DESC SUBJECTS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| subjectid | int         | NO   | PRI | NULL    | auto_increment |
| TITLE     | varchar(50) | YES  | UNI | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)

PRIMARY KEY
 THE PRIMARY KEY IS SIMILAR IS UNIQUE CONSTRAINTS BUT UNLIKE UNIQUE CONSTRAINTS THERE CAN BE ONLY ONE PRIMARY KEY FOR ONE TABLE.
 THE PRIMARY KEY AUTOMATICALLY SETS UNIQUE CONSTRAINTS FOR TAHT TABLE COLUMN;
 THE PRIMARY KEY COLUMN CAN NOT CONTAIN NULL VALUES;
 THE PRIMARY CAN BE DEFINED WHILE CREATING A NEW DATABASE OR CAN BE ADDED USING ALTER TABLE STATEMENT
 
 
FOREIGN KEY
 A FOREIGN KEY IN A TABLE ALWAYS POINTS TO A PRIMARY KEY IN ANOTHER TABLE
 THE FOREIGN KEY CONSTRIANT ALSO RESTRICTS ADDING INVALID DATA TO THE FOREIGN KEY COLUMN BECAUSE THE FOREIGN
 KEY COLUMN VALUES MUST BE SIMILAR TO THE LINKED PRIMARY KEY VALUES;
 
 THE FOREIGN KEY CAN BE DEFINED WHILE CREATING A NEW DATABASES TABLE OR CAN BE ADDED BY USING ALTER TABLE STATEMENT
 mysql> USE SCHOOL
Database changed
mysql> SELECT * FROM SUBJECTS;
+-----------+-------------+
| subjectid | TITLE       |
+-----------+-------------+
|         1 | English     |
|         2 | Mathematics |
|         3 | Science     |
|         4 | Computer    |
|         5 | History     |
|         6 | Geography   |
+-----------+-------------+
6 rows in set (0.00 sec)

mysql> SELET * FROM TEACHERS;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'SELET * FROM TEACHERS' at line 1
mysql> SELECT * FROM TEACHERS;
+-----------+----------------+------------+
| teacherid | name           | phone      |
+-----------+----------------+------------+
|         1 | John Doe       | 1234567890 |
|         2 | Caroline Smith | 0987654321 |
|         3 | Jason King     | 1234512345 |
|         4 | Stella Brown   | 0987612345 |
|         5 | Eric Hall      | 0987609876 |
|         6 | Peter Brown    | 123435454  |
+-----------+----------------+------------+
6 rows in set (0.01 sec)

mysql> DESC SUBJECTSL
    -> ^C
mysql> DESC SUBJECTS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| subjectid | int         | NO   | PRI | NULL    | auto_increment |
| TITLE     | varchar(50) | YES  |     | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)

mysql> ALTER TABLE TEACHERS ADD COLUMN SUBJECTSID INT(11) NOT NULL DEFAULT 1;
Query OK, 0 rows affected, 1 warning (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 1

mysql> DESC TEACHERS;;
+------------+-------------+------+-----+---------+----------------+
| Field      | Type        | Null | Key | Default | Extra          |
+------------+-------------+------+-----+---------+----------------+
| teacherid  | int         | NO   | PRI | NULL    | auto_increment |
| name       | varchar(80) | NO   |     | NULL    |                |
| phone      | varchar(10) | YES  |     | NULL    |                |
| SUBJECTSID | int         | NO   |     | 1       |                |
+------------+-------------+------+-----+---------+----------------+
4 rows in set (0.01 sec)

ERROR:
No query specified

mysql> ALTER TABLE TEACHERS DROP COLUMN SUBJECTSID;
Query OK, 0 rows affected (0.10 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> DESC TEACHERS;;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| teacherid | int         | NO   | PRI | NULL    | auto_increment |
| name      | varchar(80) | NO   |     | NULL    |                |
| phone     | varchar(10) | YES  |     | NULL    |                |
+-----------+-------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)

ERROR:
No query specified

mysql> ALTER TABLE TEACHERS ADD COLUMN subjectid INT(11) NOT NULL DEFAULT 1;
Query OK, 0 rows affected, 1 warning (0.03 sec)
Records: 0  Duplicates: 0  Warnings: 1

mysql> DESC TEACHERS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| teacherid | int         | NO   | PRI | NULL    | auto_increment |
| name      | varchar(80) | NO   |     | NULL    |                |
| phone     | varchar(10) | YES  |     | NULL    |                |
| subjectid | int         | NO   |     | 1       |                |
+-----------+-------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)

mysql> ALTER TABLE TEACHERS ADD CONSTRAINT fk_subjectid FOREIGN KEY(subjectid) REFERENCES SUBJECTS(subjectid);
Query OK, 6 rows affected (0.12 sec)
Records: 6  Duplicates: 0  Warnings: 0

mysql> DESC TEACHERS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| teacherid | int         | NO   | PRI | NULL    | auto_increment |
| name      | varchar(80) | NO   |     | NULL    |                |
| phone     | varchar(10) | YES  |     | NULL    |                |
| subjectid | int         | NO   | MUL | 1       |                |
+-----------+-------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)

mysql> select * from subjects;
+-----------+-------------+
| subjectid | TITLE       |
+-----------+-------------+
|         1 | English     |
|         2 | Mathematics |
|         3 | Science     |
|         4 | Computer    |
|         5 | History     |
|         6 | Geography   |
+-----------+-------------+
6 rows in set (0.00 sec)

mysql> select * from teachers;
+-----------+----------------+------------+-----------+
| teacherid | name           | phone      | subjectid |
+-----------+----------------+------------+-----------+
|         1 | John Doe       | 1234567890 |         1 |
|         2 | Caroline Smith | 0987654321 |         1 |
|         3 | Jason King     | 1234512345 |         1 |
|         4 | Stella Brown   | 0987612345 |         1 |
|         5 | Eric Hall      | 0987609876 |         1 |
|         6 | Peter Brown    | 123435454  |         1 |
+-----------+----------------+------------+-----------+
6 rows in set (0.00 sec)

mysql> update teachers set subjectid=99 where teacherid=1;
ERROR 1452 (23000): Cannot add or update a child row: a foreign key constraint fails (`school`.`teachers`, CONSTRAINT `fk_subjectid` FOREIGN KEY (`subjectid`) REFERENCES `subjects` (`subjectid`))
mysql> update teachers set subjectid=6 where teacherid=1;
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from teachers;
+-----------+----------------+------------+-----------+
| teacherid | name           | phone      | subjectid |
+-----------+----------------+------------+-----------+
|         1 | John Doe       | 1234567890 |         6 |
|         2 | Caroline Smith | 0987654321 |         1 |
|         3 | Jason King     | 1234512345 |         1 |
|         4 | Stella Brown   | 0987612345 |         1 |
|         5 | Eric Hall      | 0987609876 |         1 |
|         6 | Peter Brown    | 123435454  |         1 |
+-----------+----------------+------------+-----------+
6 rows in set (0.00 sec)

mysql> ALTER TABLE TEACHERS DROP FOREIGN KEY fk_subjectid;
Query OK, 0 rows affected (0.02 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> ALTER TABLE teachers DROP COLUMN SUBJECTID;
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> select * from teachers;
+-----------+----------------+------------+
| teacherid | name           | phone      |
+-----------+----------------+------------+
|         1 | John Doe       | 1234567890 |
|         2 | Caroline Smith | 0987654321 |
|         3 | Jason King     | 1234512345 |
|         4 | Stella Brown   | 0987612345 |
|         5 | Eric Hall      | 0987609876 |
|         6 | Peter Brown    | 123435454  |
+-----------+----------------+------------+
6 rows in set (0.00 sec)
 
CHECK
THE CHECK CONSTRAINT IS USED TO CONTROL THE VALUE RANGE THAT CAN BE STORED IN A TABLE COLUMN
A TABLE COLUMN WITH CHECK CONSTRINTS DEFINED WILL SAVE ONLY SPECIFIC VALUES IN THE COLUMN
THE CHECK CONSTRAINTS CAN BE APPLIED TO A SINGLE OR MULTIPLE TABLE COLUMNS;
THE CHECK CONSTRAINT CAN BE DEFINED WHILE CREATING A NEW TABLE OR USING ALTER TABLE STATEMENT FRO EXISTING TABLE; 



DEFAULT
THE DEFALULT CONSTRAINTS IS USED TO SET A DEFAULT VALUE FOR A DATA COLUMN 
IF THE VALUE FOR THE COLUMN IN DATA ROW IS NOT DEFINED,THE DEFAULT VALUE WILL BE ADDED TO A DATA ROW COLUMN

AUTO_INCREMENT /SEQUENCE
THE AUTO_INCREMENT ATTRIBUTE GENERATES AND SAVE A UNIQUE NUMBER EVERY TIME A NEW DATA ROW IS INSERTED INTO A TABLE;

FOR PRIMARY KEY WE ALWASYS REQUIRE A UNIQUE NUMBER TO BE STORED. INSTEAD OF CREATING A UNIQUE NUMBER MANUALLY,

mysql> USE SCHOOL;
Database changed
mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
+-----------+-----------+----------+--------+------+
58 rows in set (0.00 sec)

mysql> INSERT INTO STUDENTS(FIRSTNAME,LASTNAME,CLASS)VALUES ('John','Doe','First');
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        60 | John      | Doe      | First  | NULL |
+-----------+-----------+----------+--------+------+
59 rows in set (0.00 sec)

mysql> delete from students where studentid=60;
Query OK, 1 row affected (0.01 sec)

mysql> ALTER TABLE STUDENTS ALTER AGE SET DEFAULT 5;
Query OK, 0 rows affected (0.02 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> INSERT INTO STUDENTS(FIRSTNAME,LASTNAME,CLASS)VALUES ('John','Doe','First');
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
59 rows in set (0.00 sec)

AUTO_INCREMENT OR SEQUENCE ATTRIBUTE ARE USEFUL.
THE AUTO INCREMENT OR SEQUENCE ARE ONLY USED WITH NUMERIC DATA COLUMNS
IN MySQL BY DEFAULT AUTO_INCREMENT GENERATES BY NEW VALUE BY ADDING 1,FOR EACH NEW RECORD;

mysql> USE SCHOOL;
Database changed
mysql> DESC STUDENTS;
+-----------+-------------+------+-----+---------+----------------+
| Field     | Type        | Null | Key | Default | Extra          |
+-----------+-------------+------+-----+---------+----------------+
| studentid | int         | NO   | PRI | NULL    | auto_increment |
| FIRSTNAME | varchar(40) | NO   |     | NULL    |                |
| LASTNAME  | varchar(40) | NO   |     | NULL    |                |
| class     | varchar(20) | YES  |     | NULL    |                |
| age       | int         | YES  |     | 5       |                |
+-----------+-------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> INSERT INTO STUDENTS (FIRSTNAME,LASTNAME,CLASS,AGE) VALUES ('John','Doe','First',5);
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

////DATA CONTROL LANGUAGE (DCL)
USER NEEDS PERMISSION TO PERFORM DATABASE OPERATIONS;
PRIVELLEGES :ADD USER ,CREATE DATABASE , CREATE TABLES,PERFORM QUERIES
THE GRANT STATEMENT AND REVOKE STATEMENT

GRANT:GIVE PERMISSION
REVOKE:WITHDRAW PRIVELLEGES


///GRANT STATEMENT: TO PROVIDE LIMITED OR SELECTED NUMBER OF PRIVELLEGES
//GRANT STATEMENT
Microsoft Windows [Version 10.0.18362.836]
(c) 2019 Microsoft Corporation. All rights reserved.

C:\Users\ASUS>CD C:\Program Files\MySQL\MySQL Server 8.0\bin

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u root -p
Enter password: ********************
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> CREATE USER maker IDENTIFIED BY 'maker1234';
Query OK, 0 rows affected (0.02 sec)

mysql> CREATE USER authorizer IDENTIFIED BY 'auth1234';
Query OK, 0 rows affected (0.01 sec)

mysql> quit
Bye

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u maker -p
Enter password: *********
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use school;
ERROR 1044 (42000): Access denied for user 'maker'@'%' to database 'school'
mysql> quit
Bye

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u authorizer -p
Enter password: ********
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 11
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use school;
ERROR 1044 (42000): Access denied for user 'authorizer'@'%' to database 'school'
mysql> quit
Bye

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u admin -p
Enter password: *******
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 12
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use school;
Database changed
mysql> use my sql;
ERROR 1049 (42000): Unknown database 'my'
mysql> use mysql;
Database changed
mysql> show tables;
+---------------------------+
| Tables_in_mysql           |
+---------------------------+
| columns_priv              |
| component                 |
| db                        |
| default_roles             |
| engine_cost               |
| func                      |
| general_log               |
| global_grants             |
| gtid_executed             |
| help_category             |
| help_keyword              |
| help_relation             |
| help_topic                |
| innodb_index_stats        |
| innodb_table_stats        |
| password_history          |
| plugin                    |
| procs_priv                |
| proxies_priv              |
| role_edges                |
| server_cost               |
| servers                   |
| slave_master_info         |
| slave_relay_log_info      |
| slave_worker_info         |
| slow_log                  |
| tables_priv               |
| time_zone                 |
| time_zone_leap_second     |
| time_zone_name            |
| time_zone_transition      |
| time_zone_transition_type |
| user                      |
+---------------------------+
33 rows in set (0.01 sec)

mysql> desc user;
+--------------------------+-----------------------------------+------+-----+-----------------------+-------+
| Field                    | Type                              | Null | Key | Default               | Extra |
+--------------------------+-----------------------------------+------+-----+-----------------------+-------+
| Host                     | char(255)                         | NO   | PRI |                       |       |
| User                     | char(32)                          | NO   | PRI |                       |       |
| Select_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Insert_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Update_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Delete_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Create_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Drop_priv                | enum('N','Y')                     | NO   |     | N                     |       |
| Reload_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Shutdown_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Process_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| File_priv                | enum('N','Y')                     | NO   |     | N                     |       |
| Grant_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| References_priv          | enum('N','Y')                     | NO   |     | N                     |       |
| Index_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Alter_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Show_db_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Super_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Create_tmp_table_priv    | enum('N','Y')                     | NO   |     | N                     |       |
| Lock_tables_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Execute_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Repl_slave_priv          | enum('N','Y')                     | NO   |     | N                     |       |
| Repl_client_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Create_view_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Show_view_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| Create_routine_priv      | enum('N','Y')                     | NO   |     | N                     |       |
| Alter_routine_priv       | enum('N','Y')                     | NO   |     | N                     |       |
| Create_user_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Event_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Trigger_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Create_tablespace_priv   | enum('N','Y')                     | NO   |     | N                     |       |
| ssl_type                 | enum('','ANY','X509','SPECIFIED') | NO   |     |                       |       |
| ssl_cipher               | blob                              | NO   |     | NULL                  |       |
| x509_issuer              | blob                              | NO   |     | NULL                  |       |
| x509_subject             | blob                              | NO   |     | NULL                  |       |
| max_questions            | int unsigned                      | NO   |     | 0                     |       |
| max_updates              | int unsigned                      | NO   |     | 0                     |       |
| max_connections          | int unsigned                      | NO   |     | 0                     |       |
| max_user_connections     | int unsigned                      | NO   |     | 0                     |       |
| plugin                   | char(64)                          | NO   |     | caching_sha2_password |       |
| authentication_string    | text                              | YES  |     | NULL                  |       |
| password_expired         | enum('N','Y')                     | NO   |     | N                     |       |
| password_last_changed    | timestamp                         | YES  |     | NULL                  |       |
| password_lifetime        | smallint unsigned                 | YES  |     | NULL                  |       |
| account_locked           | enum('N','Y')                     | NO   |     | N                     |       |
| Create_role_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Drop_role_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| Password_reuse_history   | smallint unsigned                 | YES  |     | NULL                  |       |
| Password_reuse_time      | smallint unsigned                 | YES  |     | NULL                  |       |
| Password_require_current | enum('N','Y')                     | YES  |     | NULL                  |       |
| User_attributes          | json                              | YES  |     | NULL                  |       |
+--------------------------+-----------------------------------+------+-----+-----------------------+-------+
51 rows in set (0.01 sec)

mysql> SELECT USER,SELECT_PRIV,UPDATE_PRIV,DELET_PRIV,CREATE_PRIV FROM USER;
ERROR 1054 (42S22): Unknown column 'DELET_PRIV' in 'field list'
mysql> SELECT USER,SELECT_PRIV,INSERT_PRIV,UPDATE_PRIV,DELETE_PRIV,CREATE_PRIV FROM USER;
+------------------+-------------+-------------+-------------+-------------+-------------+
| USER             | SELECT_PRIV | INSERT_PRIV | UPDATE_PRIV | DELETE_PRIV | CREATE_PRIV |
+------------------+-------------+-------------+-------------+-------------+-------------+
| admin            | Y           | Y           | Y           | Y           | Y           |
| authorizer       | N           | N           | N           | N           | N           |
| maker            | N           | N           | N           | N           | N           |
| mysql.infoschema | Y           | N           | N           | N           | N           |
| mysql.session    | N           | N           | N           | N           | N           |
| mysql.sys        | N           | N           | N           | N           | N           |
| root             | Y           | Y           | Y           | Y           | Y           |
+------------------+-------------+-------------+-------------+-------------+-------------+
7 rows in set (0.00 sec)

mysql> GRANT SELECT,CREATE ON SCHOOL.*TO MAKER;
ERROR 1410 (42000): You are not allowed to create a user with GRANT
mysql> quit
Bye

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u root -p
Enter password: ********************
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 13
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use mysql;
Database changed
mysql> show tables;
+---------------------------+
| Tables_in_mysql           |
+---------------------------+
| columns_priv              |
| component                 |
| db                        |
| default_roles             |
| engine_cost               |
| func                      |
| general_log               |
| global_grants             |
| gtid_executed             |
| help_category             |
| help_keyword              |
| help_relation             |
| help_topic                |
| innodb_index_stats        |
| innodb_table_stats        |
| password_history          |
| plugin                    |
| procs_priv                |
| proxies_priv              |
| role_edges                |
| server_cost               |
| servers                   |
| slave_master_info         |
| slave_relay_log_info      |
| slave_worker_info         |
| slow_log                  |
| tables_priv               |
| time_zone                 |
| time_zone_leap_second     |
| time_zone_name            |
| time_zone_transition      |
| time_zone_transition_type |
| user                      |
+---------------------------+
33 rows in set (0.01 sec)

mysql> desc user;
+--------------------------+-----------------------------------+------+-----+-----------------------+-------+
| Field                    | Type                              | Null | Key | Default               | Extra |
+--------------------------+-----------------------------------+------+-----+-----------------------+-------+
| Host                     | char(255)                         | NO   | PRI |                       |       |
| User                     | char(32)                          | NO   | PRI |                       |       |
| Select_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Insert_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Update_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Delete_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Create_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Drop_priv                | enum('N','Y')                     | NO   |     | N                     |       |
| Reload_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Shutdown_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Process_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| File_priv                | enum('N','Y')                     | NO   |     | N                     |       |
| Grant_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| References_priv          | enum('N','Y')                     | NO   |     | N                     |       |
| Index_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Alter_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Show_db_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Super_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Create_tmp_table_priv    | enum('N','Y')                     | NO   |     | N                     |       |
| Lock_tables_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Execute_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Repl_slave_priv          | enum('N','Y')                     | NO   |     | N                     |       |
| Repl_client_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Create_view_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Show_view_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| Create_routine_priv      | enum('N','Y')                     | NO   |     | N                     |       |
| Alter_routine_priv       | enum('N','Y')                     | NO   |     | N                     |       |
| Create_user_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Event_priv               | enum('N','Y')                     | NO   |     | N                     |       |
| Trigger_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Create_tablespace_priv   | enum('N','Y')                     | NO   |     | N                     |       |
| ssl_type                 | enum('','ANY','X509','SPECIFIED') | NO   |     |                       |       |
| ssl_cipher               | blob                              | NO   |     | NULL                  |       |
| x509_issuer              | blob                              | NO   |     | NULL                  |       |
| x509_subject             | blob                              | NO   |     | NULL                  |       |
| max_questions            | int unsigned                      | NO   |     | 0                     |       |
| max_updates              | int unsigned                      | NO   |     | 0                     |       |
| max_connections          | int unsigned                      | NO   |     | 0                     |       |
| max_user_connections     | int unsigned                      | NO   |     | 0                     |       |
| plugin                   | char(64)                          | NO   |     | caching_sha2_password |       |
| authentication_string    | text                              | YES  |     | NULL                  |       |
| password_expired         | enum('N','Y')                     | NO   |     | N                     |       |
| password_last_changed    | timestamp                         | YES  |     | NULL                  |       |
| password_lifetime        | smallint unsigned                 | YES  |     | NULL                  |       |
| account_locked           | enum('N','Y')                     | NO   |     | N                     |       |
| Create_role_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Drop_role_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| Password_reuse_history   | smallint unsigned                 | YES  |     | NULL                  |       |
| Password_reuse_time      | smallint unsigned                 | YES  |     | NULL                  |       |
| Password_require_current | enum('N','Y')                     | YES  |     | NULL                  |       |
| User_attributes          | json                              | YES  |     | NULL                  |       |
+--------------------------+-----------------------------------+------+-----+-----------------------+-------+
51 rows in set (0.00 sec)

mysql> SELECT USER,SELECT_PRIV,INSERT_PRIV,UPDATE_PRIV,DELETE_PRIV,CREATE_PRIV FROM USER;
+------------------+-------------+-------------+-------------+-------------+-------------+
| USER             | SELECT_PRIV | INSERT_PRIV | UPDATE_PRIV | DELETE_PRIV | CREATE_PRIV |
+------------------+-------------+-------------+-------------+-------------+-------------+
| admin            | Y           | Y           | Y           | Y           | Y           |
| authorizer       | N           | N           | N           | N           | N           |
| maker            | N           | N           | N           | N           | N           |
| mysql.infoschema | Y           | N           | N           | N           | N           |
| mysql.session    | N           | N           | N           | N           | N           |
| mysql.sys        | N           | N           | N           | N           | N           |
| root             | Y           | Y           | Y           | Y           | Y           |
+------------------+-------------+-------------+-------------+-------------+-------------+
7 rows in set (0.00 sec)

mysql>  GRANT SELECT,CREATE ON SCHOOL.*TO MAKER;
ERROR 1410 (42000): You are not allowed to create a user with GRANT
mysql>  GRANT SELECT,CREATE ON school.*TO Maker;
ERROR 1410 (42000): You are not allowed to create a user with GRANT
mysql>  GRANT SELECT ON school.*TO Maker;
ERROR 1410 (42000): You are not allowed to create a user with GRANT
mysql> GRANT ALL ON *.* TO AUTHORIZER;
ERROR 1410 (42000): You are not allowed to create a user with GRANT
mysql> SELECT USER,SELECT_PRIV,INSERT_PRIV,UPDATE_PRIV,DELETE_PRIV,CREATE_PRIV FROM USER;
+------------------+-------------+-------------+-------------+-------------+-------------+
| USER             | SELECT_PRIV | INSERT_PRIV | UPDATE_PRIV | DELETE_PRIV | CREATE_PRIV |
+------------------+-------------+-------------+-------------+-------------+-------------+
| admin            | Y           | Y           | Y           | Y           | Y           |
| authorizer       | N           | N           | N           | N           | N           |
| maker            | N           | N           | N           | N           | N           |
| mysql.infoschema | Y           | N           | N           | N           | N           |
| mysql.session    | N           | N           | N           | N           | N           |
| mysql.sys        | N           | N           | N           | N           | N           |
| root             | Y           | Y           | Y           | Y           | Y           |
+------------------+-------------+-------------+-------------+-------------+-------------+
7 rows in set (0.00 sec)

//REVOKE STATEMENT
WITHDRAW PERMISSIONS/PRIVELLEGES
REMOVE PRIVELLEGED TO LIMITED DATABASES OR ALL DATABASES
REMOVE SELECTED NUMBER OF PRIVELLEGES OR ALL PRIVELLEGES
mysql> REVOKE SELECT,CREATE ON SCHOOL.*FROM MAKER;
ERROR 1141 (42000): There is no such grant defined for user 'MAKER' on host '%'
mysql> REVOKE ALL ON *.* FROM AUTHORIZER;
ERROR 1269 (HY000): Can't revoke all privileges for one or more of the requested users
mysql>

///TRANSACTION CONTROL LANGUAGES
DDL STATEMENT : DIFFICULT TO VERIFY CHANGES OR ROLLBACK THE CHANGES
START TRANSACTION/BEGIN,COMMIT,ROLLBACK,SAVEPOINT AND SET autocommit

STARTTRANSACTION/BEGIN:START A NEW TRANSACTION
COMMIT: COMPLETES THE TRANSACTION.AFTER COMMIT WE CAN'T REVERT THE CHANGES;

ROLLBACK:MUST EXECUTE BEFORE COMMIT.REVERT BACK THE CHANGES .AFTER ROLBACK NO COMMIT

SAVEPOINT:ROLLBACK THE CHANGES TO SAVE POINTS;

SET AUTOCOMMIT: ENABLES/DISABLES DEFALULT AUTOCOMMIT MODE FOR CURRENT SESSION.

////COMMIT STATEMENTS:
THE COMMIT STATEMENT COMPLETES THE TRANSACTION:
THE TRANSACTION CAN BE (INSERT,UPDATE OR DELETE)

COMMIT;(ONLY AFTER TRANSACTION STATEMENTS)
Microsoft Windows [Version 10.0.18362.836]
(c) 2019 Microsoft Corporation. All rights reserved.

C:\Users\ASUS>CD C:\Program Files\MySQL\MySQL Server 8.0\bin

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u admin -p
Enter password: *******
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 21
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    6 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> start transaction;
Query OK, 0 rows affected (0.00 sec)

mysql> update students set age=5 where studentid=1;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> quit
Bye

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u admin -p
Enter password: *******
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 22
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    6 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> start transaction;
Query OK, 0 rows affected (0.00 sec)

mysql> update students set age=5 where studentid=1;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> commit;
Query OK, 0 rows affected (0.00 sec)

mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> quit;
Bye

C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql -u admin -p
Enter password: *******
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 23
Server version: 8.0.20 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use school;
Database changed
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

ROLLBACK:
THE ROLLBACK REVERT BACK THE CHANGES
MUST EXECUTE BEFORE COMMIT STATEMENT
AFTER ROLLBACK NO COMMIT
TRANSACTION STATEMENT; (INSERT/UPDATE/DELETE)
ROLLBACK ONLY AFTER TRANSACTION STATEMENT;
mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> BEGIN;
Query OK, 0 rows affected (0.00 sec)

mysql> UPDATE STUDENTS AGE=6 WHERE STUDENTID=1;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '=6 WHERE STUDENTID=1' at line 1
mysql> UPDATE STUDENTS SET AGE=6 WHERE STUDENTID=1;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    6 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> ROLLBACK;
Query OK, 0 rows affected (0.00 sec)

mysql> SELECT * FROM STUDENTS;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> CREATE DATABASE bank;
Query OK, 1 row affected (0.01 sec)

mysql> USE BANK;
Database changed
mysql> CREATE TABLE clients (cid INT NOT NULL AUTO_INCRMENT PRIMARY KEY,clientname VARCHAR(30) NOT NULL, balance FLOAT);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'AUTO_INCRMENT PRIMARY KEY,clientname VARCHAR(30) NOT NULL, balance FLOAT)' at line 1
mysql> CREATE TABLE clients (cid INT NOT NULL AUTO_INCREMENT PRIMARY KEY,clientname VARCHAR(30) NOT NULL, balance FLOAT);
Query OK, 0 rows affected (0.06 sec)

mysql> CREATE TABLE tdetails (tnumber INT NOT NULL AUTO_INCREMENT PRIMARY KEY,tmessage TEXT,tdate DATETIME);
Query OK, 0 rows affected (0.04 sec)

mysql> INSERT INTO clients (clientname,balance) VALUES ('John',1000),('Mike',100);
Query OK, 2 rows affected (0.01 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM CLIENTS;
+-----+------------+---------+
| cid | clientname | balance |
+-----+------------+---------+
|   1 | John       |    1000 |
|   2 | Mike       |     100 |
+-----+------------+---------
 
////DATABASE RELATIONSHIPS;
DATA IS RELATED TO ONE TABLE FROM DATA IN ANOTHER TABLE;

RELATIONSHIPS BETWEEN TWO TABLES ARE CREATED  USING KEYS; 
A KEY IN ONE TABLE WILL NORMALLY RELATE TO A KEY IN ANOTHER TABLE;
TWO TABLES IN A DATABASE MAY ALSO BE UNRELATED

THERE ARE MAINLY 3 TYPES OF DATABASE RELATIONSHIP:
ONE TO ONE (1:1) RELATIONSHIP:ONE DATA TO MANY DATA IN ANOTHER TABLE.
ONE TO MANY(1:M) RELATIONSHIP:ONE DATA TO MANY DATA IN ANOTHER TABLE.
MANY TO MANY(M:M) RELATIONSHIP:MANY DATA TO MANY DATA IN ANOTHER TABLE.

ONE TO ONE RELATIONSHIPS :
mysql> USE SCHOOL;
Database changed
mysql> SHOW TABLES;
+------------------+
| Tables_in_school |
+------------------+
| students         |
| students2        |
| subjects         |
| teachers         |
+------------------+
4 rows in set (0.07 sec)

mysql> CREATE TABLE examids (
    -> examid VARCHAR(10) NOT NULL,
    -> studentid INT NOT NULL);
Query OK, 0 rows affected (0.07 sec)

mysql> INSERT INTO examids VALUES ('id01',1),('id02',2),('id03',3);
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * students;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'students' at line 1
mysql> select * from students;
+-----------+-----------+----------+--------+------+
| studentid | FIRSTNAME | LASTNAME | class  | age  |
+-----------+-----------+----------+--------+------+
|         1 | John      | Doe      | Second |    5 |
|         2 | Mary      | Smith    | Third  |    7 |
|         3 | James     | Brown    | First  |    5 |
|         4 | Mike      | Walker   | Second |    6 |
|         5 | Linda     | Jones    | Third  |    7 |
|         6 | John      | Doe      | Third  |    7 |
|         7 | James     | Smith    | First  |    6 |
|         8 | John      | Brown    | Second |    6 |
|         9 | Daniel    | Jones    | First  |    7 |
|        10 | Paul      | Anderson | Third  |    5 |
|        11 | Mark      | Davis    | Second |    6 |
|        12 | Steven    | Thomas   | First  |    7 |
|        13 | Brian     | King     | Second |    5 |
|        14 | Kevin     | Hall     | First  |    6 |
|        15 | Jason     | Lee      | Third  |    5 |
|        16 | Jose      | Young    | First  |    6 |
|        17 | Frank     | Smith    | First  |    7 |
|        18 | Eric      | Jones    | Second |    7 |
|        19 | Jerry     | Martin   | Third  |    5 |
|        20 | Peter     | King     | First  |    6 |
|        21 | Henry     | Clark    | Second |    7 |
|        22 | Carl      | White    | Second |    5 |
|        23 | Joe       | Thomas   | First  |    7 |
|        24 | Jack      | Smith    | Third  |    6 |
|        25 | Roy       | King     | Second |    5 |
|        26 | Adam      | Hall     | First  |    6 |
|        27 | Bobby     | White    | Second |    7 |
|        28 | Johnny    | Davis    | First  |    6 |
|        29 | Jimmy     | Jones    | Third  |    5 |
|        30 | Emma      | Walker   | First  |    5 |
|        31 | Sophia    | Walker   | Third  |    6 |
|        32 | Ava       | Jones    | First  |    7 |
|        33 | Mia       | Smith    | Second |    6 |
|        34 | Emily     | Walker   | Second |    5 |
|        35 | Grace     | King     | First  |    5 |
|        36 | Lillian   | Jones    | Third  |    7 |
|        37 | Lily      | King     | Third  |    6 |
|        38 | Layla     | Young    | First  |    5 |
|        39 | Zoe       | Thomas   | Second |    7 |
|        40 | Anna      | Jones    | Second |    5 |
|        41 | Leah      | Brown    | Third  |    6 |
|        42 | Camila    | Hall     | First  |    5 |
|        43 | Riley     | Martin   | Third  |    6 |
|        44 | Nora      | Smith    | Second |    7 |
|        45 | Hailey    | Clark    | Second |    7 |
|        46 | Ellie     | King     | Third  |    5 |
|        47 | Lucy      | Jones    | Third  |    6 |
|        48 | Stella    | White    | First  |    5 |
|        49 | Bella     | White    | Second |    7 |
|        50 | Mila      | Smith    | Third  |    6 |
|        51 | Maya      | Brown    | First  |    5 |
|        52 | Faith     | Thomas   | Third  |    5 |
|        53 | Eva       | Brown    | Second |    7 |
|        54 | Julia     | King     | Third  |    6 |
|        55 | Ashley    | Davis    | First  |    5 |
|        56 | Ruby      | Young    | Third  |    7 |
|        57 | Alice     | Jones    | Second |    6 |
|        58 | Jasmine   | Hall     | Third  |    7 |
|        61 | John      | Doe      | First  |    5 |
|        62 | John      | Doe      | First  |    5 |
+-----------+-----------+----------+--------+------+
60 rows in set (0.00 sec)

mysql> select * from examids;
+--------+-----------+
| examid | studentid |
+--------+-----------+
| id01   |         1 |
| id02   |         2 |
| id03   |         3 |
+--------+-----------+
3 rows in set (0.00 sec)

mysql> use onlineshop;
Database changed
mysql> display tables;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'display tables' at line 1
mysql> show tables;
+----------------------+
| Tables_in_onlineshop |
+----------------------+
| categories           |
| customers            |
| items                |
| orders               |
+----------------------+
4 rows in set (0.00 sec)

mysql> create table itemcodes (
    -> itemcode VARCHAR(20) NOT NULL,
    -> itemid INT NOT NULL);
Query OK, 0 rows affected (0.04 sec)

mysql> INSERT INTO itemcodes VALUES('code1234',1),('code1235',2),('code1236',3);
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from items;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+
7 rows in set (0.01 sec)

mysql> select * from itemcodes;
+----------+--------+
| itemcode | itemid |
+----------+--------+
| code1234 |      1 |
| code1235 |      2 |
| code1236 |      3 |
+----------+--------+
3 rows in set (0.00 sec)

ONE TO MANY(1:M) RELATIONSHIP:ONE DATA TO MANY DATA IN ANOTHER TABLE.
IT IS THE MOST COMMON RELATIONSHIP IN REALTIONAL DATABASE MANAGEMENT SYSTEM
mysql> USE COMPANY;
Database changed
mysql> SELECT * FROM clients;
+----------+-------------+------------+-------------------------------------+
| clientid | name        | phone      | address                             |
+----------+-------------+------------+-------------------------------------+
|        1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|        2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|        3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|        4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
+----------+-------------+------------+-------------------------------------+
4 rows in set (0.01 sec)

mysql> SELECT * FROM PROJECTS;
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
| projectid | title                                                | clientid | employeeid | startdate           | enddate             |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
|         1 | Develop ecommerse website from scratch               |        1 |          3 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
|         2 | WordPress website for our company                    |        1 |          2 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         3 | Manage our company servers                           |        2 |          7 | 2020-05-20 11:33:43 | 2020-07-04 11:33:43 |
|         4 | Hosting account is not working                       |        3 |          9 | 2020-05-20 11:33:43 | 2020-05-27 11:33:43 |
|         5 | MySQL database from my desktop application           |        4 |         17 | 2020-05-20 11:33:43 | 2020-06-04 11:33:43 |
|         6 | Develop new WordPress plugin for my business website |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-30 11:33:43 |
|         7 | Migrate web application and database to new server   |        2 |       NULL | 2020-05-20 11:33:43 | 2020-05-25 11:33:43 |
|         8 | Android Application development                      |        4 |         23 | 2020-05-20 11:33:43 | 2020-06-19 11:33:43 |
+-----------+------------------------------------------------------+----------+------------+---------------------+---------------------+
8 rows in set (0.01 sec)

mysql> USE ONLINESHOP;
Database changed
mysql> SELECT * FROM ORDERS;
+---------+--------+------------------------------+-------+---------------------+
| orderid | userid | items                        | total | orderdate           |
+---------+--------+------------------------------+-------+---------------------+
|       1 |      2 | i7 processor, 8GB RAM Laptop |  1000 | 2020-05-20 11:35:39 |
|       2 |      1 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       3 |     25 | Healthy dog food recipes     |    19 | 2020-05-20 11:35:39 |
|       4 |      1 | How to train your cat        |    25 | 2020-05-20 11:35:39 |
|       5 |      3 | Blue Colored Jeans           |   150 | 2020-05-20 11:35:39 |
|       6 |     15 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
|       7 |      4 | Beautiful Black T-Shirts     |    99 | 2020-05-20 11:35:39 |
+---------+--------+------------------------------+-------+---------------------+
7 rows in set (0.01 sec)

mysql> SELECT * FROM CUSTOMERS;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.01 sec)
mysql> USE ONLINESHOP;
Database changed
mysql> SHOW TABLES;
+----------------------+
| Tables_in_onlineshop |
+----------------------+
| categories           |
| customers            |
| itemcodes            |
| items                |
| orders               |
+----------------------+
5 rows in set (0.00 sec)

mysql> CREATE TABLE order_history (
    -> user_id INT NOT NULL,
    -> item_id INT NOT NULL,
    -> order_date DATE);
Query OK, 0 rows affected (0.07 sec)

mysql> INSERT INTO order_history(userid,itemid,order_date) VALUES(5,1.'2016-02-14'),(1,1,'2016-02-14'),(5,3,'2016-02-14');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''2016-02-14'),(1,1,'2016-02-14'),(5,3,'2016-02-14')' at line 1
mysql> INSERT INTO order_history(userid,itemid,order_date) VALUES(5,1,'2016-02-14'),(1,1,'2016-02-14'),(5,3,'2016-02-14');
ERROR 1054 (42S22): Unknown column 'userid' in 'field list'
mysql> INSERT INTO order_history (user_id,itemid,order_date) VALUES (5,1,'2016-02-14'),(1,1,'2016-02-14'),(5,3,'2016-02-14');
ERROR 1054 (42S22): Unknown column 'itemid' in 'field list'
mysql> INSERT INTO order_history (user_id,item_id,order_date) VALUES (5,1,'2016-02-14'),(1,1,'2016-02-14'),(5,3,'2016-02-14');
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM CUSTOMERS;
+--------+-------------+------------+-------------------------------------+
| userid | name        | phone      | address                             |
+--------+-------------+------------+-------------------------------------+
|      1 | Jimmy Jones | 1234567890 | Victoria Pavilion, Las Vegas, NV    |
|      2 | Henry Clark | 0987654321 | 4125 Sydney Place, Miami, FL        |
|      3 | Ruby Young  | 1234512345 | 6170 Peshwar Place, Washington, DC  |
|      4 | Julia King  | 0987612345 | MountainView Hospital, Victoria, TX |
|      5 | Anna Jones  | 0987609876 | 1234 Obere Street, Miami, FL        |
+--------+-------------+------------+-------------------------------------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM ITEMS;
+--------+------------+-----------------------------------------+-------+
| itemid | categoryid | name                                    | price |
+--------+------------+-----------------------------------------+-------+
|      1 |          1 | Android Mobile Phone                    |   250 |
|      2 |          1 | i7 processor, 8GB RAM Laptop            |  1000 |
|      3 |          2 | How to train your cat                   |    25 |
|      4 |          2 | Healthy dog food recipes                |    19 |
|      5 |          2 | Learn how to meditate for mental health |    30 |
|      6 |          3 | Beautiful Black T-Shirts                |    99 |
|      7 |          3 | Blue Colored Jeans                      |   150 |
+--------+------------+-----------------------------------------+-------+

7 rows in set (0.00 sec)

mysql> SELECT * FROM ORDER_HISTORY;

+---------+---------+------------+
| user_id | item_id | order_date |
+---------+---------+------------+
|       5 |       1 | 2016-02-14 |
|       1 |       1 | 2016-02-14 |
|       5 |       3 | 2016-02-14 |
+---------+---------+------------+
3 rows in set (0.00 sec)


### HAPPY  SQL CODING 10 TEN THOUSANDS
 












































































































 
 




