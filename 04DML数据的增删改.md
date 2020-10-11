#数据的增、删、改

## 增   插入记录 insert
### 原则：

* 数据大小必须在字段得长度范围内
* 值与字段必须对应，个数相同，类型相同
* 除了数值类型外，其它得字段类型得值必须使用音号引起（建议单引号）
* 如果要插入空值，可以不写字段，或者插入空值

insert into 表(字段1,字段2,字段3) values(值1,值2,值3)；   *//列，对应具体的值* 

insert into 表 values(值1,值2,值3)； *//默认给列全部的数据，如果没有的话写NULL*

insert into 表 values (值1,值2,值3),(值1,值2,值3),(值1,值2,值3);  *//一次插入多条数据*

select * from testx    *//查看表的所有数据*

例如表testx：cid  name

insert into testx(cid) values('c003');  
inset into testx(cid,name) values('003',NULL); 
insert into testx values('c004','水果');   
inster into testx values ('c008','蔬菜'),('c009','坚果'),('c010','熟食');

##更新表记录 update
用来修改指定条件的数据，将满足条件的记录指定修改为指定值
### 语法：

update 表名 set 字段名=值,字段名=值,...;     *//更新所有记录的指定字段*

update 表名 set 字段名=值，字段名=值,... where 条件；*//更新符合条件记录的指定字段*

表testshop，字段 icd，name

update testshop set name='水果';

update testshop set name='苹果' where cid='003';

## 删除记录 delete
delete from 表名 [where 条件];

delete from testshop;  *//删除所有数据,一条一条删除*

truncate table testshop;   *//删除所有数据，删除表，再建一个新表*

delete from testshop where cid='003';

注意：delect 删除一条数据，不清空auto_increment记录数。
truncate 直接将表删除，重新建表，auto_increment将置为0，从新开始。

create table employee(id int,name varchar(20),salary int)；

update employee set salary=salary+1000 where name='xue';





