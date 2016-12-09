## The full teragen command
```
[root@ip-10-0-0-137 java]# su raffles
[raffles@ip-10-0-0-137 java]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Ddfs.block.size=64000000 -Dmapred.map.tasks=8 51200000 tgen512m

```
## The output of the time command
```

real    1m16.611s
user    1m8.824s
sys     0m4.770s

```

## The command and output of hdfs dfs -ls /user/raffles/tgen512m
```
[raffles@ip-10-0-0-137 java]$ hdfs dfs -ls /user/raffles/tgen512m
Found 2 items
-rw-r--r--   3 raffles raffles          0 2016-12-09 03:58 /user/raffles/tgen512m/_SUCCESS
-rw-r--r--   3 raffles raffles 5120000000 2016-12-09 03:58 /user/raffles/tgen512m/part-m-00000


## Show how many blocks are linked to this directory
```
[raffles@ip-10-0-0-137 java]$ hdfs fsck /user/raffles/tgen512m 2>/dev/null | grep 'Total blocks'
 Total blocks (validated):      80 (avg. block size 64000000 B)
```

