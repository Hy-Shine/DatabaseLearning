## Oracle触发器用法

### 1 触发器简介

- 定义：某个条件成立的时候，触发器里面所定义的语句就会被自动的执行。因此，触发器不需要人为的去调用，也不能调用。

- 分类：DML触发器、替代（`instead of`）触发器、系统事件触发器

  ```sql
  DML触发器：对数据表进行DML语句操作（如insert、update、delete），又分为：语句级和行级
  语句级触发器可以在某些语句执行前或执行后被触发。
  行级触发器则是在定义的了触发的表中的行数据改变时就会被触发一次。
  ```

### 2 实现过程

#### 2.1 DML触发器

- 语法结构

  ```sql
  create [or replace] trigger trigger_name
  before|after trigger_event
  on table_name
  [for each row]
  begin
  	pl/sql语句  --触发体，是标准的PL/SQL语句块
  end;
  解释：
  before|after:指定触发器是在触发事件发生之前触发，触发事件发生之后触发
  trigger_event：触发事件，在DML触发器中主要为insert、update、delete等
  for each row：指定创建的是行级触发器，若没有该子句则创建的是语句级触发器
  ```

#### 2.2 替代触发器

对视图进行操作时定义的触发器，替代触发器只能定义在视图上。

- 语法结构

  ```sql 
  create [or replace] trigger trigger_name --触发器名称
  instead of trigger_event --触发事件
  on view_name --视图名称
  for each row  --替代触发器必须指定为行级的触发器
  [when trigger_condition] --触发条件
  trigger_body --触发体，PL/SQL块
  ```

#### 2.3 系统事件触发器

对数据库实例或某个用户模式进行操作时定义的触发器，可以分为：**数据库系统触发器**和**用户触发器**