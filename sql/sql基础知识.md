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
  
### 3. 文本字段 vs 数值字段
SQL 使用单引号来环绕文本值（大部分数据库系统也接受双引号）。   
如果是数值字段，请不要使用引号
### 4. 其他
逻辑运算的优先级：  
` ()    not        and         or`
    