## 日期函数

Oracle中常用的日期格式有两种：DATE、TIMESTAMP。DATE精确到秒，TIMESTAMP精确到秒的小数。

```plsql
--Oracle中的日期可以与数值直接计算，DATE/TIMESTAMP类型与数值直接计算的结果均为DATE类型
SELECT SYSDATE,SYSDATE+1 加1天,SYSDATE+1/24 加1小时,SYSDATE+1/24/60 加1分钟,SYSDATE+1/24/60/60 加1秒 FROM DUAL;
--不损失timestamp精度的日期与数值的加减计算
SELECT SYSDATE,SYSDATE+INTERVAL '1' YEAR FROM DUAL;
INTERVAL 'Value' format(year|month|day|hour|minute|second)
```

- add_months(date,i)  加减月份

  ```plsql
  SELECT ADD_MONTHS(SYSDATE,+-2) FROM DUAL;   ---当前时间添加/减去2个月
  ```
  
- MONTHS_BETWEEN(date1,date2)

  ```plsql
  --返回间隔月份
  SELECT MONTHS_BETWEEN(SYSDATE,DATE '2019-08-12') FROM DUAL;
  Result: 3.40814628136201
  ```

- next_day(date,char)

  ```plsql
  --char为星期一~日|,monday~sunday(看数据库格式)
  --返回下一个周一的日期
  SELECT NEXT_DAY(SYSDATE,'MONDAY|星期一') FROM DUAL;
  ```

- last_day(date)

  ```plsql
  作用：返回某月的最后一天
  SELECT LAST_DAY(date1) FROM DUAL;  --返回指定日期所在月份的最后一天
  ```

- extract(date from datetime)

  ```plsql
  --Date1为日期格式,YEAR、MONTH、DAY、HOUR、MINUTE、SECOND
  SELECT EXTRACT(month from Date1) from TABLE1;
  SELECT EXTRACT(YEAR FROM SYSDATE) FROM DUAL;
  SELECT EXTRACT(DAY FROM SYSDATE) FROM DUAL;
  ```

### TRUNC()函数
```plsql
TRUNC(DATE1,'dd')	--一天之初
TRUNC(DATE1,'day')	--一周之初
TRUNC(DATE1,'mm|month')	--一月之初
TRUNC(DATE1,'yyyy|year')	--一年之初
```