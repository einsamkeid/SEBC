
### Master server
```
mysql> GRANT REPLICATION SLAVE ON *.* TO 'root'@'ip-10-0-0-123.ap-southeast-1.compute.internal' IDENTIFIED BY 'password';
Query OK, 0 rows affected (0.00 sec)

mysql> SET GLOBAL binlog_format = 'ROW';
Query OK, 0 rows affected (0.00 sec)

mysql> FLUSH TABLES WITH READ LOCK;
Query OK, 0 rows affected (0.00 sec)

mysql> SHOW MASTER STATUS;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000004 |      294 |              |                  |
+-------------------------+----------+--------------+------------------+
1 row in set (0.00 sec)


mysql> UNLOCK TABLES;
```

### Replica server
```
mysql> CHANGE MASTER TO MASTER_HOST='ip-10-0-0-122.ap-southeast-1.compute.internal', MASTER_USER='root', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql-bin.000004', MASTER_LOG_POS=294;
Query OK, 0 rows affected (0.02 sec)
mysql> START SLAVE;
```

### Output of `SHOW SLAVE STATUS \G` on replica server
```
mysql> SHOW SLAVE STATUS \G
*************************** 1. row ***************************
               Slave_IO_State: Connecting to master
                  Master_Host: ip-10-0-0-122.ap-southeast-1.comp           ute.internal
                  Master_User: root
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql-bin.000004
          Read_Master_Log_Pos: 294
               Relay_Log_File: mysqld-relay-bin.000001
                Relay_Log_Pos: 4
        Relay_Master_Log_File: mysql-bin.000004
             Slave_IO_Running: No
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 294
              Relay_Log_Space: 106
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: NULL
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 2013
                Last_IO_Error: error connecting to master 'root@           ip-10-0-0-122.ap-southeast-1.compute.internal:3306' - retry-time           : 60  retries: 86400
               Last_SQL_Errno: 0
               Last_SQL_Error:
1 row in set (0.00 sec)

```