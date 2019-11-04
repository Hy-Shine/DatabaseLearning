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
select id,
case 
	when id = '1' then ''
	when id then 
else id end as dd
from user
```

