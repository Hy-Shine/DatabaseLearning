## VIEW

视图可以理解为数据库中一张虚拟的表，它是通过一张或者多张基表进行关联查询后组成一个虚拟的逻辑表。查询视图，本质上是对表进行关联查询。                                                      

视图本身是不包含任何数据，只是一个查询结果，当基表的数据发生变化时，视图里面的数据也会跟着发生变化。

**视图的分类**：单表视图，多表关联视图，视图中含有子视图。

```plsql
Usage: CREATE [OR REPLACE] VIEW VIEW_NAME AS
	 statement
	 [WITH READ ONLY];
表user_views可以查看当前用户下所有视图创建过程
```

- 创建视图

  ```plsql
  CREATE [OR REPLACE] VIEW view_name AS
  select_statement
  [WITH READ ONLY]
  解释：
  1, OR REPLACE：如果视图已经存在，则替换旧视图。
  2, WITH READ ONLY：默认不填，用户是可以通过视图对基表执行增删改操作，但是有很多在基表上的限制，WITH READ ONLY说明视图是只读视图，不能通过该视图进行增删改操作。
  ```

  ```plsql
  --案例：创建多表关联视图
  create view vw_stuinfo as 
  select a.stuid,--学号
         a.stuname,--学生姓名
         a.age,--年龄
         b.classname,--班级
         b.monitorname,--班长
    from stuinfo a, class b where a.classno = b.classno;
   --利用上面创建的视图查询
  select * from vw_stuinfo  --vw_stuinfo为视图名
  [where column = 'values'];  --可以添加限制条件，视图还可以嵌套
  ```
  
- 删除视图

  ```plsql
  DROP VIEW view_name;
  ```