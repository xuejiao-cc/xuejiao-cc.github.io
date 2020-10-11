## Mysql的登录：
### 方式1：
 mysql -u root -p123456
mysql -u root -p 然后回车输入密码

### 方式2 ，通过远程的方式连接到别的Mysql服务器
mysql --host=192.168.88.100 --user=root --password=123456
mysql --host=192.168.88.100 --user=root --password

## 数据的类型：
### 整数
       tinyint 很小的整数   最大到127
       smallint 小的整数
       mediumint 中等大小的整数
       int（integer）普通大小的整数
       bigint   2^64-1    

### 小数类型
      float 单精度浮点整数   123.2134   （6位）
      double 双精度浮点整数  （14位）
      decimal （m，d） 压缩严格的定点数  decimal(10,2)，10个有效位（整数+小数），小数保留2位
### 日期类型
      year   YYY  1901~2155
      time   HH：MM：SS   
      date   YYY-MM-DD   
      datetime  年月日时分秒  YYY-MM-DD HH：MM：SS 
### 文本
     varchar：描述字符串 varchar（20），该字符串的最大长度是20，该类型会自动调整实际长度；



