
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
4.修改库存表 - new  

**修改库存表**：
修改入库日期列indate 的数据类型，由字符型改为日期型（date）。

【注意：表名必须小写】

```sql
ALTER TABLE sg
MODIFY indate DATE;
```

5.修改职工表 - new  

修改职工表emp：

增加列：部门编号：dno char(3) ，设置外码约束参照部门表dept的dno，并设置删除和更新均为级联。

【注意：表名必须用小写。】
```sql
alter table emp add dno char(3),
add constraint dno foreign key (dno) references dept(dno) 
on update cascade on delete cascade;
```
6.修改部门表 - new  

修改部门表dept：

添加约束：为部门负责人mgr添加外码约束，参照员工emp表的员工编号列eno：并设置规则为：删除限制，更新级联。

【注意：表名必须用小写。】
```sql
ALTER TABLE dept
ADD FOREIGN KEY (mgr) REFERENCES emp(eno) ON DELETE RESTRICT ON UPDATE CASCADE;

```
7.创建商品价格修改记录表 new  

AUTO_INCREMENT  自动增长

9.修改表结构：修改供应情况表  

为供应情况表spj添加参照完整性约束（无需设置规则，采用默认约束规则）

spj的SNO列参照s表SNO列，采用默认规则；

spj的PNO列参照p表PNO列，设置删除级联；

spj的JNO列参照j表JNO列，设置更新级联；

[可以一条语句或者多条语句]
```sql
ALTER TABLE spj ADD CONSTRAINT spj_sno_fk FOREIGN KEY (SNO) REFERENCES s(SNO);
ALTER TABLE spj ADD CONSTRAINT spj_pno_fk FOREIGN KEY (PNO) REFERENCES p(PNO) ON DELETE CASCADE;
ALTER TABLE spj ADD CONSTRAINT spj_jno_fk FOREIGN KEY (JNO) REFERENCES j(JNO) ON UPDATE CASCADE;
```