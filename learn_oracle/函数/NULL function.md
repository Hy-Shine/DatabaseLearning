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

- NULLIF

  ```plsql
  Usage: NULLIF(exp1,exp2)
  --Description:
  If expr1 and expr2 are equal, the NULLIF function returns NULL. Otherwise, it returns expr1.
  Parameters:exp1 and exp2
  Must be either a numeric value or a value that is the same datatype.
  --Example
  SELECT NULLIF(12,12) FROM DUAL;
  Result:NULL
  SELECT NULLIF('123','1234') FROM DUAL;
  Result:'123'
  ```

- COALESCE

  ```sql
  Usage: COALESCE( expr1, expr2, ... expr_n )
  --Description:
  The COALESCE function returns the first non-null expression in the list. If all expressions evaluate to null, then the COALESCE function will return null.
  --Note:
  The COALESCE function returns any datatype such as a string, numeric, date, etc. 
  (BUT all expressions must be the same datatype in the COALESCE function.)
  --Example
  SELECT COALESCE(12,123)
  Result:12
  SELECT COALESCE(NULL,NULL,'A') FROM DUAL;
  Result:'A'
  SELECT COALESCE(NULL,NULL,NULL) FROM DUAL;
  Result:NULL
  ```

  