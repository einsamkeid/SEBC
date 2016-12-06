# Choose a partner in class
one cluster distcp test

i tried to connect my partner but he is using company system
i can't connect his system

# Use teragen to create a 500 MB file
```
[root@ip-10-0-0-73 ~]# sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teran 5000000 /user/hdfs/source
```
# Use distcp
```
[root@ip-10-0-0-73 ~]# sudo -u hdfs hadoop fs -ls source
Found 2 items
-rw-r--r--   3 hdfs supergroup          0 2016-12-06 06:50 source/_SUCCESS
-rw-r--r--   3 hdfs supergroup  500000000 2016-12-06 06:50 source/part-m-00000

[root@ip-10-0-0-73 ~]# sudo -u hdfs hadoop distcp hdfs://ec2-54-254-240-137.ap-southeast-1.compute.amazonaws.com:8020/user/hdfs/source/ hdfs://ec2-54-254-240-137.ap-southeast-1.compute.amazonaws.com:8020/user/hdfs/target/

[root@ip-10-0-0-73 ~]# sudo -u hdfs hadoop fs -ls
Found 2 items
drwxr-xr-x   - hdfs supergroup          0 2016-12-06 06:50 source
drwxr-xr-x   - hdfs supergroup          0 2016-12-06 07:43 target
 ```
 
# source hdfs fsck <path> -files -blocks
```
[root@ip-10-0-0-73 ~]# sudo -u hdfs hdfs fsck /user/hdfs/source -files -blocks
Connecting to namenode via http://ip-10-0-0-74.ap-southeast-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /10.0.0.73 for path /user/hdfs/source at Tue Dec 06 07:53:49 UTC 2016
/user/hdfs/source <dir>
/user/hdfs/source/_SUCCESS 0 bytes, 0 block(s):  OK

/user/hdfs/source/part-m-00000 500000000 bytes, 4 block(s):  OK
0. BP-448683908-10.0.0.74-1481001278398:blk_1073742613_1789 len=134217728 Live_repl=3
1. BP-448683908-10.0.0.74-1481001278398:blk_1073742614_1790 len=134217728 Live_repl=3
2. BP-448683908-10.0.0.74-1481001278398:blk_1073742615_1791 len=134217728 Live_repl=3
3. BP-448683908-10.0.0.74-1481001278398:blk_1073742617_1793 len=97346816 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 125000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Dec 06 07:53:49 UTC 2016 in 3 milliseconds

```
# target hdfs fsck <path> -files -blocks
```
[root@ip-10-0-0-73 ~]# sudo -u hdfs hdfs fsck /user/hdfs/target -files -blocks
Connecting to namenode via http://ip-10-0-0-74.ap-southeast-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /10.0.0.73 for path /user/hdfs/target at Tue Dec 06 07:56:43 UTC 2016
/user/hdfs/target <dir>
/user/hdfs/target/_SUCCESS 0 bytes, 0 block(s):  OK

/user/hdfs/target/part-m-00000 500000000 bytes, 4 block(s):  OK
0. BP-448683908-10.0.0.74-1481001278398:blk_1073742669_1845 len=134217728 Live_repl=3
1. BP-448683908-10.0.0.74-1481001278398:blk_1073742670_1846 len=134217728 Live_repl=3
2. BP-448683908-10.0.0.74-1481001278398:blk_1073742671_1847 len=134217728 Live_repl=3
3. BP-448683908-10.0.0.74-1481001278398:blk_1073742672_1848 len=97346816 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 125000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Dec 06 07:56:43 UTC 2016 in 1 milliseconds


The filesystem under path '/user/hdfs/target' is HEALTHY
```