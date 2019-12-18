## constraint

### 1	约束类型

```plsql
主键约束、唯一约束、非空约束、外键约束、检检查约束
--查询约束  OWNER,CONSTRAINT_NAME,CONSTRAINT_TYPE,TABLE_NAME
SELECT * FROM USER_CONSTRAINTS WHERE OWNER = 'USER_NAME' AND TABLE_NAME = 'TABLE_NAME';
```

### 2	约束

#### 2.1	主键约束

```plsql
--单个字段主键
alter table table1 add constraint constraint_name primary key col1;
alter table table1 add primary key col1;
--复合主键
alter table table1 add constraint constraint_name primary key (col1,col2,..);
--删除主键
alter table table1 drop constraint constraint_name;
alter table table1 drop primary key;
```

启用/禁用Oracle PRIMARY KEY约束

```plsql
ALTER TABLE table_name DISABLE|ENABLE CONSTRAINT primary_key_constraint_name;
ALTER TABLE table_name DISABLE|ENABLE PRIMARY KEY;
[启用|禁用约束]
ALTER TABLE TABLE_NAME ENABLE|DISABLE CONSTRAINT CONSTRAINT_NAME;
```

