## WITH AS

```plsql
WITH NAME AS (
	statemnet
)
select * from name 
where ..
```

```plsql
WITH TEST-NAME AS(
SELECT T.*,DENSE_RANK() OVER(PARTITION BY col1,.. ORDER BY cols) rank
    FROM TABLE-NAME
)
SELECT cols FROM TEST-NAME
WHERE RANK = 2
```

