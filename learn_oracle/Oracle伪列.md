## Oracle伪列

Oracle的伪列是Oracle表在存储的过程中或查询的过程中，表会有一些附加列，称为伪列。伪列就像表中的字段一样，但是表中并不存储。**伪列只能查询，不能增删改。**Oracle的伪列有：rowid、rownum。

### 1   Oracle ROWID

Oracle表中的每一行在数据文件中都有一个物理地址， ROWID 伪列返回的就是该行的**物理地址**。使用 ROWID 可以快速的定位表中的某一行。 ROWID 值可以唯一的标识表中的一行。
通过Oracle select 查询出来的ROWID，返回的就是该行数据的物理地址。

```plsql
--伪列在查询时不显式存在
select t.*,t.rowid from table_name;
select * from table_name where rowid = 'AAAR7fAAEAAAACvAAB';
```

### 2   Oracle ROWNUM

ORACLE ROWNUM表示的Oracle查询结果集的顺序，ROWNUM为每个查询结果集的行标识一个行号，第一行返回1，第二行返回2，依次顺序递增。

ROWNUM 与 ROWID 不同，ROWID 是插入记录时生成，ROWNUM 是**查询数据时**生成。ROWNUM 标识的是查询结果中的行的次序。

```plsql
select t.*,rownum from student t;   --并非t.rownum
```

- ROWNUM经常用来限制查询的结果返回的行数，求前几行或前几名的数据。

  ```plsql
  select t.* from student where rownum < 5 order by xh 
  ```

  

  



