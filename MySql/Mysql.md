创建数据库   CREATE DATABASE 库名<br>
删除数据库   DROP  DARABASE 库名<br>
创建表       CREATE TABLE 表名 
（ 列名（id）  数据类型（INT） ）character set 字符集collate 校对规则 engine存储引擎<br>
修改表        ALTER TABLE 表名  ADD/MODIFY (列名 数据类型)<br>
                                DROP 列名<br>
增加数据      INSERT INTO 表名 （字段）VALUES（值）<br>
修改数据      UPDATE 表名 SET ...  WHERE ...  把谁的什么改为什么<br>
删除数据      DELETE FROM 表名 WHERE      删除某条记录<br>
查            SELECT ...  FROM 表名 WHERE 条件<br>
条件         在...之间 WHERE BETWEEN ... AND...（批量删除）   <br>
符合IN里的值 WHERE ...IN（， ，） <br>
模糊查询      WHERE...LIKE ‘  ’  %零到多个  _ 一个字符<br>
升降序         order by..ASC.默认升序，降序DESC<br>
分组          GROUP BY  部门  HAVING 条件      按相同部门分组，每个部门的...<br>
分页查询       SELECT .... LIMIT a,b  从a+1个取，取b个<br>
多表查询
合并查询       两个查询结果合并 UNION ALL  去掉all可以去重<br>
左外连接       SELECT...FROM 表1 left join 表2 on 条件  以左边为基础没有匹配也会显示<br>
自增长         AUTO_INCREMENT 加一条数据就会+1<br>
添加索引        CREATE 索引类型 索引名字 ON 表名（列名）  <br>
                ALTER TABLE 表名 ADD 索引类型 (列名) <br>
索引类型     主键primary key 自动是索引  唯一索引 unique index 普通索引 index<br>
存储引擎      事务安全型 innoDB     访问速度快，不支持外键MyISAM    <br>

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
