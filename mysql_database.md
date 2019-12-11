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
### [简书部分优秀文章](https://www.jianshu.com/p/118e1c41e9f0)
1. alter table user modify column name varchar(50) ; --修改字段长度
- alter table test change  column address address1 varchar(30)--修改表列名
- alter table test add  column name varchar(10); --添加表列
- --添加CreateTime 设置默认时间 CURRENT_TIMESTAMP 
- ALTER TABLE `table_name`
- ADD COLUMN  `CreateTime` datetime NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间' ;
- -修改CreateTime 设置默认时间 CURRENT_TIMESTAMP 
- ALTER TABLE `table_name`
- MODIFY COLUMN  `CreateTime` datetime NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间' ;
- mySql 设置表的自增主键的起始值
- alter table    表名  AUTO_INCREMENT = 1000;
2. 查询表的所有字段及注释
- select column_name,column_comment from information_schema.columns where table_name='表名' and table_schema='数据库名'
3. 驱动连接:
- jdbc:mysql://x.x.x.x:3306/whaleconfig?useUnicode=true&characterEncoding=UTF-8&autoReconnect=true&autoReconnectForPools=true&allowMultiQueries=true
4. 创建用户并授权
- grant all privileges on *.* to 'test'@'%' identified by 'test' with grant option;
- flush privileges;
- show grants for test;
5. 创建数据库
- create database if not exists test default charset utf8 collate utf8_general_ci;
6. 修改mysql最大连接数
- 配置文件中:
- /etc/mysql/my.conf or /vi /etc/my.cnf
- [mysqld]
- max_connections = 40960
- Shell中(不用重启):
- show variables like '%max_connections%'
- set GLOBAL max_connections=40960
7. 查看某个实例的数据库连接数
- select * from (select substr(host,1,instr(host,':')-1) as ip,count(1) count from information_schema.`PROCESSLIST` where db='spring' group by substr(host,1,instr(host,':')-1) t order by count desc;
8. mysql8.0安装教程: https://blog.csdn.net/qq_37350706/article/details/81707862
### 数据库E-R模型
- E-entry表示实体，R-relationship表示关系，两个实体间对应关系规则，包括一对一，一对多，多对多，
数据表中的一个列在关系型数据库中一行就是一个对象
### 三范式
- 第一范式（1NF）:列不可拆分
- 第二范式（2NF）：唯一标识
- 第三范式（3NF）：引用主键
- 后一个范式，均为在前一个范式的基础上建立的
### 数据完整性：在创建表的时候，为表添加一些强制性的验证，包括数据字段的类型、约束
### 常用的字段数据类型，如：
- 数字：int，decimal
- 字符串：varchar，text
- 日期：datetime
- 布尔：bit
### 常见约束：
- 主键：primary key
- 非空：not null
- 唯一：unique
- 默认：default
- 外键：foreign key
### 库操作，五个，举个例子，我们对数据库testma进行创建、删除、切换、查看操作
- 查看所有的数据库：show databases;
- 创建：create database testma;
- 删除：drop database testma;
- 切换：use testma;
- 查看当前：select database();
### 表操作，举个例子，对表students进行创建、修改、
- 查看当前库中所有表：show tables;
- 创建表，auto_increment表示自动增长：
create table students(id int auto_increment primary key,sname varchar(10) not null)
- 修改表 alter table 表名 add|change|drop 列名 类型；如
alter table students add birthday datetime;
- 删除表：drop table students;
- 查看表结构：describe students/即desc students;
- 更改表名称：rename table 原表名 to 新表名;
- 查看表的创建语句：show create table '表名';
### 数据操作
- 查询：select * from students;
- 增加：
- 全列插入：insert into 表名 values(...)
- 缺省插入：insert into 表名(列1,...) values(值1,...)
- 同时插入多条数据：insert into 表名 values(...),(...)...;
- 或insert into 表名（列1,...） values(值1,...),(值1,...)...;
- 修改
- update 表名 set 列1=值1,... where 条件
- 删除
- delete from 表名 where 条件
- 逻辑删除，本质就是修改操作update
### 查询
- 条件查询-比较运算符（= | > | < | >= | <= | !=）、
- 逻辑运算符(and、or、not)
- 模糊查询（like、%-任意多个任意字符、_表示一个任意字符）
- 范围查询（in表示在一个非连续的范围内，between...and..表示在一个连续范围内）
- 如select * from students where id in(1,3,8);
- select * from students where id between 3 and 8;
- 空判断is null 如select * from students where hometown is null;
### 优先级
- 小括号，not，比较运算符，逻辑运算符
- and比or先运算，如果同时出现并希望先算or，需要结合()使用
### 聚合查询（5个聚合函数）
- count(*)计算总行数
- max(列名)表示求此列的最大值
- min(列名)表示求此列的最大值
- sum(列名)表示求此列的和
- avg(列名)表示求此列的平均值
### 分组查询
- SELECT 性别,学号 as number,姓名 as name from student group by 性别,name,number;
### 排序查询
- select * from 表名 order by 列1 asc|desc, 列2 asc|desc,...
- 将行数据按照列1进行排序，如果某些行列1的值相同，则按照列2排序，依次类推
- 默认情况是从小到大排序，asc从小到大排序，desc从大到小排序
- 分页select * from 表名 limit start,count
- 即从start开始，获取count条数据，start索引从0开始
### sql语句书写顺序一般为
- select-from-where-group by-having-order by-limit这种顺序
### 连接查询
- 表A inner join 表B:表A与表B匹配的行会出现在结果中
- 表A left join 表B:表A与表B匹配的行会出现在结果中,外加表A中独有的数据，未对应的数据使用null填充
- 表A right join 表B:表A与表B匹配的行会出现在结果中,外加表B中独有的数据，未对应的数据使用null填充
- 在查询或条件中推荐使用“表名.列名”的语法
### 视图（对于较为复杂的查询，定义视图是一种很好的办法）
### 视图本质上相当于对查询的一个封装
- 定义视图：
- create view stuscore as select student.*,scores.score from scores
- inner join student on scores.stuid=student.id;
- 视图的用途就是查询 select * from stuscore;
### 事务
- 当一个业务逻辑需要多个sql完成时，如果其中某条sql语句出错，则希望整个操作都退回
### 事务的四大特性（简称ACID）
1.原子性 2.一致性 3.隔离性 4.持久性
