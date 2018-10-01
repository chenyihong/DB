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
```
创建新的数据表格 `TABLE`为表格名称
                `ID`和`context`为字段(标题)
                `INT`和`VARCHAR`为数据类型
                `NOT NULL`和`NULL`可否为无
                `PRIMARY KEY`为列表的主关键字
```
```
字符串类型     字节大小         描述及存储需求

CHAR         0-255字节          定长字符串

VARCHAR      0-255字节          变长字符串

TINYBLOB     0-255字节        不超过 255 个字符的二进制字符串

TINYTEXT     0-255字节        短文本字符串

BLOB         0-65535字节      二进制形式的长文本数据

TEXT         0-65535字节      长文本数据

MEDIUMBLOB   0-16 777 215字节 二进制形式的中等长度文本数据

MEDIUMTEXT   0-16 777 215字节 中等长度文本数据

LOGNGBLOB    0-4 294 967 295字节 二进制形式的极大文本数据

LONGTEXT     0-4 294 967 295字节 极大文本数据

VARBINARY(M)                   允许长度0-M个字节的定长字节符串，值的长度+1个字节

BINARY(M)    M                 允许长度0-M个字节的定长字节符串
```

```
CREATE TABLE(
  ID INT NOT NULL PRIMARY KEY,
  context VARCHAR(255) NULL
);
```

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


