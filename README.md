# ---DATABASE---
1.MySQL
2.Access
3.Oracle


C:\Program Files\MySQL\MySQL Server 8.0\bin>mysql.exe `-u root -p`

Enter password:***********

show databases;//打印所有数据库的列表
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mydb               |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```
use mydb ← 也可以是 use mydb;

show tables;//查看此数据库中所有的表格
```
+----------------+
| Tables_in_mydb |
+----------------+
| mytable        |
+----------------+
```
describe mytable;
```
+---------+--------------+------+-----+---------+-------+
| Field   | Type         | Null | Key | Default | Extra |
+---------+--------------+------+-----+---------+-------+
| id      | int(11)      | NO   | PRI | NULL    |       |
| context | varchar(255) | YES  |     | NULL    |       |
+---------+--------------+------+-----+---------+-------+
```
