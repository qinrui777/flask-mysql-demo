# flask-mysql-demo
> set up a demo for flask 、mysql with Mac OS 



### Set up mysql (docker)

获取镜像
`docker pull mysql:5.6.45`

启动镜像，并设置密码
`docker run --name flask-mysql-demo1 -e MYSQL_ROOT_PASSWORD=password -p 3306:3306 -d mysql:5.6.45`

测试
```bash
➜docker exec -it flask-mysql-demo1 bash
root@9b6b3dafbaab:/# mysql -uroot -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 1
Server version: 5.6.45 MySQL Community Server (GPL)

Copyright (c) 2000, 2019, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.00 sec)

mysql>
```

准备一个数据库
```bash
mysql> CREATE DATABASE flaskapp;
Query OK, 1 row affected (0.00 sec)

mysql> USE flaskapp;
Database changed
mysql> CREATE TABLE users(name varchar(20),email varchar(40));
Query OK, 0 rows affected (0.01 sec)

mysql> SELECT * FROM users;
Empty set (0.00 sec)
```


###  Set up Virtual Env
`virtualenv venv`

`source venv/bin/activate`

pip install -r requirements.txt



Ref: 
- https://github.com/febin-george/flaskapp