# Prueba de Sentry con Hive en ambiente Kerberizado

```
[dobeslao@ip-172-31-24-52 ~]$ kinit
Password for dobeslao@VINKOS.COM:

[dobeslao@ip-172-31-24-52 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1002
Default principal: dobeslao@VINKOS.COM

Valid starting       Expires              Service principal
11/29/2017 15:06:09  11/30/2017 15:06:09  krbtgt/VINKOS.COM@VINKOS.COM
        renew until 12/06/2017 15:06:09

[dobeslao@ip-172-31-24-52 ~]$ beeline
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-18-127.ec2.internal:10000/default;principal=hive/ip-172-31-18-127.ec2.internal@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-18-127.ec2.internal:10000/default;principal=hive/ip-172-31-18-127.ec2.internal@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-18-127.ec2.internal> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129210909_0c82d708-4d88-4fa8-84f9-0dd400440b62): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129210909_0c82d708-4d88-4fa8-84f9-0dd400440b62); Time taken: 0.576 seconds
INFO  : Executing command(queryId=hive_20171129210909_0c82d708-4d88-4fa8-84f9-0dd400440b62): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129210909_0c82d708-4d88-4fa8-84f9-0dd400440b62); Time taken: 0.242 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.117 seconds)
0: jdbc:hive2://ip-172-31-18-127.ec2.internal>
```

# Pruebas de usuarios desde beeline

## george
```
[dobeslao@ip-172-31-18-218 ~]$ kdestroy ; kinit george

[dobeslao@ip-172-31-18-218 ~]$ beeline -u "jdbc:hive2://ip-172-31-18-127.ec2.internal:10000/default;principal=hive/ip-172-31-18-127.ec2.internal@VINKOS.COM"

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129222626_cfae0c1c-65ea-42d9-bcc3-b5db05730ff0): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129222626_cfae0c1c-65ea-42d9-bcc3-b5db05730ff0); Time taken: 0.052 seconds
INFO  : Executing command(queryId=hive_20171129222626_cfae0c1c-65ea-42d9-bcc3-b5db05730ff0): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129222626_cfae0c1c-65ea-42d9-bcc3-b5db05730ff0); Time taken: 0.095 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| checksum   |
| sample_07  |
+------------+--+
2 rows selected (0.16 seconds)

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> select * from checksum;
INFO  : Compiling command(queryId=hive_20171129222626_c395e9b2-736b-4a38-9022-534ef5102d72): select * from checksum
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:checksum.md5sum, type:string, comment:null), FieldSchema(name:checksum.year, type:int, comment:null), FieldSchema(name:checksum.month, type:int, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129222626_c395e9b2-736b-4a38-9022-534ef5102d72); Time taken: 0.156 seconds
INFO  : Executing command(queryId=hive_20171129222626_c395e9b2-736b-4a38-9022-534ef5102d72): select * from checksum
INFO  : Completed executing command(queryId=hive_20171129222626_c395e9b2-736b-4a38-9022-534ef5102d72); Time taken: 0.001 seconds
INFO  : OK
+------------------+----------------+-----------------+--+
| checksum.md5sum  | checksum.year  | checksum.month  |
+------------------+----------------+-----------------+--+
+------------------+----------------+-----------------+--+
No rows selected (0.181 seconds)

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> select * from default.sample_07;
INFO  : Compiling command(queryId=hive_20171129221111_95655496-fd3e-45cf-b319-044b03c5107b): select * from default.sample_07
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:sample_07.name, type:string, comment:null), FieldSchema(name:sample_07.age, type:int, comment:null), FieldSchema(name:sample_07.active, type:boolean, comment:null), FieldSchema(name:sample_07.year, type:int, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129221111_95655496-fd3e-45cf-b319-044b03c5107b); Time taken: 0.167 seconds
INFO  : Executing command(queryId=hive_20171129221111_95655496-fd3e-45cf-b319-044b03c5107b): select * from default.sample_07
INFO  : Completed executing command(queryId=hive_20171129221111_95655496-fd3e-45cf-b319-044b03c5107b); Time taken: 0.0 seconds
INFO  : OK
+-----------------+----------------+-------------------+-----------------+--+
| sample_07.name  | sample_07.age  | sample_07.active  | sample_07.year  |
+-----------------+----------------+-------------------+-----------------+--+
+-----------------+----------------+-------------------+-----------------+--+
No rows selected (0.199 seconds)

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> insert into sample_07 partition (year=2017) values ('usuario',33,true);
Error: Error while compiling statement: FAILED: SemanticException No valid privileges
 User george does not have privileges for QUERY
 The required privileges: Server=server1->Db=default->Table=sample_07->action=insert; (state=42000,code=40000)
```

## ferdinand
```
[dobeslao@ip-172-31-24-52 ~]$ kdestroy ; kinit ferdinand

[dobeslao@ip-172-31-24-52 ~]$ beeline -u "jdbc:hive2://ip-172-31-18-127.ec2.internal:10000/default;principal=hive/ip-172-31-18-127.ec2.internal@VINKOS.COM"

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129223636_812fd292-ae8d-4070-960f-856362ecdad3): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129223636_812fd292-ae8d-4070-960f-856362ecdad3); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20171129223636_812fd292-ae8d-4070-960f-856362ecdad3): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129223636_812fd292-ae8d-4070-960f-856362ecdad3); Time taken: 0.109 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.255 seconds)

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> select * from default.sample_07;
INFO  : Compiling command(queryId=hive_20171129221818_33fd1ad1-882d-4ccb-89d6-9d4e61be1bd2): select * from default.sample_07
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:sample_07.name, type:string, comment:null), FieldSchema(name:sample_07.age, type:int, comment:null), FieldSchema(name:sample_07.active, type:boolean, comment:null), FieldSchema(name:sample_07.year, type:int, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129221818_33fd1ad1-882d-4ccb-89d6-9d4e61be1bd2); Time taken: 0.159 seconds
INFO  : Executing command(queryId=hive_20171129221818_33fd1ad1-882d-4ccb-89d6-9d4e61be1bd2): select * from default.sample_07
INFO  : Completed executing command(queryId=hive_20171129221818_33fd1ad1-882d-4ccb-89d6-9d4e61be1bd2); Time taken: 0.001 seconds
INFO  : OK
+-----------------+----------------+-------------------+-----------------+--+
| sample_07.name  | sample_07.age  | sample_07.active  | sample_07.year  |
+-----------------+----------------+-------------------+-----------------+--+
+-----------------+----------------+-------------------+-----------------+--+
No rows selected (0.194 seconds)

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> insert into sample_07 partition (year=2017) values ('usuario',33,true);
Error: Error while compiling statement: FAILED: SemanticException No valid privileges
 User ferdinand does not have privileges for QUERY
 The required privileges: Server=server1->Db=default->Table=sample_07->action=insert; (state=42000,code=40000)

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> select * from checksum;
Error: Error while compiling statement: FAILED: SemanticException No valid privileges
 User ferdinand does not have privileges for QUERY
 The required privileges: Server=server1->Db=default->Table=checksum->Column=md5sum->action=select; (state=42000,code=40000)
```

## Bonus, datos de ambiente

```
0: jdbc:hive2://ip-172-31-18-127.ec2.internal> SHOW ROLES;
INFO  : Compiling command(queryId=hive_20171129224747_ed699da1-d796-4411-b9c0-a8df3dfc2eb8): SHOW ROLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:role, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129224747_ed699da1-d796-4411-b9c0-a8df3dfc2eb8); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20171129224747_ed699da1-d796-4411-b9c0-a8df3dfc2eb8): SHOW ROLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129224747_ed699da1-d796-4411-b9c0-a8df3dfc2eb8); Time taken: 0.024 seconds
INFO  : OK
+---------------+--+
|     role      |
+---------------+--+
| writes        |
| reads         |
| sentry_admin  |
+---------------+--+

0: jdbc:hive2://ip-172-31-18-127.ec2.internal> SHOW DATABASES;
INFO  : Compiling command(queryId=hive_20171129224747_adc41234-175c-47b9-ac7b-4c8bad7ded31): SHOW DATABASES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:database_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129224747_adc41234-175c-47b9-ac7b-4c8bad7ded31); Time taken: 0.052 seconds
INFO  : Executing command(queryId=hive_20171129224747_adc41234-175c-47b9-ac7b-4c8bad7ded31): SHOW DATABASES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129224747_adc41234-175c-47b9-ac7b-4c8bad7ded31); Time taken: 0.098 seconds
INFO  : OK
+----------------+--+
| database_name  |
+----------------+--+
| default        |
+----------------+--+
1 row selected (0.164 seconds)
```
