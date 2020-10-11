基础操作，简单查询，比较运算，逻辑运算，排序查询，分组查询，分页查询，复制数据到已存在的表格

###简单查询
    create table products（pid int，pname varchar(20),price double)；
    select * from products；
    select pname,price from products;  *//查询商品名和价格*
    select * from products as p； *// 表别名
    select pname as pn from prducts；
    select distinct price from products； *//去重复
    select pname，price+10 from products； *//查询结果是表达式，将所有商品的价格+10元进行显示

###条件查询
####比较运算符 
* >  <    >=   <=    =    <>   != 
* between....and....  区间（包含头尾）
* IN（set） 显示在in列表中的值，例如：in（100，200）

* LIKE '张%'    LIKE '%涛%'    模糊查询，Like语句中，% 代表零个或多个任意字符, _代表一个字符，例如： first_name like '_a%';

* IS NULL ；  IS NOT NULL 判断是否为空

####逻辑运算符
* and  多个条件同时成立
* or 多个条件任一成立
* not 不成，where not(salary>100);


##排序查询
order by  将查询的结果进行排序，暂时放置在select的后面
> select * from 表名 order by 排序字段 ASC|DESC;  
ASC 升序（默认）
DESC 降序
![image.png](https://upload-images.jianshu.io/upload_images/3732474-eaa06f2812d90f1e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



###聚合查询
聚合函数查询是纵向查询，它是对一列的值进行计算，然后返回一个单一的值，聚合函数会忽略空值。
######cont()  统计指定列不为NULL的记录行数
       select count(*或者1或者字段名) from products;  *//在统计某一列时，如果值为null，那么这条不统计；*
######sum()   计算指定列的数值和，如果指定列类型不是数值，那么计算结果为0；
       select sum(price) from products;  *//只能计算数值型，非数值无意义//*
######max()   计算指定列的最大值，如果指定列是字符串类型，那么使用字符串排序运算；
       select max(price) from products;
######min()    计算指定列的最小值，如果指定列是字符串类型，那么使用字符串排序计算；
      select min(price) from products;
######avg()    计算指定列的平均值，如果指定列类型不是数值，那么计算结果为0；
      select avg(price) from products;
      select min(price),max(price) from products;


##分组查询
###having和where 的区别：
having是对分组后的数据进行过滤，where后面不可以使用分组函数；
分组之后，select后面只能跟分组字段 和聚合函数


###SQL语句的执行顺序
form>where>group by>聚合函数>having>select

##分页查询 limit
limit M,N

N表示每页要显示多少条
M表示，起始索引值，从第几条开始显示
> `每页显示5条
> 第1页： limit 0,5
> 第2页： limit 5,5
> 第3页： limit 10,5
> 第4页： limit 15,5
> 第5页： limit 20,5`
....
第10页： limit (10-1)*5,5
查询表的前5条数据：
select * from products limit 0,5

##insert into select 语句
从一个表中复制数据，然后把数据插入到已存在的表中
insert into product2 select id，pname from products where pname=‘华为’；
