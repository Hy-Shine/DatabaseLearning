## 创建dblink

### 1 检查dblink

```plsql
select t.* from dba_objects t where t.object_type='DATABASE LINK';
或
select * from dba_db_links;  --结果较为详细
```

### 2 检查用户权限

对于要创建`dblink`的用户需要拥有创建`dblink`权限，如果没有则需要具有`dba`权限的用户授权。

```plsql
grant [public] create database link to user_name;
```

### 3 创建dblink

```plsql
创建全局[public] dblink需要sys，system用户
实例：
create [public] database link dblink_name  --dblink_name:要创建的dblink名称
connect to 数据库用户名 identified by "用户密码"  --要连接的数据库，名称及密码
using '(DESCRIPTION = (ADDRESS_LIST = (ADDRESS = (PROTOCOL = TCP)(HOST =210.41.168.143)(PORT = 1521)))(CONNECT_DATA = (SERVICE_NAME = orcl)))';
```

### 4 删除dblink

```plsql
drop [public] database link dblink_name;
```

