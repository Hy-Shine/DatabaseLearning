## LOOP语句

- 循环控制: LOOP 语句，LOOP 语句多次执行语句序列

LOOP 语句的三种形式:

- **Simple loop**无条件的循环

  ```plsql
  LOOP
  	statement1;
  	statement2;
  	...
  	EXIT [WHEN CONDITION];
  END LOOP;
  --使用loop语句时,应使用EXIT语句结束循环，否则将陷入死循环
  ```

- **WHILE loop**有条件的循环

  **Syntax**

  ```PLSQL
  --在WHILE LOOP中，如果条件成立则执行循环，否则结束循环
  WHILE condition LOOP
  	statement1;
  	statement2;
  	...
  END LOOP;
  ```

  eg:

  ```plsql
  DECLARE
    v_counter NUMBER :=1;
    v_result NUMBER ;
  BEGIN
    WHILE  v_counter <= 10 LOOP
      v_result := 9  *v_counter;
      DBMS_OUTPUT.PUT_LINE('9'||'x'||v_counter||' = '||v_result);
      v_counter  := v_counter+1;
    END LOOP;
  DBMS_OUTPUT.PUT_LINE('out');
  END;
  ```

- **FOR loop**有计数的循环

  ```plsql
  FOR loop_counter in [REVERSE] lower_limit .. upper_limit LOOP
  	statement1;
  	statement2;
  	...
  END LOOP;
  ```
  
eg:
  
  ```plsql
  DECLARE
    v_result  NUMBER;
  BEGIN
    FOR v_counter IN  1..10 LOOP
      v_result:= 19*v_counter;
      DBMS_OUTPUT.PUT_LINE(v_result);
    END LOOP;
  END;
  ```
  
  