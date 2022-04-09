# 一、基本配置  

### 1.修改密码 ###
**通用：**ALTER user 用户名@主机名 IDENTIFIED BY "新密码";  
(eg:ALTER user root@localhost IDENTIFIED BY "新密码;)  
mysql安装后默认root为用户名,localhost为主机名

**5.x:** SET password for root@localhost=password("新密码");  
设置完需要**刷新权限**: flush privileges;

~~*忘记密码*~~:首先**停止MySQL服务**,然后在my.ini文件中加入skip-grant-tables;
保存后重新**启动**MySQL服务,直接输入 **mysql -uroot+回车** 即可进入MySQL命令行修改密码.  
(改完密码需要去掉my.ini文件中的skip-grant-tables,否则一直处于安全模式)

### 2.查询用户 ###
use mysql; <br> select user,host from user;  
修改用户连接权限: UPDATE user set host='%' where user='用户名';  
其中,%可以是任意IP/IP段,如果直接设置成%代表所有IP均可以通过此用户连接数据库

### 3.创建与查看 ###
创建新用户: CREATE user username@% IDENTIFIED BY 'password';  
查看连接数: show processlist;

### 4.基本语法 ###
|命令方法|含义|命令方法|含义|
|:------|:---|:------|:---|
|show database;|查看数据库|show tables;|查看数据库中的所有表|
|use {database name};|使用数据库|desc {table name}|查看表结构|
|create database {库名};|创建数据库|drop database {库名};|删除数据库|
|drop table {表名};|删除数据表|delete from {表名} where ...;|删除指定条件的数据(整行)|

|  commands      | meaning        |
| :------------- | :------------- |
| insert into {表名} (field,field2...) values(v,v2...); | 插入一条数据,对应的字段值为v,v2... |
| update {表名} set filed=v,field2=v2 where ...; | 修改指定行的字段值 |
| select {字段,字段2 as alias(别名),字段3...} from {表名} {where Clause} {limit N} {offset M} {order by 字段} | 查找表中符合条件的行的字段,字段2,字段3... <br> from后面可以接多个表 |
| select * from {表名} | 查看表的所有行的字段,select as用于修改查询时显示的字段名称 |
| where子句:where condition {and/or} condition2... | 和增删改查一起使用,用于筛选符合条件的数据 |
| like子句(模糊匹配):where {字段1} like '%a' | 筛选字段1以a结尾的行,%范围占位符,_单位占位符 |
| like子句示例:'%a%' '\_a\_' [] \[^] | 中间有a 三位且中间是a 类似正则 查询内容含%,_等可用[]括起来 |
| create table if not exist {表名}(<br> 字段1 type auto_increment primary key,<br> 字段2 type not null,<br> ...,<br> primary key(某字段) <br>)engine=InnoDB default charset=utf8; | 建表 |
| select e1,... from {表1}{where} union {all/distinct} select e',... from {表2}{where}; | union查询, distinct不显示重复数据,all显示,默认distinct |
| select e1,... form {表} group by {字段}; | group by分组子句,e1可以是字段也可以是**函数** |
| select f1... from table1... order by f1 {ASC/DESC(降序)} | order by排序子句,默认ASC(升序) |

## [菜鸟MySQL教程](https://www.runoob.com/mysql/mysql-tutorial.html) ##
