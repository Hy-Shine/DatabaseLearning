## EXISTS - IN

- 结果返回单字段

  ```plsql
  --IN 
  SELECT * FROM TABLE1 
  WHERE ID IN (SELECT ID FROM TABLE2 WHERE CONDITION 
  --EXISTS 
  SELECT * FROM TABLE1 A 
  WHERE EXISTS (SELECT * FROM TABLE2 B WHERE join_condition and other_conditions)
  ```

- 结果返回多字段

  ```plsql
  --IN
  SELECT * FROM TABLE1 
  	WHERE (ID,XM) IN (SELECT ID,XM FROM TABLE2 CONDITION)
--EXISTS
  SELECT * FROM TABLE1 A 
  	WHERE EXISTS (SELECT * FROM TABLE2 B WHERE A.ID = B.XM AND A.XM = B.XM)
  ```
  
  ```PLSQL
  NOT IN 与 NOT EXISTS的用法同上
  ```
  
  - 应用场景
  
    ```plsql
    EXISTS : TABLE2 > TABLE1
    IN : TABLE2 < TABLE1
    EXISTS 或 IN : TABLE1 ~ TABLE2
    在任何情况下, NOT IN 的效率都低于 NOT EXISTS
    ```
  
    