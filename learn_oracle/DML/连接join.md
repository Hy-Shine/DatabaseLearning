## 连接

### 1	交叉连接	CROSS JOIN

```plsql
---该连接也称为笛卡尔连接
---返回行数为两表行数之积(不加过滤条件时)
SELECT * FROM A CROSS JOIN B WHERE CONDITIONS
等价于
SELECT * FROM A,B WHERE CONDITIONS
```

### 2	内连接	INNER 	JOIN

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/SQL_Join_-_07_A_Inner_Join_B.svg/220px-SQL_Join_-_07_A_Inner_Join_B.svg.png" alt="显示内部重叠部分填充的维恩图。" style="zoom:110%;" />

```plsql
---结果为符合连接条件的两表的交集
SELECT A.*,B.* FROM A INNER [OUTER] JOIN B ON A.COL_A1 = B.COL_B1 [WHERE CONDITIONS]
```

### 3	左(外)连接	LEFT	JOIN

![显示左边圆圈和重叠部分填充的维恩图。](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f6/SQL_Join_-_01_A_Left_Join_B.svg/220px-SQL_Join_-_01_A_Left_Join_B.svg.png)

```PLSQL
---以左表为主表,根据连接条件匹配右表
SELECT A.*,B.* FROM A LEFT [OUTER] JOIN B ON A.COL_A1 = B.COL_B1 [WHERE CONDITIONS]
```

### 4	右(外)连接	RIGHT	JOIN 

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/SQL_Join_-_03_A_Right_Join_B.svg/220px-SQL_Join_-_03_A_Right_Join_B.svg.png" alt="显示右边圆圈和重叠部分填充的维恩图。" style="zoom:110%;" />

```plsql
---以右表为主表,根据连接条件匹配左表
SELECT A.*,B.* FROM A RIGHT [OUTER] JOIN B ON A.COL_A1 = B.COL_B1 [WHERE CONDITIONS]
```

### 5	全连接	FULL	JOIN

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3d/SQL_Join_-_05b_A_Full_Join_B.svg/220px-SQL_Join_-_05b_A_Full_Join_B.svg.png" alt="显示右圆、左圆和重叠部分填充的维恩图。" style="zoom:110%;" />

```plsql
---结果为两表的并集,也是左右外连接的并集
SELECT A.*,B.* FROM A FULL [OUTER] JOIN B ON A.COL_A1 = B.COL_B1 [WHERE CONDITIONS]
等价于
SELECT A.*,B.* 
	FROM A LEFT [OUTER] JOIN B 
		ON A.COL_A1 = B.COL_B1
UNION
SELECT A.*,B.* 
	FROM A RIGHT [OUTER] JOIN B 
		ON A.COL_A1 = B.COL_B1
[WHERE CONDITIONS]
```

