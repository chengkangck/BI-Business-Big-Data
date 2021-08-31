# 数据库管理系统MySQL

## 一、MySQL的介绍

### 1、大数据本质

- 利用大数据的软件工具对大数据进行处理，从数据中挖掘价值

### 2、数据处理流程

- 数据采集：将产生各种数据进行统一化的存储
- 数据存储：将数据存储数据仓库中
- 数据处理：使用SQL开发语言开发程序对数据进行处理
- 数据应用：将处理好的结果进行 应用

### 3、数据存储及处理

- 存储的形式：文件
  - 不能满足企业中对于数据处理需求
- 工作需求：更加规范的数据存储、处理
  - 早期：Excel【表格，聚合统计分析，图表】
  - 问题
    - Excel能承载的数据量大小：MB
      - 实际工作中要处理的数据大小：GB
    - Excel中提供的功能不能满足对数据处理的需求
      - 支持开发不同的功能
      - 开发的方式不太友好
  - 解决
    - 数据库管理系统

### 4、数据库管理系统

- 功能
  - 专门用户数据存储、处理数据的工具
- 特点
  - 承载数据量会更大
  - 更加规范化
  - 功能更加全面
  - 开发接口更加优化：SQL
- 应用场景
  - 网站后台中存储商品信息、订单信息、用户注册 信息

### 5、MySQL介绍及概念

- 常见的数据库管理系统

  - Oracle：Sun公司商业化数据库产品，性能功能是最强大，但是是收费的商业化产品
  - SQL Server：微软公司的产品，受Windows局限性比较大 ，市场占有率并不高，收费
  - MySQL：Sun公司的社区产品，体积小，速度快，总体使用的成本比较低

- MySQL的介绍

  - 典型的市场占有率是最高的数据库管理系统
  - 在国内非常广泛
    - 所有网站后台的存储

- 概念

  - 数据库管理系统

    - 专门用户存储和处理数据【结构化数据】的工具
    - MySQL就是一个数据库管理系统

  - 结构化数据

    - 例如：表格，行和列是固定的
    - 行和列是固定的结构，就是数据的格式存在一定的规律

  - 数据库：MySQL中用于管理和区分数据表的单元

    - database
    - 理解为对数据进行分类存放的划分
    - 数据库1：存放用户的数据
    - 数据库2：存放商品的数据
    - 数据库3：存放订单的数据
    - 类似于一个Excel文件
      - 人事：人事的Excel文件
      - 财务：财务的Excel文件

  - 表格：MySQL中用于在数据库中划分数据的单元

    - 将数据进行更细的划分
    - 类似于一个Excel文件中会有多张表
      - 人事Excel文件 
        - 在职人员信息表
        - 离职人员信息表
      - 财务Excel文件
        - 报销信息表
        - 收入信息表
        - 报税信息表

  - 数据库管理系统与Excel对比

    |           Excel            |      MySQL       |
    | :------------------------: | :--------------: |
    |       一个Excel文件        |    一个数据库    |
    | 可以有多个Excel的sheet表格 | 可以有多张数据表 |
    |        表格有行和列        |  表格中有行和列  |

    - 区别：
      - MySQL功能更加强大
      - Excel的开发比较复杂
      - MySQL对数据进行处理：SQL

- MySQL的使用

  - SQL：开发语言，实现数据的存储以及分析管理



## 二、MySQL及DataGrip部署

### 1、MySQL安装

- 参考MySQL安装文档实现安装

### 2、DataGrip的安装

- 功能：使用图形化界面的方式来操作MySQL，进行数据的管理
- 参考DataGrip安装文档实现安装

### 3、DataGrip连接MySQL

- 创建一个连接，配置连接MySQL即可

  - MySQL所在机器的地址和端口

    - 地址：localhost
    - 端口：3306

  - MySQL的连接驱动

    - 下载

  - MySQL用户名和密码

    ```
    用户名：root
    密码：123456
    ```

  - MySQL连接地址属性

    ```
    jdbc:mysql://localhost:3306?serverTimezone=UTC
    ```

- 参考视频或者课件中的图片实现连接



## 三、SQL介绍及其规则

### 1、SQL的介绍

- Struct Qurey Language：结构化查询语言

- 一种编程语言，是一种命令，通过这种命令或者编程语言开发程序来实现数据处理

  - MySQL使用SQL命令来管理MySQL中数据

- SQL是所有RDBMS【关系型数据库管理系统】通用语言

  - 在语法上有一点点区别

    

### 2、SQL的分类

- MySQL中的SQL根据不同的功能模块划分不同的命令的分类

- DDL：数据定义语言

  - 如何管理我们的数据库和表
  - 数据库的管理：创建、删除、切换
    - 学生信息数据库
  - 表的管理：创建、删除、清空、描述
    - 学生表
    - 成绩表
    - 学籍表

- DML：数据操作语言

  - 如何管理表中的数据
  - 对表中数据实现以下功能
    - 插入：insert
    - 更改：update
    - 删除：delete
  - 例如
    - 录入学生信息
    - 更改学生信息
    - 删除学生信息

- DQL：数据查询语言

  - 实现对表中数据的查询和统计分析

  - 我们在工作中60%的开发都是开发SQL，有90%都是在开发DQL

  - select

    

### 3、SQL的规则

- 所有的SQL语句都需要以分号来作为结束符，表示这条命令结束了，可以提交运行

  ```sql
  show databases;
  show tables;
  select * from mysql.user;
  ```

  

## 四、SQL分析之DDL

### 1、数据库管理

- 创建

  - 功能：构建一个新的数据库

  - 语法

    ```sql
    create database [ if not exists ] 数据库的名字;
    ```

  - 测试

    - 创建一个新的数据库叫做：itcast01

      ```sql
      create database itcast01;
      ```

      ![image-20200626202110922](Day01：数据库管理系统MySQL.assets/image-20200626202110922.png)

    - 创建一个新的数据库：itcast02

      ```sql
      create database if not exists itcast02;
      ```

      ![image-20200626202312950](Day01：数据库管理系统MySQL.assets/image-20200626202312950.png)

    - if not exists：如果不存在的情况下，就创建，如果已经存在就不会创建

      - 功能：为了避免程序报错

      - 如果不加：数据库已存在，就会报错

      - 如果加了：数据库已存在，不会报错

        ![image-20200626202616343](Day01：数据库管理系统MySQL.assets/image-20200626202616343.png)

        

- 列举

  - 功能：用于列举当前MySQL中所有的数据库名称

  - 语法

    ```sql
    show  databases;
    ```

  - 测试

    ![image-20200626201927898](Day01：数据库管理系统MySQL.assets/image-20200626201927898.png)

- 查看

  - 功能：查看当前所在的数据库

  - 语法

    ```sql
    select database();
    ```

  - 测试

    ![image-20200626202921195](Day01：数据库管理系统MySQL.assets/image-20200626202921195.png)

    - null表示我们当前不在任何一个数据库中

- 切换

  - 功能：切换到某个数据库中

  - 语法

    ```
    use 数据库名称;
    ```

  - 测试

    - 切换到itcast01这个数据库中

      ```sql
      use itcast01;
      ```

      ![image-20200626203115436](Day01：数据库管理系统MySQL.assets/image-20200626203115436.png)

    - 切换到itcast02这个数据库中

      ```sql
      use itcast02;
      ```

      ![image-20200626203205537](Day01：数据库管理系统MySQL.assets/image-20200626203205537.png)

      

- 删除

  - 功能：删除已存在的一个数据库

  - 语法

    ```sql
    drop database [ if exists ] 数据库名称;
    ```

  - 测试

    - 删除itcast01这个数据库

      ```sql
      drop  database itcast01;
      ```

      ![image-20200626203451258](Day01：数据库管理系统MySQL.assets/image-20200626203451258.png)

    - if exists ：如果存在，就删除，如果不存在就不删除

      - 功能：为了避免程序报错

      - 如果不加：数据库不存在，删除就会报错

      - 如果加了：数据库不存在，删除不会报错

        ![image-20200626203741535](Day01：数据库管理系统MySQL.assets/image-20200626203741535.png)

        

### 2、数据表管理

- 数据类型

  - 定义：用于描述表中列的一个数据格式

  - 类型：

    - 字符类型：中文、英文或者比较长的数字、日期都可以使用字符串来存储

      - 字符类型是万能的类型

        ```
        'a'：这就是一个字符，一个数字、一个英文字母、一个符号
        'abc,12344'：这就是一个字符串，很多个字符构成一个整体
        ```

        - 字符串表示的数字是不能参与计算的

      - ==只要是字符类型，就使用varchar（N）==

        - N表示字符串的长度，只能大不能小
        - 手机号码：varchar（11）
          - varchar（20）：可以
          - varchar(10)：不可以

    - 数字类型

      - 整数
        - 整形：int
        - ==只要是整数就用：int==
      - 小数
        - 单精度：float
        - 双精度：double
        - ==只要是小数就用：double==

    - 日期类型

      - 日期是一种特殊的格式
      - ==date：用于存储年月日==
        - yyyy-MM-dd
        - 2020-01-01
      - ==datetime：用于存储年月日，时分秒==
        - yyyy-MM-dd HH:mm:ss
        - 2020-01-01 12:30:50

- 创建

  - 功能：在某个数据库中创建一张，定义表的结构【表中哪些列以及每一列的类型】

  - 语法

    ```
    create table [if not exists] [数据库名称.]表的名称(
       col1 type1,
       col2 type2,
       col3 type3,
       ……
       colN typeN
    );
    ```

    - 注意事项
      - 所有的符号都是英文的，不允许出现中文符号
      - 除了最后一行就是结尾括号的前一号不用加逗号，其他的都要加逗号
      - 每一列都要指定对应的类型
        - 字符串：varchar(N)
        - 整数：int
        - 小数：double
        - 年月日日期：date
        - 年月日时分秒：datetime
      - 如果不加数据库名称，表示在当前数据库中创建表

  - 测试

    - 创建一张学生表student：学生学号、学生姓名、学生年龄、学生性别

      ```
      create table if not exists student(
         stuid varchar(10),
         stuname varchar(10),
         age int,
         sex varchar(2)
      );
      ```

      ![image-20200626211200711](Day01：数据库管理系统MySQL.assets/image-20200626211200711.png)

      

- 列举

  - 功能：列举当前数据库中所有的表

  - 语法

    ```
    show tables;
    ```

  - 测试

    ![image-20200626210834791](Day01：数据库管理系统MySQL.assets/image-20200626210834791.png)

    ​	![image-20200629210140287](Day01：数据库管理系统MySQL.assets/image-20200629210140287.png)

    

- 描述

  - 功能：查看一张表的详细的结构信息

  - 语法：

    ```
    desc  [dbname.]tbname;
    ```

  - 测试

    ```
    desc student;
    desc bigdata.student;
    ```

    ![image-20200629210418658](Day01：数据库管理系统MySQL.assets/image-20200629210418658.png)

    

- 删除

  - 功能：删除一张不需要再使用的表

  - 语法

    ```
    drop table [ if exists ] [dbname.]tbname;
    ```

  - 测试

    ```
    drop table if exists student;
    ```

    ![image-20200629211104002](Day01：数据库管理系统MySQL.assets/image-20200629211104002.png)

    

## 五、SQL分析之DML

### 1、创建表格

- 创建一个商品的分类表：category

  - 分类编号：cid
  - 分类名称：cname

- 创建语句

  ```
  create table category(
    cid varchar(5),
    cname varchar(10)
  );
  ```

  ![image-20200629212641728](Day01：数据库管理系统MySQL.assets/image-20200629212641728.png)

  

### 2、插入数据

- 功能：写入一条数据进入数据表

- 关键字：insert

- 语法

  ```
  insert into tbname(co11,col2,col3……)  values(value1,value2,value3……);
  ```

- 测试

  ```
  insert into category(cid,cname) values('c001','电器');
  insert into category(cname) values('服饰');
  insert into category(cid,cname) values(null,'化妆品');
  insert into category values('c002','书籍');
  insert into category values(null,'蔬菜');
  ```

  ![image-20200629213403110](Day01：数据库管理系统MySQL.assets/image-20200629213403110.png)

  ![image-20200629214132789](Day01：数据库管理系统MySQL.assets/image-20200629214132789.png)

  

  - 查询某张表的所有内容

    ```
    select * from category;
    ```

  - ==注意事项==

    - 所给定的列的名称必须与后面的值一一对应
    - 给定值的时候，除了数值类型或者null，其他类型必须加上单引号
    - 给定的值不能超过创建表时定义的长度
    - 如果要给表中的每一列都赋值，就可以不写列名

### 3、更新数据

- 功能：修改数据表中的数据

- 关键字：update

- 语法

  ```
  update 表的名称 set col1 = newValue,col2 = newValue …… [where 条件];
  ```

- 测试

  - 需求1：将服饰的分类id更改为c003

    ```
    update  category set  cid = 'c003';
    ```

    ![image-20200629215253675](Day01：数据库管理系统MySQL.assets/image-20200629215253675.png)

    - 上面不能满足我们的需求，因为更改了其他不需要更改的数据
    - 解决：加上where 条件
      - 只有满足where条件的数据才会被更改
      - 没有指定where条件，就更改所有数据

  - 需求2：将服饰的分类id更改为c004

    ```
    update category set cid = 'c004' where cname = '服饰';
    ```

    ![image-20200629215715473](Day01：数据库管理系统MySQL.assets/image-20200629215715473.png)

  - 需求3：将化妆品的分类id更改为c001，并且将分类名称更改为化妆

    ```
    update category set cid='c001',cname='化妆' where cname = '化妆品';
    ```

    ![image-20200629215920737](Day01：数据库管理系统MySQL.assets/image-20200629215920737.png)

  - 需求4：将所有 c003的分类名称更改为笔记本

    ```
    update category set cname = '笔记本' where cid = 'c003';
    ```

    ![image-20200629220038167](Day01：数据库管理系统MySQL.assets/image-20200629220038167.png)

  - ==注意：==

    - 更改的列的新的值必须与列的类型相符
    - 新的值不能超过这一列的长度

  

### 4、删除数据

- 功能：删除数据表中的数据

- 关键字：delete

- 语法

  ```
  delete from 表的名称  [where 条件];
  ```

  - 如果不加where条件，会删除整张表所有的数据

  - where 条件：符合条件的数据将会被删除

  - 需求1：删除所有分类名称为笔记本的分类数据

    ```
    delete from category where cname = '笔记本';
    ```

    ![image-20200629221111664](Day01：数据库管理系统MySQL.assets/image-20200629221111664.png)

  - 需求2：删除分类id不为c001的分类的数据

    ```
    delete from category where cid != 'c001';
    ```

- 清空表中所有的数据

  - delete：用于删除表中的数据，一行一行删除

    ```
    delete from category;
    ```

  - truncate：用于清空整张表的数据

    ```
    truncate category;
    ```

    ![image-20200629221411664](Day01：数据库管理系统MySQL.assets/image-20200629221411664.png)

  - 区别

    - delete：DML命令，一条一条删除
    - truncate：DDL命令，类似于将整张表删除，然后重新创建一张一样的空表





## 六、SQL分析之DQL

### 1、准备数据

- 创建测试数据库

  ```SQL
  drop database if exists bigdata;
  create database bigdata;
  use bigdata;
  ```

- 创建商品表

  ```sql
  create table product(
   pid int,
   pname varchar(20),
   price double,
   category_id varchar(32)
  );
  ```

- 插入商品测试数据

  ```sql
  INSERT INTO product(pid,pname,price,category_id) VALUES(1,'联想',5000,'c001');
  INSERT INTO product(pid,pname,price,category_id) VALUES(2,'海尔',3000,'c001');
  INSERT INTO product(pid,pname,price,category_id) VALUES(3,'雷神',5000,'c001');
  INSERT INTO product(pid,pname,price,category_id) VALUES(4,'杰克琼斯',800,'c002');
  INSERT INTO product(pid,pname,price,category_id) VALUES(5,'真维斯',200,'c002');
  INSERT INTO product(pid,pname,price,category_id) VALUES(6,'花花公子',440,'c002');
  INSERT INTO product(pid,pname,price,category_id) VALUES(7,'劲霸',2000,'c002');
  INSERT INTO product(pid,pname,price,category_id) VALUES(8,'香奈儿',800,'c003');
  INSERT INTO product(pid,pname,price,category_id) VALUES(9,'相宜本草',200,'c003');
  INSERT INTO product(pid,pname,price,category_id) VALUES(10,'面霸',5,'c003');
  INSERT INTO product(pid,pname,price,category_id) VALUES(11,'好想你枣',56,'c004');
  INSERT INTO product(pid,pname,price,category_id) VALUES(12,'香飘飘奶茶',1,'c005');
  INSERT INTO product(pid,pname,price,category_id) VALUES(13,'海澜之家',1,'c002');
  ```

- 创建商品分类类：categroy

  ```SQL
  create table category(
    category_id varchar(10),
    category_name varchar(100)
  );
  ```

- 插入商品分类测试数据

  ```sql
  insert into category values('c001','电脑');
  insert into category values('c002','服装');
  insert into category values('c003','化妆品');
  insert into category values('c004','吃的');
  insert into category values('c005','喝的');
  ```

  

### 2、基本语法

- 功能：实现对于数据表中的数据的查询、统计分析、处理

- 关键字：select

- 语法

  ```SQL
  select 1 from 2 where 3 group by 4 having 5 order by 6 limit 7;
  ```

  - 1：用于决定查询的结果中有哪些列，给定哪些列，结果就会显示这些列

    - 写列的名字，多列用逗号隔开
    - *号代表所有的列

  - 2：用于表示查询哪张表，给定表的名字

  - 3：条件查询，只有满足条件的数据才会被返回

    - 不满足条件的数据会被过滤掉，不会在结果中显示
    - 符合where条件的行才会在结果中显示

  - 4：用于实现分组的，将多条数据按照某一列或者多列进行分组，划分到同一组中

    - 用于实现统计分析
    - 语法：group by col

  - 5：用于实现分组后的条件过滤

    - 功能类似于where
    - 满足having后的条件就会出现在结果中
    - 不满足条件就会被过滤掉
    - 与where的区别
      - where：分组之前过滤
      - having：分组之后过滤

  - 6：用于实现将查询的结果按照某一列或者多列进行排序

    - order by col  [ asc | desc]
    - asc：升序排序
    - desc：降序排序
    - 如果不指定，默认是升序排序

  - 7：用于实现分页输出

    

### 3、简单查询

- 查询所有的商品信息

  ```
  select * from product;
  ```

  ![image-20200702152955689](Day01：数据库管理系统MySQL.assets/image-20200702152955689.png)

  

- 查询所有的商品名称和价格

  ```
  select pname,price from product;
  ```

  ![image-20200702153232051](Day01：数据库管理系统MySQL.assets/image-20200702153232051.png)

  

- 查询所有的商品名称和价格，结果的列的名称分别为商品和价格

  ```
  select pname as '商品', price as '价格' from product;
  ```

  ![image-20200702153554316](Day01：数据库管理系统MySQL.assets/image-20200702153554316.png)

  - as：用于给列或者表取别名

  

- 查询所有商品的价格，并去掉重复价格

  - 查询所有商品价格

  ![image-20200702153803436](Day01：数据库管理系统MySQL.assets/image-20200702153803436.png)

  - 去掉重复价格

    ```
    select distinct price from product;
    ```

    ![image-20200702153930200](Day01：数据库管理系统MySQL.assets/image-20200702153930200.png)

  - distinct：用于对列值进行去重

    

- 将所有商品的价格+10元显示

  ```
  select price as '价格' , price + 10 as '新价格' from product;
  ```
  
  ![image-20200702154219464](Day01：数据库管理系统MySQL.assets/image-20200702154219464.png)
  
  - 直接对数值类型的列进行运算
    - 加：+
    - 减：-
    - 乘：*
    - 除：/



### 4、条件查询：where

- 功能：对于数据行的过滤

- 查询商品名称为“花花公子”的商品所有信息 

  ```
  select * from product where pname = '花花公子';
  ```

  ![image-20200702155631783](Day01：数据库管理系统MySQL.assets/image-20200702155631783.png)

  

- 查询价格为800商品  

  ```
  select * from product where price = 800;
  ```

  ![image-20200702155805675](Day01：数据库管理系统MySQL.assets/image-20200702155805675.png)

  

- 查询价格不是800的所有商品

  ```
  select * from  product where  price != 800;
  ```

  ![image-20200702160012180](Day01：数据库管理系统MySQL.assets/image-20200702160012180.png)

  

- 查询商品价格大于60元的所有商品信息

  ```
  select * from product where price > 60;
  ```

  ![image-20200702160137164](Day01：数据库管理系统MySQL.assets/image-20200702160137164.png)

  - 等于：=

  - 不等于：！=

  - 小于：<

  - 大于：>

  - 小于等于：<=

  - 大于等于：>=

    

- 查询商品价格在200到1000之间所有商品

  ```
  select * from product where price >= 200 and price <= 1000;
  select * from product where price between 200 and 1000;
  ```

  ![image-20200702160548070](Day01：数据库管理系统MySQL.assets/image-20200702160548070.png)

  - and：并列关系，两个条件都要满足

    

- 查询商品价格是200或800的所有商品

  ```
  select * from product where price = 200 or price = 800;
  ```

  ![image-20200702160828528](Day01：数据库管理系统MySQL.assets/image-20200702160828528.png)

  - or：或者关系，两个条件满足其中一个即可

    

- 查询含有'霸'字的所有商品

  ```
  select * from product where pname like '%霸%';
  ```

  ![image-20200702161145607](Day01：数据库管理系统MySQL.assets/image-20200702161145607.png)

  - %：任意多个字符

    

- 查询以'香'开头的所有商品

  ```
  select * from product where pname like '香%';
  ```

  ![image-20200702161427047](Day01：数据库管理系统MySQL.assets/image-20200702161427047.png)

  

- 查询第二个字为'想'的所有商品

  ```
  select * from  product where pname like '_想%';
  ```

  ![image-20200702161702350](Day01：数据库管理系统MySQL.assets/image-20200702161702350.png)

  - _：表示一个字符

    

- 查询没有分类的商品

  ```
  insert into product values(14,'weiC 100',9.9,null);
  ```

  ![image-20200702162050786](Day01：数据库管理系统MySQL.assets/image-20200702162050786.png)

  ```
  select * from product where category_id is null;
  ```

  ![image-20200702162218157](Day01：数据库管理系统MySQL.assets/image-20200702162218157.png)

  

- 查询有分类的商品

  ```
  select * from product where category_id is not null;
  ```

  ![image-20200702162327329](Day01：数据库管理系统MySQL.assets/image-20200702162327329.png)

  

### 5、聚合查询

- 聚合函数
  - 函数：MySQL为你定义好的功能，你只要调用这个命令就可以实现聚合功能
  - MYSQL默认为我们提供的常见的聚合函数
    - count(colname)：统计某一列的行数，统计个数，null不参与统计
    - sum（colname）：计算某一列的所有值的和，只能对数值类型求和，如果不是数值，结果为0
    - max（colname）：计算某一列的所有值中的最大值
    - min（colname）：计算某一列的所有值中的最小值
    - avg（colname）：计算某一列的平均值

- 查询商品的总条数 

  ```
  select count(pid) as '总个数' from product;
  ```

  ![image-20200702201119336](Day01：数据库管理系统MySQL.assets/image-20200702201119336.png)

  

- 查询价格大于200商品的总条数 

  ```
  select count(pid) as '大于200的商品个数' from product where price > 200;
  ```

  ![image-20200702201447950](Day01：数据库管理系统MySQL.assets/image-20200702201447950.png)

  

- 查询分类为'c001'的所有商品价格的总和  

  ```
  select sum(price) as totalPrice from product where category_id = 'c001';
  ```

  ![image-20200702201649601](Day01：数据库管理系统MySQL.assets/image-20200702201649601.png)

  

- 查询分类为'c002'所有商品的平均价格 

  ```
  select avg(price) as '平均价格' from product where category_id = 'c002';
  ```

  ![image-20200702201929937](Day01：数据库管理系统MySQL.assets/image-20200702201929937.png)

  

- 查询商品的最大价格和最小价格  

  ```
  select max(price) as '最大价格',min(price) as '最小价格' from product;
  ```
  
  ![image-20200702202344072](Day01：数据库管理系统MySQL.assets/image-20200702202344072.png)
  
  
  
  

### 6、分组查询：gourp by

- 关键字：group by col …… having
- 功能：按照某些列进行分组，对分组后的数据进行处理，一般都会搭配聚合函数使用

- 统计各个分类商品的个数  

  - 分析过程

    - 结果长什么样？

      ```
      category_id			个数
      c001				3
      c002				5
      c003				3
      c004				2
      c005				1
      ```

    - 按照什么分组？

      - 按照category_id进行分组

    - 统计每组商品的个数

      - count

  ```
  select category_id,count(*) as '个数' from product group by category_id;
  ```

  ![image-20200702203429283](Day01：数据库管理系统MySQL.assets/image-20200702203429283.png)

- 统计查询每种分类中的商品的最大价格和最小价格

  - 分析
    - 结果长什么样？
      - 三列：分类的id		最大价格			最小价格
    - 按照分类的id进行分组
    - 统计每个分组内部的最大价格和最小价格

  ```
  select  
      category_id,
      max(price) as maxprice,
      min(price) as minprice   
  from 
      product  
  group by 
      category_id;
  ```

  ![image-20200702203945489](Day01：数据库管理系统MySQL.assets/image-20200702203945489.png)

  

- 统计各个分类商品的个数,且只显示个数大于1的数据

  ```
  select category_id,count(*) as '个数' from product group by category_id;
  ```
  
  - 需要对分组后的结果再进行行的过滤
  - where：实现对数据行的过滤，指定条件
    - 这个需求中不能使用where
    - 因为where会在group by之前执行，而个数是在分组之后才产生的列
  - having：实现对数据行的过滤，指定条件，写法与where一致
    - 用于分组之后结果数据的过滤
    - 对分组以后的 结果进行过滤
  - 什么时候用where，什么时候用having
    - 你要过滤的条件是分组之前就存在的，还是分组以后才产生的
  
  ```
  select category_id,count(*) as '个数' from product group by category_id having count(*) > 1;
  ```
  
  ![image-20200702204613303](Day01：数据库管理系统MySQL.assets/image-20200702204613303.png)
  
  

### 7、排序查询：order by

- 关键字：order by col…… 【 asc | desc】
- 功能：将结果按照某些列进行升序或者 降序的排序来显示
  - 默认是升序
  - asc：升序
  - desc：降序
- 

- 查询所有商品的信息，并按照价格降序排序

  ```
  select * from product order by  price desc;
  ```

  ![image-20200702205645391](Day01：数据库管理系统MySQL.assets/image-20200702205645391.png)

  

- 查询所有商品的信息，并按照价格排序(降序)，如果价格相同，以分类排序(降序)

  ```
  select * from product order by price desc,category_id desc;
  ```

  ![image-20200702205923524](Day01：数据库管理系统MySQL.assets/image-20200702205923524.png)

  

- 统计各个分类商品的个数 ，并按照个数降序排序

  ```sql
  select category_id,count(*) as '个数' from product group by category_id;
  ```
  
  ![image-20200702210133787](Day01：数据库管理系统MySQL.assets/image-20200702210133787.png)
  
  ```sql
  select category_id,count(*) as '个数' from product group by category_id order by count(*) desc;
  ```
  
  ![image-20200702210257846](Day01：数据库管理系统MySQL.assets/image-20200702210257846.png)
  
  ![image-20200702210324695](Day01：数据库管理系统MySQL.assets/image-20200702210324695.png)
  
  

### 8、分页查询：limit

- 关键字：limit
- 功能：限制输出的结果
- 语法：limit M,N
  - M：你想从第M+1条开始显示
  - N：显示N条
  - 显示第一条到第三条
    - M：0
    - N：3
  - 显示第9条到第10条
    - M：8
    - N：2
  - 如果从第一条开始，M为0，可以省略不写
    - limit N

- 查询product表的前5条记录

  ```sql
  select * from product limit 0,5;
  select * from product limit 5;
  ```

  ![image-20200702211351033](Day01：数据库管理系统MySQL.assets/image-20200702211351033.png)

  

- 查询product表的第4条和第5条记录

  ```sql
  select * from product limit 3,2;
  ```
  
    ![image-20200702211507141](Day01：数据库管理系统MySQL.assets/image-20200702211507141.png)
  
  
  
- 查询商品个数最多的分类的前三名

  - 查询所有商品分类的商品个数
  
    ```sql
    select category_id,count(*) as numb  from product group by category_id;
    ```
  
  - 对上一步做排序
  
    ```sql
    select category_id,count(*) as numb  from product group by category_id order by numb desc;
    ```
  
  - limit选择前三名
  
    ```sql
    select category_id,count(*) as numb  from product group by category_id order by numb desc limit 3;
    ```
  
    ![image-20200702211811837](Day01：数据库管理系统MySQL.assets/image-20200702211811837.png)
  
    
  
  

### 9、结果保存

- 语法

  ```
  insert into 表的名称   select……
  ```

- 功能：将一条select语句运行的结果写入一张表中

- 注意：结果表的列一定要与Select语句的结果的列要匹配

  - 列的名称可以不一样
  - 但是列的类型和个数必须一一对应

- 统计各个分类商品的个数 ，并按照个数降序排序，并将结果进行保存

  ```sql
  select
    category_id,
    count(*) as numb
  from
    product
  group by
    category_id
  order by
    numb desc;
  ```

  ![image-20200702213032264](Day01：数据库管理系统MySQL.assets/image-20200702213032264.png)

  ```sql
  --创建一张表用于存储分析的结果
  create table result (
    cid varchar(100),
    numb int
  );
  ```

  ![image-20200702213133496](Day01：数据库管理系统MySQL.assets/image-20200702213133496.png)

  ```sql
  --将分析的结果存储在这张表中
  insert into result
  select
    category_id,
    count(*) as numb
  from
    product
  group by
    category_id
  order by
    numb desc;
  ```

  ![image-20200702213315008](Day01：数据库管理系统MySQL.assets/image-20200702213315008.png)

  





## 七、多表关系与查询

### 1、多表关系

- 电商数据库
  - 用户表
    - 用户id、用户名称、用户手机……
  - 商品表
    - 商品id、商品名称、商品价格、库存、尺寸……
  - 订单表
    - 订单id、用户id、商品id、总金额、支付方式
- 员工数据库
  - 员工表
    - 员工id、员工姓名、员工性别、年龄、部门id……
  - 部门表
    - 部门id、部门名称、部门位置、部门领导……
  - 员工和部门之间的关系
    - 员工属于某一个部门

![image-20200702220547447](Day01：数据库管理系统MySQL.assets/image-20200702220547447.png)

- 表与表之间通过某些列来实现关联，表现数据之间的关系

  

### 2、join

- 功能：通过两张表之间关联的列，实现将两张表的列进行合并

- 关键字：A    join B   on  条件

- 语法

  ```
  select 查询的两张表的哪些列  from A表  join  B表  on 关联条件;
  ```

- 本质：通过某种列的关系，将两张表的列进行了关联

- 需求1：查询每个商品的名称以及所属分类的名称

  - 分析结果长什么样？

    ```
    商品名称			分类名称
    联想					电脑
    ……
    weiC 100			 吃的
    ```

  - 问题：商品名称 属于商品表，分类名称属于分类表

  - 关系：分类id：categor_id

  - 查询

    ```sql
    --将商品表与分类表通过分类id进行关联，并显示两张表的所有列
    select
       a.*,
       b.*
    from
       product as a join category as b on a.category_id = b.category_id;
    ```

    ![image-20200702222803025](Day01：数据库管理系统MySQL.assets/image-20200702222803025.png)

    ```sql
    select
      a.pname,
      b.category_name
    from
      product a join category b on a.category_id = b.category_id;
    ```

    ![image-20200702223043014](Day01：数据库管理系统MySQL.assets/image-20200702223043014.png)

    

- 需求2：统计每个分类名称对应的商品个数

  ```sql
  select
    b.category_name,
    count(*) as numb
  from
    product a join category b on a.category_id = b.category_id
  group by
    b.category_name;
  ```

  ![image-20200702223505148](Day01：数据库管理系统MySQL.assets/image-20200702223505148.png)

  

- 需求3：统计除了吃的分类以外的所有分类的商品个数，并显示个数最多的前三个分类

  ```sql
  select 
     b.category_name,
     count(*) as numb
  from 
     product a join category b on a.category_id = b.category_id
  where
     b.category_name != '吃的'
  group by
     b.category_name
  order by
     numb desc
  limit 3;
  ```

  ![image-20200702224023108](Day01：数据库管理系统MySQL.assets/image-20200702224023108.png)

  

- 分类

  - inner join：内连接，inner可以省略

    - 关联条件中，两张表都有这个值，结果就有
    - 类似于集合中两个集合的交集

  - left outer join：左外连接，outer可以省略

    - 关联条件中，左表中有，结果就有

    - 类似于集合中左表的全集

      ```
      select
        a.pname,
        b.category_name
      from
        product a left join category b on a.category_id = b.category_id;
      ```

      - 左表是product，右表是category
      - 如果product表中有一条数据的category_id是c006，而category中没有
      - 结果有

  - right   outer join：右外连接，outer可以省略

    - 关联条件中，右表中有，结果就有

    - 类似于集合中右表的全集

      ```
      select
        a.pname,
        b.category_name
      from
        product a right join category b on a.category_id = b.category_id;
      ```

      - 左表是product，右表是category
      - 如果category表中有一条数据的category_id是c006，而product中没有
      - 结果有

  - full   join：全连接

    - 关联条件中，两张表任意一边有，结果就有
    - 类似于集合中的两张表全集

  





### 3、子查询

- 功能：在select语句中嵌套select语句

- 需求1：查询化妆品这个分类对应的所有商品信息

  - 分析结果长什么样？
    - 所有商品信息：product
  - 条件：化妆品这个分类对应的商品
    - 化妆品：category
  - 解决：先获取化妆品对应的分类id，然后根据分类id到商品表中查询这个分类id对应的商品

  ```
  select category_id from category where category_name = '化妆品';
  select * from product where category_id = 'c003';
  ```

  |

  ```
  select * from product where category_id = (select category_id from category where category_name = '化妆品');
  ```

  - 先执行内层的SQL语句
  - 然后执行外层的SQL语句

  ![image-20200702230753367](Day01：数据库管理系统MySQL.assets/image-20200702230753367.png)

  

- 需求2：查询相宜本草对应的分类的名称

  - 结果：显示分类的 名称：category
  - 条件：相宜本草  pname：product

  ```
  --先查询相宜本草对应的分类id
  select category_id from product where pname = '相宜本草';
  --根据分类id到分类表中查询分类的名称
  select category_name from category where category_id = 'c003';
  |
  select category_name from category where category_id = (select category_id from product where pname = '相宜本草');
  ```

  ![image-20200702231153230](Day01：数据库管理系统MySQL.assets/image-20200702231153230.png)

- join与子查询的应用场景

  - 如果你的查询结果包含多张表的列
    - join
  - 如果你的查询结果只有一张表的列，条件来自于别的表
    - 子查询















