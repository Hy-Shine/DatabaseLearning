## DECODE函数

```plsql
--格式
DECODE(表达式,条件1,结果1,条件2,结果2...,缺省值)
若表达式的值满足条件1，则输出结果1，
若表达式的值满足条件2，则输出结果2，
所有条件均不满足，则输出缺省值。
```

```plsql
--只有一个条件的情况
DECODE(表达式,条件,结果1,结果2)
```

## SIGN函数

```plsql
--格式
sign(差值)      
若差值结果大于0，结果返回1；小于0，返回-1；等于0，返回0。

```

