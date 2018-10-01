# ---DATABASE---

* MySQL
* Access
* Oracle

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
创建新的数据表格 `mytable`为表格名称
                `ID`和`context`为字段(标题)
                `INT`和`VARCHAR`为数据类型/字符串类型
                `NOT NULL`和`NULL`可否为无
                `AUTO_INCREMENT`当输入新的数据,ID会自动增加
                `PRIMARY KEY`为列表的主关键字
```

```
CREATE mytable(
  ID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  context VARCHAR(255) NULL
);
```

```
字符串类型     字节大小              描述及存储需求

CHAR          0-255字节             定长字符串

VARCHAR       0-255字节             变长字符串

TINYBLOB      0-255字节             不超过 255 个字符的二进制字符串

TINYTEXT      0-255字节             短文本字符串

BLOB          0-65535字节           二进制形式的长文本数据

TEXT          0-65535字节           长文本数据

MEDIUMBLOB    0-16 777 215字节      二进制形式的中等长度文本数据

MEDIUMTEXT    0-16 777 215字节      中等长度文本数据

LOGNGBLOB     0-4 294 967 295字节   二进制形式的极大文本数据

LONGTEXT      0-4 294 967 295字节   极大文本数据

VARBINARY(M)                        允许长度0-M个字节的定长字节符串，值的长度+1个字节

BINARY(M)    M                      允许长度0-M个字节的定长字节符串
```




```
show tables;//查看此数据库中所有的表格
+----------------+
| Tables_in_mydb |
+----------------+
| mytable        |
+----------------+
```

```
用于查看表格的数据类型
describe mytable;     <========= describe 可以用缩写 desc
+---------+--------------+------+-----+---------+----------------+
| Field   | Type         | Null | Key | Default | Extra          |
+---------+--------------+------+-----+---------+----------------+
| ID      | int(11)      | NO   | PRI | NULL    | auto_increment |
| context | varchar(255) | YES  |     | NULL    |                |
+---------+--------------+------+-----+---------+----------------+
```

```
用于输入数据
-案例1:
INSERT INTO mytable (id,context)
VALUES(1,"primo");
Query OK, 1 row affected (0.53 sec)
+----+---------+
| ID | context |
+----+---------+
|  1 | primo   |
+----+---------+

-案例2:[用于有AUTO_INCREMENT]
INSERT INTO mytable(context)
VALUES("secondo");
Query OK, 1 row affected (0.24 sec)
+----+---------+
| ID | context |
+----+---------+
|  1 | primo   |
|  2 | secondo |
+----+---------+

-案例3:
INSERT INTO mytable
VALUES(3,"TERZO");
Query OK, 1 row affected (0.21 sec)
+----+---------+
| ID | context |
+----+---------+
|  1 | primo   |
|  2 | secondo |
|  3 | TERZO   |
+----+---------+
```
```
用于删除指定表格中的个别指定数据
DELETE FROM mytable
WHERE ID=3;   <===========删除的条件,此处为id为3的所有数据
Query OK, 1 row affected (0.21 sec)
+----+---------+
| ID | context |
+----+---------+
|  1 | primo   |
|  2 | secondo |
+----+---------+
```

```
用于查看表格中所有数据
mysql> select * from mytable;
+----+---------+
| id | context |
+----+---------+
|  1 | primo   |
+----+---------+
```

```
用于删除表格(!!!!!慎用!!!!!)
mysql> DROP TABLE mytable;
Query OK, 0 rows affected (1.17 sec)
```

```
DESCRIBE mysql.user;
+------------------------+-----------------------------------+------+-----+-----------------------+-------+
| Field                  | Type                              | Null | Key | Default               | Extra |
+------------------------+-----------------------------------+------+-----+-----------------------+-------+
| Host                   | char(60)                          | NO   | PRI |                       |       |
| User                   | char(32)                          | NO   | PRI |                       |       |
| Select_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Insert_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Update_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Delete_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Create_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Drop_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Reload_priv            | enum('N','Y')                     | NO   |     | N                     |       |
| Shutdown_priv          | enum('N','Y')                     | NO   |     | N                     |       |
| Process_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| File_priv              | enum('N','Y')                     | NO   |     | N                     |       |
| Grant_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| References_priv        | enum('N','Y')                     | NO   |     | N                     |       |
| Index_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Alter_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Show_db_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| Super_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Create_tmp_table_priv  | enum('N','Y')                     | NO   |     | N                     |       |
| Lock_tables_priv       | enum('N','Y')                     | NO   |     | N                     |       |
| Execute_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| Repl_slave_priv        | enum('N','Y')                     | NO   |     | N                     |       |
| Repl_client_priv       | enum('N','Y')                     | NO   |     | N                     |       |
| Create_view_priv       | enum('N','Y')                     | NO   |     | N                     |       |
| Show_view_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Create_routine_priv    | enum('N','Y')                     | NO   |     | N                     |       |
| Alter_routine_priv     | enum('N','Y')                     | NO   |     | N                     |       |
| Create_user_priv       | enum('N','Y')                     | NO   |     | N                     |       |
| Event_priv             | enum('N','Y')                     | NO   |     | N                     |       |
| Trigger_priv           | enum('N','Y')                     | NO   |     | N                     |       |
| Create_tablespace_priv | enum('N','Y')                     | NO   |     | N                     |       |
| ssl_type               | enum('','ANY','X509','SPECIFIED') | NO   |     |                       |       |
| ssl_cipher             | blob                              | NO   |     | NULL                  |       |
| x509_issuer            | blob                              | NO   |     | NULL                  |       |
| x509_subject           | blob                              | NO   |     | NULL                  |       |
| max_questions          | int(11) unsigned                  | NO   |     | 0                     |       |
| max_updates            | int(11) unsigned                  | NO   |     | 0                     |       |
| max_connections        | int(11) unsigned                  | NO   |     | 0                     |       |
| max_user_connections   | int(11) unsigned                  | NO   |     | 0                     |       |
| plugin                 | char(64)                          | NO   |     | caching_sha2_password |       |
| authentication_string  | text                              | YES  |     | NULL                  |       |
| password_expired       | enum('N','Y')                     | NO   |     | N                     |       |
| password_last_changed  | timestamp                         | YES  |     | NULL                  |       |
| password_lifetime      | smallint(5) unsigned              | YES  |     | NULL                  |       |
| account_locked         | enum('N','Y')                     | NO   |     | N                     |       |
| Create_role_priv       | enum('N','Y')                     | NO   |     | N                     |       |
| Drop_role_priv         | enum('N','Y')                     | NO   |     | N                     |       |
| Password_reuse_history | smallint(5) unsigned              | YES  |     | NULL                  |       |
| Password_reuse_time    | smallint(5) unsigned              | YES  |     | NULL                  |       |
+------------------------+-----------------------------------+------+-----+-----------------------+-------+
```





```
mysql> exit
Bye
```
![image](https://github.com/chenyihong/DB/blob/master/1.jpg)
