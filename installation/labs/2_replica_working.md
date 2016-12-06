
### Master server
```
mysql> GRANT REPLICATION SLAVE ON *.* TO 'root'@'ip-10-0-0-74.ap-southeast-1.compute.internal' IDENTIFIED BY 'password';
Query OK, 0 rows affected (0.00 sec)

mysql> SET GLOBAL binlog_format = 'ROW';
Query OK, 0 rows affected (0.00 sec)

mysql> FLUSH TABLES WITH READ LOCK;
Query OK, 0 rows affected (0.00 sec)

mysql> SHOW MASTER STATUS;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000003 |      3029|              |                  |
+-------------------------+----------+--------------+------------------+
1 row in set (0.00 sec)


mysql> UNLOCK TABLES;
```

### Replica server
```
mysql> CHANGE MASTER TO MASTER_HOST='ip-10-0-0-73.ap-southeast-1.compute.internal', MASTER_USER='root', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql_binary_log.000003', MASTER_LOG_POS=3029;
Query OK, 0 rows affected (0.02 sec)
mysql> START SLAVE;
```

### Output of `SHOW SLAVE STATUS \G` on replica server
```
mysql> show slave status \G;
*************************** 1. row ***************************
               Slave_IO_State:
                  Master_Host: ip-10-0-0-73.ap-southeast-1.compute.internal
                  Master_User: root
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql-binary_log.000003
          Read_Master_Log_Pos: 3029
               Relay_Log_File: mysqld-relay-bin.000001
                Relay_Log_Pos: 4
        Relay_Master_Log_File: mysql-binary_log.000003
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
          Exec_Master_Log_Pos: 3029
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
                Last_IO_Errno: 1236
                Last_IO_Error: Got fatal error 1236 from master when reading data from binary log: 'Could not find first log file name in binary log index file'
               Last_SQL_Errno: 0
               Last_SQL_Error:
1 row in set (0.00 sec)

ERROR:
No query specified


```