## group by分组函数

格式：

```plsql
GROUP BY COL1,COL2,... [HAVING CONDITIONS]
以 GROUP BY后的字段作为分组条件,将值相同的放在一个分组
HAVING后跟聚合函数: AVG(),COUNT(),SUM(),MIN(),MAX()等
```

```PLSQL
SELECT COL1,COL2 FROM TABLE1 WHERE CONDITIONS GROUP BY COL1,COL2 HAVING CONDITIONS
```

- 示例

  ```plsql
  SELECT XH,KCH FROM KCXX [WHERE CONDITIONS] GROUP BY XH,KCH HAVING COUNT(1) > 1  --查找分组重复的
  SELECT XH,KCH,MIN(XM) FROM KCXX GROUP BY XH,KCH 
  ```

  