# INSERT

- **插入单条记录**

  ```plsql
  INSERT INTO TABLE1(col1,col2,col3,...) VALUES(value1,value2,value3,...);
  ```

- **插入多条记录**

  ```plsql
  ---方法1
  INSERT ALL
      INTO TABLE1(COL1,COL2) VALUES(value1,value2)
      INTO TABLE1(COL2,COL3) VALUES(value3,value4)  --可以与上面有不同字段
  SELECT * FROM DUAL;
  等同于
  INSERT INTO TABLE1(COL1,COL2) VALUES(value1,value2);
  INSERT INTO TABLE1(COL2,COL3) VALUES(value3,value4);
  ---方法2
  INSERT ALL TABLE1(COL1,COL2)
  SELECT 'value1','value2' FROM DUAL UNION ALL
  SELECT 'value3','value4' FROM DUAL UNION ALL
  SELECT 'value5','value6' FROM DUAL ;
  ```

## INSERT ALL

- **无条件插入**

  ```plsql
--分别向table1、table2中插入符合条件的数据，且两张表插入的数据量一致
INSERT ALL 
       INTO TABLE1(COL1,COL2) VALUES(COL1,COL2)    --values里面放的是要插入的字段名
       INTO TABLE2(COL1,COL3,COL4) VALUES(COL1,COL2,COL4)
SELECT COL1,COL2,COL3,COL4 FROM TABLE_NAME [WHERE CONDITION];
  ```

- **有条件插入**

  ```plsql
  --分别向符合条件的表中插入数据
  INSERT ALL
   WHEN CONDITION1 THEN
     INTO TABLE1(COL1,COL2) VALUES(COL1,COL2)  --符合condition和condition1条件的数据
     WHEN CONDITION2 THEN
     INTO TABLE2(COL1,COL3) VALUES(COL1,COL3)  --符合condition和condition2条件的数据
  SELECT COL1,COL2,COL3 FROM TABLE_NAME [WHERE CONDITION];
  ```
  

## INSERT FIRST

```plsql

```



