## 表空间

### 1	表空间介绍

```plsql
---表空间的分类
永久表空间：存放数据库中永久化存储的对象，表、视图、存储过程等。
临时表空间：存放数据库操作中中间执行的过程，执行结束后存放的内容被自动释放掉，不进行永久保存。
UNDO表空间：保存事务所修改数据的旧值，也就是被修改前的数据。利用UNDO表空间可以对数据进行撤销、回滚的操作。
```

### 2	创建与管理

- 新建数据表空间

    ```plsql
    CREATE TABLESPACE TABLESPACE_NAME
    datafile 'D:\oracle\product\10.2.0\oradata\orcl\SIRM2.dbf' size 1024M	--存储位置,初始大小1024M
    AUTOEXTEND ON NEXT 50M MAXSIZE UNLIMITED|2000M	--每次扩展50M，无限制扩展(最大2000M)
    EXTENT MANAGEMENT local  autoallocate   --区管理本地化
    SEGMENT SPACE MANAGEMENT AUTO;   --段空间管理为自动
    ```

- 临时表空间

    ```
    临时表空间也可以用，但是只能将临时表放在里面，临时表空间主要放置一些临时数据，比如查询一个复杂的sql语句，系统会将中间数据放在临时表空间里暂存临时表空间会自己删除（可以选择会话结束就删除）
    ```

    ```plsql
    CREATE TEMPORARY TABLESPACE USER_TEMP  
    TEMPFILE 'D:\oracle\oradata\Oracle9i\user_temp.dbf'   --存储位置
    size 500m   --初始大小
    AUTOEXTEND ON NEXT 50M MAXSIZE 2G   --自动扩展,每次50M,最大至2G
    extent management local; 
    ```

- 查看用户表空间

    ```plsql
    DBA_TABLESPACES    系统管理员级的用户查看的数据字典
    USER_TABLESPACES   普通用户查看的数据字典
    ```

- 自动增长

    ```plsql
    ALTER DATABASE DATAFILE 'c:\SmartDB01.ora' AUTOEXTEND ON;	--设置表空间自动增长
    ALTER DATABASE DATAFILE 'c:\SmartDB01.ora' AUTOEXTEND ON NEXT 100M [maxsize 2000M];//每次自动增长200m，最大2000M
    ```

- 表空闲情况

    ```plsql
    SELECT TABLESPACE_NAME,SUM(BYTES)/1024/1024 FROM DBA_FREE_SPACE GROUP BY TABLESPACE_NAME; 
    dba_data_files，DBA_TABLESPACES
    ```

- 修改数据文件

    ```plsql
    增加数据文件 ALTER TABLESPACE tablespace_name ADD DATAFILE 'XX.dbf' SIZE xx;
    删除数据文件 ALTER TABLESPACE tablespace_nameDROP DATEFILE 'XX.dbf';  
    --注：不能删除表空间中的第一个数据文件，如果要删除该文件则需要删除整个表空间
    ```

    

- 删除表空间

    ```plsql
    DROP TABLESPACE tablespace_name [INCLUDING CONTENTS [AND DATAFILES][CASCADE CONSTRAINT]];
    注：无选项	--当表空间为空才能删除, 只是删除表空间(不删除里面的数据文件,物理文件保留)。
    INCLUDING CONTENTS	--删除表空间及对象
    INCLUDING CONTENTS AND DATAFILES  --删除表空间、对象及数据文件
    INCLUDING CONTENTS CASCADE CONSTRAINT	--删除关联
    INCLUDING CONTENTS AND DATAFILES CASCADE CONSTRAINT	--含前两项。表空间删除后，如果物理文件没删除，去本地路径下手动删除。
    
    ```

    