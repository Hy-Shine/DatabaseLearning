
##  索引（index）

作用：优化数据库查询的效率，提升数据库的查询性能。

`Oracle`中常见的索引类型：`B-Tree`，`BITMAP`，`函数索引`，`hash索引`，`reverse反向索引`，`分区索引和分区表的全局索引`

- 索引的创建

  ```plsql
  create [unique]|[bitmap] index index_name --UNIQUE表示唯一索引、BITMAP位图索引
  on table_name(column1,column2...|[express])  --express表示函数索引
  [tablespace tab_name] --tablespace表示索引存储的表空间
  [pctfree n1]     --索引块的空闲空间n1
  注释：
  column_name：指定要对哪个列创建索引，也可以对多列创建索引，这种索引称为组合索引。若为函数表达式，则称为函数索引。
  ```
  
- 修改(alter)索引

  ```plsql
  alter index index_old rename to index_new;  --重新命名索引
  alter index index_name coalesce;  --合并索引
  alter index index_name rebuild;  --重新构造
  ```

- 删除(drop)索引

  ```plsql
  drop index index_name;  --删除索引
  ```

- 查询索引状态

  ```plsql
  select t.INDEX_NAME,  --索引名字
         t.index_type,  --索引类型
         t.TABLESPACE_NAME,  --表空间
         t.status,  --状态
         t.UNIQUENESS  --是否唯一索引
    from all_indexes T 
    where  t.INDEX_NAME='index_name';		--index_name为索引名
  ```


