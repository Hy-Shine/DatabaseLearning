## 字符函数

- SUBSTR()

    ```PLSQL
    字符截取函数
    select SUBSTR(STR,a,b) from dual;	--a位置开始(a为负值从后面开始),长度为b
    SELECT SUBSTR(str,a) from dual;	--a位置开始,到末尾
    示例：
    SELECT SUBSTR('HELLO',2,2),SUBSTR('HELLO',2),SUBSTR('HELLO',-2,2) FROM DUAL;--EL,ELLO,LO
    ```

- CONCAT() 

    ```plsql
    --字符连接函数
    SELECT CONCAT(str1,str2) from dual;
    eg: select concat(123,'hello') from dual;--123hello 
    ```

- LENGTH()

    ```PLSQL
    --长度函数
    SELECT LENGTH('123ABC你好'),LENGTHB('123ABC你好') FROM DUAL;  --8,10
    ```

- TRIM()

    ```plsql
    --去除空格
    trim 去除两端空格，不去除字符中间空格,ltrim 去除左端空格，不去除中间,rtrim 去除右端空格，不去除中间
    select trim(' a b '),ltrim(' a b '),rtrim(' a b ') from dual;--a b,a b , a b;
    ```

- INSTR()

    ```PLSQL
    --字符查找函数
    INSTR(str1,str2)  --返回str2在str1第一次出现的位置
    INSTR(str1,str2,n1,n2)  --n1:开始位置,n2:第几次出现,若n1<0则反向查找
    eg:
    SELECT INSTR('ABEQWE','E') FROM DUAL;  --3
    SELECT INSTR('ABEQWE','E',2,2) FROM DUAL;  --6
    ```

- rpad()、lpad()

    ```plsql
    --填充函数
    --格式：lpad(object1,length,object2)
    lpad()左侧填充,rpad()右侧填充
    ```

- INITCAP()

  ```plsql
  --将每个单词首字母大写,其余小写,单词之间不应以数字连接
  initcap('hEllo world') >Hello World
  initcap('hello2world') >Hello2world
  initcap('hello[!|#|%|汉字]world') >Hello[!|#|%|汉字]World，特殊字符包含且不限于这些
  ```

- chr(),ascii()

    ```plsql
    --char() 将ascii值对应字符,ascii()求对应字符的ascii值
    CHR(65)	A
    ASCII('A')	65
    ```

    