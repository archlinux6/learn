查询无上司（report_to不确定）的员工信息，输出员工号、员工姓名、职位。
```sql
SELECT employee_id, employee_name, job_title 
FROM employee 
WHERE report_to IS NULL;

```