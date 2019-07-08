
## mysql 学习笔记

打开数据库 mysql -u root -p 

显示数据库show databases;

创建数据库 create database test;

使用数据库 use database test;

查看创建数据库语句 show create database test\G; 加入\G 显示的结构更清晰

创建数据库表 create table user (id int(12) primary key auto_increment,name varchar(25),location
 varchar(50));

修改表名 alter table user rename [to] student;

查看数据表结构 desc user;

查看数据库表的创建语句 show create table user\G;

修改字段的数据类型 alter table user modify location varchar(30);

修改字段名称 alter table user change location loc varchar(25);

添加表的新字段名 alter table user add age int(3);

删除字段 alter table drop age;

添加心字段名到指定位置 alter table user add age int(3) not null after name;
alter table user add sex char(2) first;

修改字段在表的制定位置 alter table user modify sex char(2) after name;

插入数据 insert into student (id,name,age,sex,loc) values (3,"王二",20,"男","北京");

查询所有数据 select * from student;


