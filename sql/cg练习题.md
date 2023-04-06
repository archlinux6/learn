
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