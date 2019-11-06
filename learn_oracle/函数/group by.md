## group by分组函数

格式：

```plsql
group by col,col2,... [having condition]
以 group by后的字段作为分组条件,将值相同的放在一个分组
having后跟聚合函数: avg(),count(),sum(),min(),max()等
```

- 示例

  ```plsql
  SELECT XH,KCH FROM KCXX GROUP BY XH,KCH HAVING COUNT(1) > 1  --查找分组重复的
  SELECT XH,KCH,MIN(XM) FROM KCXX GROUP BY XH,KCH 
  ```

  