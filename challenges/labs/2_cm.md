## List the command and output of ls /etc/yum.repos.d in challenges/labs/2_cm.md
```
[root@ip-10-0-0-137 java]# ls /etc/yum.repos.d
CentOS-Base.repo       CentOS-Media.repo  cloudera-manager.repo  mysql-community-source.repo
CentOS-Debuginfo.repo  CentOS-Vault.repo  mysql-community.repo
```

## Copy the GRANT statement you used into challenges/labs/2_cm.md
```
mysql> drop user scm;
Query OK, 0 rows affected (0.00 sec)
mysql> grant all on scm.* TO 'scm'@'ec2-54-198-42-51.compute-1.amazonaws.com' IDENTIFIED BY '123456';
Query OK, 0 rows affected (0.00 sec)
mysql> grant all on scm.* TO 'scm'@'ip-172-30-0-16.ec2.internal' IDENTIFIED BY '123456';
Query OK, 0 rows affected (0.00 sec)
```

## Use the scm_prepare_database.sh script to write your db.properties file
```
[root@ip-10-0-0-137 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm scm
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
2016-12-09 03:16:37,653 [main] INFO  com.cloudera.enterprise.dbutil.DbCommandExecutor  - Successfully connected to database.
All done, your SCM database is configured correctly!

```