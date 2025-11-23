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