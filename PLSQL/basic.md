## 基础

plsql程序由三部分组成：声明部分(`declare`),执行部分(`begin end`),异常部分(`exception`)

```PLSQL
PLSQL块结构：
DECLARE
	/*声明部分：变量、类型、游标*/
BEGIN
	/*执行部分：过程和sql语句,也是程序的主要部分*/
EXCEPTION
	/*异常部分：处理错误*/
END;
```
```plsql
--变量命名
v_name  --变量
c_name  --常量
```

```plsql
--声明变量
v_n number := 1;
v_name varchar2(100);  --将v_name定义为varchar2(100)类型
v_name table1.name%type;  --动态的获取变量类型,将表table1的name字段类型赋予v_name
```

