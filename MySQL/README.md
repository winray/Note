####Note for MYSQL
- 显示MYSQL的版本
 - select version();
- 显示当前时间
  - select now();
- 显示字符串
  - SELECT "welecome to my blog!"
- 当计算器用
  - select ((4 * 4) / 10 ) + 25; 
- 串接字符串
	```sql
	select CONCAT(f_name, " ", l_name) 
	AS Name 
	from employee_data 
	where title = 'Marketing Executive'; 
	```
- 创建数据表
   ```sql
   create table MyClass(
		id int(4) NOT NULL primary key auto_increment,
		name char(20) NOT NULL,
		sex int(4) NOT NULL default '0',
		degree double(16,2)
   ) ENGINE = MYISAM;
   #Double(M, D):M是显示宽度而D是小数位数。
   ```
- 获取数据表结构
  - `desc`命令用于获取数据表结构。
  ```sql
  desc 表名;
  同样
     show columns from 表名;
  也能获取数据表结构。
  举例如下：
	mysql> desc MyClass;
	mysql> show columns from MyClass;
  ```
- 删除数据表
  - drop table命令用于删除数据表。
  ```sql
  drop table命令格式：drop table <表名>;

	例如，删除表名为 MyClass 的表：
		mysql> drop table MyClass;
  ```
- 向表中插入数据（记录）
  ```sql
  insert into命令格式：insert into <表名> [(<字段名1>[,..<字段名n > ])] values ( 值1 )[, ( 值n )];
  insert into MyClass values(1,'Tom',96.45),(2,'Joan',82.99), (2,'Wang', 96.59);
  ```
- 查询表中的数据（记录）
  ```sql
  命令格式： select <字段1, 字段2, ...> from < 表名 > where < 表达式 >;
  #查看表 MyClass 中所有数据：
  mysql> select * from MyClass;
  #查看表 MyClass 中前2行数据：
  mysql> select * from MyClass order by id limit 0,2;
  #select一般配合where使用，以查询更精确更复杂的数据。
  ```
- 删除记录
  - delete from命令用于删除表中的数据。
  ```sql
  #delete from命令格式：delete from 表名 where 表达式
  delete from命令格式：delete from 表名 where 表达式
  删除表 MyClass中编号为1 的记录：
    mysql> delete from MyClass where id=1;
  ```
- 修改表中的数据
  - update set命令用来修改表中的数据。
  ```sql
  update set命令格式：update 表名 set 字段=新值,… where 条件;
  #举例如下：
  mysql> update MyClass set name='Mary' where id=1;
  ```
  - UPDATE语法可以用新值更新原有表行中的各列。SET子句指示要修改哪些列和要给予哪些值。WHERE子句指定应更新哪些行。如果没有WHERE子句，则更新所有的行。如果指定了ORDER BY子句，则按照被指定的顺序对行进行更新。LIMIT子句用于给定一个限值，限制可以被更新的行的数目。
- 增加表的字段
  - alter add命令用来增加表的字段。
  ```sql
  alter add命令格式：alter table 表名 add字段 类型 其他;
  例如，在表MyClass中添加了一个字段passtest，类型为int(4)，默认值为0：
  mysql> alter table MyClass add passtest int(4) default '0';
  ```
  - 加索引
   mysql> alter table 表名 add index 索引名 (字段名1[，字段名2 …]);
   ```sql
   mysql> alter table employee add index emp_name (name);
   ```
  - 加主关键字的索引
    mysql> alter table 表名 add primary key (字段名);
	```sql
	mysql> alter table employee add primary key(id);
	```
  - 加唯一限制条件的索引
    mysql> alter table 表名 add unique 索引名 (字段名);
	```sql
	例子： mysql> alter table employee add unique emp_name2(cardnumber);
	```
  - 删除某个索引
   mysql> alter table 表名 drop index 索引名;
   ```sql
   例子： mysql>alter table employee drop index emp_name;
   ```
  - 增加字段
   `mysql> ALTER TABLE table_name ADD field_name field_type;`
  - 修改原字段名称及类型
   `mysql> ALTER TABLE table_name CHANGE old_field_name new_field_name field_type;`
  - 删除字段
    `MySQL ALTER TABLE table_name DROP field_name;`
- 修改表名
  - rename命令用于修改表名。
    - rename命令格式：rename table 原表名 to 新表名;
  ```sql
  例如，在表MyClass名字更改为YouClass：
    mysql> rename table MyClass to YouClass;
  ```




















