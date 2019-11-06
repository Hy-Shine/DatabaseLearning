### SUBSTR函数（字符截取函数）

#### 1 命令格式

```plsql
格式1： substr(string,a,b) //截取从a位置开始(含a)之后的b个字符，a为0或1等价
格式2： substr(string,a) //截取从a位置开始(含a)之后的所有字符，a为0或1等价
```

#### 2 实例

- 格式1

  ```plsql
   1、select substr('HelloWorld',0,3) value from dual; //返回结果：Hel，截取从“H”开始3个字符
   2、select substr('HelloWorld',1,3) value from dual; //返回结果：Hel，截取从“H”开始3个字符
   3、select substr('HelloWorld',2,3) value from dual; //返回结果：ell，截取从“e”开始3个字符
   4、select substr('HelloWorld',5,3) value from dual; //返回结果：oWo
   5、select substr('HelloWorld',-2,3) value from dual; //返回结果：ld 
   6、select substr('HelloWorld',-3,3) value from dual; //返回结果：rld （从后面倒数第三位开始往后取3个
  ```
  
- 格式2

  ```plsql
  1、select substr('HelloWorld',0) value from dual;  //返回结果：HelloWorld，截取所有字符
  2、select substr('HelloWorld',1) value from dual;  //返回结果：HelloWorld，截取所有字符
  3、select substr('HelloWorld',2) value from dual;  //返回结果：elloWorld，截取从“e”开始之后所有字符
  4、select substr('HelloWorld',-2) value from dual;  //返回结果：ld，从最后一个“d”开始 往回截取2个字符
  ```
  

### SUBSTRB函数

与`substr`函数类似，取得是**字节数**，`substr`函数取得是字符数。