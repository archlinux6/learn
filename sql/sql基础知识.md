 ### 1. SQL 指结构化查询语言 Structured Query Language。
SQL 对大小写不敏感：SELECT 与 select 是相同的。  

分号是在数据库系统中分隔每条 SQL 语句的标准方法，这样就可以在对服务器的相同请求中执行一条以上的 SQL 语句。  

### 2. SQL 命令
（1）SELECT 语句用于从数据库中选取数据。  
```sql
SELECT column1, column2, ...
FROM table_name;
```
`SELECT *` 选取所有列  

（2）SELECT DISTINCT 语句用于返回唯一不同的值。
```sql
SELECT DISTINCT country FROM Websites;
```
从 "Websites" 表的 "country" 列中选取唯一不同的值。  

（3）WHERE 子句用于过滤记录。
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
```sql
SELECT * FROM Websites WHERE country='CN';
```
从 "Websites" 表中选取国家为 "CN" 的所有网站。
(4) ORDER BY 用于对结果集进行排序
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```
- column1, column2, ...：要排序的字段名称，可以为多个字段。
- ASC：表示按升序排序，默认升序。
- DESC：表示按降序排序。    

(5) INSERT INTO 用于向表中插入新记录  
- 第一种形式无需指定要插入数据的列名，只需提供被插入的值即可：
    ```sql
    INSERT INTO table_name
    VALUES (value1,value2,value3,...);  
    ```
- 第二种形式需要指定列名及被插入的值：

    ```sql
    INSERT INTO table_name (column1,column2,column3,...)
    VALUES (value1,value2,value3,...);
    ```
 (6)  UPDATE 用于更新表中已存在的记录

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
 (n) 其他  
Not:非 满足不包含该条件的值。
```sql
select * from emp where not sal > 1500;
```  
查询EMP表中 sal 小于等于 1500 的值。  

空值判断： is null
```sql
select * from emp where comm is null;
```  
查询 emp 表中 comm 列中的空值。  

In
```sql
select * from emp where sal in (5000,3000,1500);
```
查询 EMP 表 SAL 列中等于 5000，3000，1500 的值。 


Like模糊查询
```sql
select * from emp where ename like 'M%';
```
- % 表示多个字值  
- _ 下划线表示一个字符
- M% : 正则表达式，表示的意思为模糊查询信息为 M 开头的
- %M% : 表示查询包含M的所有内容。 
- %M_ : 表示查询以M在倒数第二位的所有内容。
### 3. 文本字段 vs 数值字段
SQL 使用单引号来环绕文本值（大部分数据库系统也接受双引号）。   
如果是数值字段，请不要使用引号
### 4. 其他
逻辑运算的优先级：  
` ()    not        and         or`
