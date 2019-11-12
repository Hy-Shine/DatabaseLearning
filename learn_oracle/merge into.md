## merge into

```plsql
MERGE INTO TARGET_TABLE T1
	USING table|view|sub_query T2
		ON (T1.COL1 = T2.COL2)  --两者连接条件
	WHEN MATCHED THEN
	UPDATE 
		SET COL = ... [WHERE CONDITION]
	WHEN NOT MATCHED THEN
	INSERT
		VALUES(COL1,...) [WHERE CONDITION]
```

```plsql
示例:
merge into merge1 t1
      using t_tsjyxx t2
      on (t1.tsbh = t2.tsbh)
      when matched then
        update
        set t1.jyrq=t2.jyrq,t1.ghrq=t2.ghrq,t1.jyrkh=t2.jyrkh,
        t1.jyrxm = '1',t1.tsmc=t2.tsmc||t2.jyrkh||'ABC'
      when not matched then
        insert
          values(t2.tsbh,t2.jyrq,t2.ghrq,t2.jyrkh,t2.jyrxm,t2.tsmc) where substr(t2.tsbh,2,1) = '3'
```

