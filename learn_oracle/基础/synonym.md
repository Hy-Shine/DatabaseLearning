## 同义词

### 1 介绍

Oracle synonym 同义词是数据库当前用户通过给另外一个用户的对象创建一个别名，然后可以通过对别名进行查询和操作，等价于直接操作该数据库对象。Oracle同义词常常是给表、视图、函数、过程、包等制定别名。

### 2 操作

###	2.1	创建同义词

```plsql
--创建public synonym 需要有dba权限,创建者要有对object的操作权限
CREATE [OR REPLACE] [PUBLIC] SYNONYM [USER1].SYNONYM_NAME FOR user2.object 
```

### 2.2	删除

```plsql
--同义词删除只能通过同义词拥有者的用户或者具有DBA权限的用户才能删除
DROP [PUBLIC] SYNONYM [USER.]sysnonym_name;
```

