###The hostname of your MySQL node
```
[root@ip-10-0-0-137 ~]# hostname -f
ip-10-0-0-137.ap-southeast-1.compute.internal
```

###The command and output for mysql --version
```
[root@ip-10-0-0-137 java]# mysql --version
mysql  Ver 14.14 Distrib 5.5.53, for Linux (x86_64) using readline 5.1
```
###The command and output for listing MySQL databases
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hue                |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)
