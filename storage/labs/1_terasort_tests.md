# Create an end-user Linux account named with your GitHub handle
```
[root@ip-10-0-0-73 ~]# useradd einsamkeid
``` 
## Create a home HDFS directory for this user as well
```
[root@ip-10-0-0-73 ~]# sudo -u hdfs hdfs dfs -mkdir /user/einsamkeid
[root@ip-10-0-0-73 ~]# sudo -u hdfs hdfs dfs -chown einsamkeid:einsamkeid /user/einsamkeid
```
## Run the following exercises as this user
[root@ip-10-0-0-73 ~]# su einsamkeid
[einsamkeid@ip-10-0-0-73 root]$ cd
[einsamkeid@ip-10-0-0-73 ~]$


## Create a 10 GB file using `teragen`

```
[einsamkeid@ip-10-0-0-73 ~]$ cd /opt/cloudera/parcels/CDH/jars/

[einsamkeid@ip-10-0-0-73 jars]$ time hadoop jar hadoop-examples.jar teragen -Ddfs.block.size=33554432 -Dmapred.map.tasks=4 107374182 /user/einsamkeid/teragen

...

        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=230593859918397906
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10737418200

real    2m45.780s
user    2m11.682s
sys     0m8.798s


[einsamkeid@ip-10-0-0-73 jars]$ hdfs dfs -du -h -s teragen
10.0 G  30.0 G  teragen


[einsamkeid@ip-10-0-0-73 jars]$ hdfs dfs -stat '%n %b %o' teragen/*
_SUCCESS 0 33554432
part-m-00000 10737418200 33554432
```

## Run the `terasort` command on this file
 ```
 [einsamkeid@ip-10-0-0-73 jars]$ time hadoop jar hadoop-examples.jar terasort teragen terasort
 ...
        File Input Format Counters
                Bytes Read=10737418200
        File Output Format Counters
                Bytes Written=0
16/12/06 08:23:28 INFO terasort.TeraSort: done

real    8m26.819s
user    8m48.082s
sys     1m11.125s
```