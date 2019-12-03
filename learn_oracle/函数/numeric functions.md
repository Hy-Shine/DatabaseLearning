## 数值函数

```plsql
---数值函数
FLOOR(x)  向下取整,返回小于或等于n的最大的整数
CEIL(x)   向上取整,返回大于或等于n的最小的整数
MOD(m,n)  取余函数
ABS(x)  取绝对值
SQRT(x)  取平方根
```

```plsql
LOG(x,y) : 以x为底y的对数,x>0 and !=1,
LN(x) : 即ln(x)
EXP(x) : e的x次方
POWER(m,n)  求幂,m的n次方
```

```plsql
--TRUNC(X[,Y])函数：X在第Y位截断。直接截取,不四舍五入。y缺省值为0。y>0,就是四舍五入到小数点右边y位。若y<0,四舍五入到小数点左边|y|位。
SELECT TRUNC(12.364,2) FROM DUAL;  --12.36
SELECT TRUNC(12.364,1) FROM DUAL;  --12.3
SELECT TRUNC(12.364,0) FROM DUAL;  --12
SELECT TRUNC(12.364,-1) FROM DUAL;  --10
SELECT TRUNC(12.364,-2) FROM DUAL;  --0
--ROUND(x,n) : 用法与 trunc()函数类似,四舍五入,n为保留至小数点多少位
select ROUND(12.365,-2) from DUAL;  --0
SELECT ROUND(12.35,1) FROM  DUAL;  --12.4
```

- NVL()与NVL2()

  ```plsql
  --nvl(exp1,exp2)  若exp1为空则返回exp2,否则返回exp1
  SELECT NVL('','HELLO') ISNULL,  --HELLO
  NVL('123','HELLO') NOTNULL  --123
  FROM DUAL
  --NVL2(expr1,expr2,expr3)  若exp1非空则返回exp2,否则返回exp3
  SELECT NVL2('','yes','no')  ISNULL,  --no
  NVL2('123','yes','no') NOTNULL  --yes
  FROM DUAL
  ```

  