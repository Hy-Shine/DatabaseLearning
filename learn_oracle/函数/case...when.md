## CASE WHEN

### 第一种

```plsql
select id,
case name
	when 'nihao' then value1
	when '' then value2
	else 'qita' 
end as column_name
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

