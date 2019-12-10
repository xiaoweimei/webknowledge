### 数据库范式（四种范式）
- 第一范式（1NF）、第二范式（2NF）、第三范式（3NF）、BCN范式（BCNF）
- 第一范式要求表中不能有重复字段，并且每个字段不能再拆分。
### 了解数据库和数据库系统的区别
- 数据库系统不是单纯的数据库，而是由数据库、数据库管理系统、应用开发工具构成，很多时候，数据库管理员
- 和用户可以当成数据库系统的一份子
#### 数据定义语言：DDL语句
#### 数据操作语言：DML语句
#### 数据控制语言：DCL语句
### mySQL数据库优势
1.开放源代码 2.跨平台 3. 价格优势 4.功能强大且使用方便
### 四条基本命令
- 显示数据库|使用数据库|显示数据表|查看表结构
- show databases;|use database;|show tables;|show columes from tablename;
- 创建数据库test- create database test
- 创建表friendstbl — create table friendstbl(name varchar(20), address varchar(50), phone varchar(30));
- 删除数据表 drop table friendstbl;
### 数据表的增，删，改，查
- 增   insert into friendstbl(name,address,phone) values('张三','西二旗','123456');
- 删   delete from friendstbl(name,address,phone) where name='张三';
- 改   update friendstbl set address='上地' where name='张三';
- 查   select name,phone from friendstbl where address='西二旗';
### 显示当前用户，当前数据库，数据库版本号
- 显示当前用户         select user();
- 显示当前数据库       select database();
- 显示数据库版本号     select version();
### 创建用户，删除用户，修改密码，为用户授权
- create user 'username'@'host'[identified by 'passward']
- 示例：
- mysql> create user hjj2@localhost identified by '123456';
- mysql> create user hjj2@'%'identified by '123456'; #可从任何一台远程机器登陆
- mysql> drop user hjj2@localhost
- mysql> set password for hjj@localhost = password('123');
### 数据库存储引擎的选择
1.InnoDB存储引擎
2.MyISAM存储引擎
3.MEMORY存储引擎
