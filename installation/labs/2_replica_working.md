# MariaDB installation - with a replica server

The Slave_IO_State field will read Waiting for master to send event.

```
MariaDB [(none)]> SHOW SLAVE STATUS\G;  -- (check if any error)
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: ip-172-31-29-97.ec2.internal
                  Master_User: replicant
                  Master_Port: 3306
                Connect_Retry: 10
              Master_Log_File: mysql_binary_log.000005
          Read_Master_Log_Pos: 67980136
               Relay_Log_File: ip-172-31-18-63-relay-bin.000004
                Relay_Log_Pos: 67980431
        Relay_Master_Log_File: mysql_binary_log.000005
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB: employees,amon,rman,metastore,sentry,nav,navms,hive,hue,oozie,scm
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 67980136
              Relay_Log_Space: 67980789
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 1
               Master_SSL_Crl:
           Master_SSL_Crlpath:
                   Using_Gtid: No
                  Gtid_IO_Pos: 0-2-378
      Replicate_Do_Domain_Ids:
  Replicate_Ignore_Domain_Ids:
                Parallel_Mode: conservative
1 row in set (0.00 sec)
```
