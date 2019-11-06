## REPLACE函数

REPLACE(COL,原内容，要替代内容)

- 单个字符替换

  ```plsql
  SELECT REPLACE('BH012','0','1') FROM DUAL;   ---将bh字段中的 0 全部替换为 1
  ```

- 连续的多字符串替换

  ```plsql
  SELECT REPLACE('ABCDEF','ABC','123') FROM DUAL;   --将ABC替换为123
  result:123DEF
SELECT REPLACE('ABCDEFG','ABD','123') FROM DUAL;  --未找到连续的ABD字符串，故不执行替换
  result:abcefg
  ```
  

## TRANSLATE函数

`格式:translate(col,from_string,to_string)`

将`from_string`中对应字符换成`to_string`中的对应字符，若`from_string`字符长度大于`to_string`，则无对应的以空值替换

```plsql
SELECT TRANSLATE('5*[2+6]/{9-3}', '[]{}', '()()') FROM DUAL;    --[被(替换,]被)替换,{被(替换,}被)替换
result:5*(2+6)/(9-3)
SELECT TRANSLATE('ABCDEFG','ABD','123') FROM DUAL;  --对比上面的replace函数
result:12C3EFG
SELECT TRANSLATE('ABCDEFG','ABD','123') FROM DUAL;  --from_string的长度大于to_string，D被空值替换
result:12CEFG
```

