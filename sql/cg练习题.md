
1.表定义：创建student表

|  列名 | 说明  | 数据类型  | 约束  |
|---|---|---|---|
| SNO  |学号   |CHAR(7)  |主码   |
|  SNAME | 姓名  |  CHAR(10) |  NOT NULL |
| SSEX  | 性别  | 枚举类型  |  取“男”或“女” |
|SAGE   |年龄   |  SMALLINT |  |
|  SDEPT | 所在系  |VARCHAR(20)   |  默认“计算机系”

注：

1、说明不设置（如，列名SNO的“学号”不要定义）。

2、表名使用全小写。

3、不要设置表的存储引擎和字符编码，默认即可。
```sql
CREATE TABLE student(
  SNO CHAR(7) PRIMARY KEY,
  SNAME CHAR(10) NOT NULL,
  SSEX ENUM('男','女'),
  SAGE SMALLINT,
  SDEPT VARCHAR(20) DEFAULT '计算机系'
);
```

2.创建部门表 - new

创建部门表：dept，表结构如下：

1、部门编号：dno  字符型（3） 主码，

2、部门名称：dname 可变字符型（20） 不允许为空，

3、负责人：mgr 字符型（5）外码参照职工表emp的eno，设置删除规则为限制、更新规则为级联。

【注意：注释说明、表的字符编码不设置，表名全小写。】
```sql
 create table dept(
 dno char(3) primary key,
 dname varchar(20) not null,
 mgr char(5) ,
 foreign key (mgr) references emp(eno) on update cascade on delete restrict
 );
 ```
 3.创建库存表 - new
创建库存表sg，表结构如下：

1、仓库编号：SNO    字符型（5） 主码;

2、商品编号：GNO    字符型（6）主码;

3、库存数量：QUANTITY  整型；

4、外码约束：SNO 参照库存表：store的SNO列，设置删除限制，更新级联；

5、外码约束：GNO 参照商品表：goods的GNO列，设置删除限制，更新级联；

【注意表名必须为小写】
```sql
CREATE TABLE sg (
  sno CHAR(5),
  gno CHAR(6),
  quantity INT,
  PRIMARY KEY (sno, gno),
  FOREIGN KEY (sno) REFERENCES store (sno) ON DELETE RESTRICT ON UPDATE CASCADE,
  FOREIGN KEY (gno) REFERENCES goods (gno) ON DELETE RESTRICT ON UPDATE CASCADE
);

```
   