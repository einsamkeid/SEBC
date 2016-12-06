## Create a `precious` directory in HDFS; copy the ZIP course file into it.
```
[iskeskin@ip-172-30-0-132 ~]$ hdfs dfs -mkdir precious
[iskeskin@ip-172-30-0-132 ~]$ hdfs dfs -put SEBC-master.zip precious
```
## Enable snapshots for `precious`
```
[einsamkeid@ip-10-0-0-73 ~]$ hdfs dfs -mkdir  precious
[einsamkeid@ip-10-0-0-73 ~]$ hdfs dfs -put SEBC-master.zip precious
[einsamkeid@ip-10-0-0-73 ~]$ hdfs dfs -ls precious
Found 1 items
-rw-r--r--   3 einsamkeid einsamkeid     410040 2016-12-06 08:40 precious/SEBC-master.zip

[root@ip-10-0-0-73 einsamkeid]# sudo su hdfs
[hdfs@ip-10-0-0-73 einsamkeid]$ hdfs dfsadmin -allowSnapshot /user/einsamkeid/precious
Allowing snaphot on /user/einsamkeid/precious succeeded
```

## Create a snapshot called `sebc-hdfs-test`
```
[hdfs@ip-10-0-0-73 einsamkeid]$ hdfs dfs -createSnapshot /user/einsamkeid/precious sebc-hdfs-test
Created snapshot /user/einsamkeid/precious/.snapshot/sebc-hdfs-test
```

## Delete the directory
```
[hdfs@ip-10-0-0-73 einsamkeid]$ hdfs dfs -rm -r -skipTrash /user/einsamkeid/precious
rm: The directory /user/einsamkeid/precious cannot be deleted since /user/einsamkeid/precious is snapshottable and already has snapshots
```

## Delete the ZIP file
```
[hdfs@ip-10-0-0-73 einsamkeid]$  hdfs dfs -rm -r -skipTrash /user/einsamkeid/precious/*
Deleted /user/einsamkeid/precious/SEBC-master.zip

```

## Restore the deleted file
```
[einsamkeid@ip-10-0-0-73 root]$ hdfs dfs -cp -ptopax precious/.snapshot/sebc-hdfs-test/SEBC-master.zip precious/

[einsamkeid@ip-10-0-0-73 root]$ hdfs dfs -ls precious/
Found 1 items
-rw-r--r--   3 einsamkeid einsamkeid     410040 2016-12-06 08:49 precious/SEBC-master.zip
```