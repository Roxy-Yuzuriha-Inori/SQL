# case函数
分组查询job,并且如果job为1则显示班主任，job为2显示讲师
```sql
select
  (case when job=1 then '班主任'
        when job=2 then '讲师'
        else '其他' end) pos,
  count(*) num
from emp group by job order by num;
```
# if函数
如果gender=1则是男性员工，gender=2为女性员工
```sql
select 
  if(gender = 1,'男性员工','女性员工') name,
  count(*) value
from emp group by gender

```