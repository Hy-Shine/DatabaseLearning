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
   4、select substr('HelloWorld',0,100) value from dual; //返回结果：HelloWorld，100虽然超出预处理的字符串最长度，但不会影响返回结果，系统按预处理字符串最大数量返回。
   5、select substr('HelloWorld',5,3) value from dual; //返回结果：oWo
   6、select substr('Hello World',5,3) value from dual; //返回结果：o W (中间的空格也算一个字符串，结果是：o空格W)
   7、select substr('HelloWorld',-1,3) value from dual; //返回结果：d （从后面倒数第一位开始往后取1个字符，而不是3个。原因：下面红色 第三个注解）
   8、select substr('HelloWorld',-2,3) value from dual; //返回结果：ld （从后面倒数第二位开始往后取2个字符，而不是3个。原因：下面红色 第三个注解）
   9、select substr('HelloWorld',-3,3) value from dual; //返回结果：rld （从后面倒数第三位开始往后取3个字符）
  10、select substr('HelloWorld',-4,3) value from dual; //返回结果：orl （从后面倒数第四位开始往后取3个字符）
  ```

- 格式2

  ```plsql
  11、select substr('HelloWorld',0) value from dual;  //返回结果：HelloWorld，截取所有字符
  12、select substr('HelloWorld',1) value from dual;  //返回结果：HelloWorld，截取所有字符
  13、select substr('HelloWorld',2) value from dual;  //返回结果：elloWorld，截取从“e”开始之后所有字符
  14、select substr('HelloWorld',-1) value from dual;  //返回结果：d，从最后一个“d”开始 往回截取1个字符
  15、select substr('HelloWorld',-2) value from dual;  //返回结果：ld，从最后一个“d”开始 往回截取2个字符
  ```
  

### SUBSTRB函数

与`substr`函数类似，取得是**字节数**，`substr`函数取得是字符数。