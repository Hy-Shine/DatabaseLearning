## CASE WHEN

### 第一种

```plsql
select id
case name
when 'nihao' then ''
when '' then ''
else 'qita' end as shi
from user;
```

### 第二种

```plsql
SELECT ID,	
CASE 	
	WHEN ID = '1' THEN ''
	WHEN ID THEN 
ELSE ID END AS DD	
FROM USER	
```

