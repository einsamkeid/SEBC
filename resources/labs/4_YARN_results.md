### it takes a log time to execute. I don't no the reaseon.
### After I expended volume of cm (30G -> 100G)
```
[root@ip-10-0-0-73 ~]# bash ./test.sh
Testing loop started on Wed Dec 7 03:27:37 UTC 2016
Deleted /user/einsamkeid/yarntest/tg-10G-2-1-512
Deleted /user/einsamkeid/yarntest/ts-10GB-2-1-512
Deleted /user/einsamkeid/yarntest/tg-10G-2-1-1024
Deleted /user/einsamkeid/yarntest/ts-10GB-2-1-1024
Deleted /user/einsamkeid/yarntest/tg-10G-2-1-1536
Deleted /user/einsamkeid/yarntest/ts-10GB-2-1-1536
Deleted /user/einsamkeid/yarntest/tg-10G-2-2-512
Deleted /user/einsamkeid/yarntest/ts-10GB-2-2-512
Deleted /user/einsamkeid/yarntest/tg-10G-2-2-1024
Deleted /user/einsamkeid/yarntest/ts-10GB-2-2-1024
Deleted /user/einsamkeid/yarntest/tg-10G-2-2-1536
Deleted /user/einsamkeid/yarntest/ts-10GB-2-2-1536
Deleted /user/einsamkeid/yarntest/tg-10G-4-1-512
Deleted /user/einsamkeid/yarntest/ts-10GB-4-1-512
Deleted /user/einsamkeid/yarntest/tg-10G-4-1-1024
Deleted /user/einsamkeid/yarntest/ts-10GB-4-1-1024
Deleted /user/einsamkeid/yarntest/tg-10G-4-1-1536
Deleted /user/einsamkeid/yarntest/ts-10GB-4-1-1536
Deleted /user/einsamkeid/yarntest/tg-10G-4-2-512
Deleted /user/einsamkeid/yarntest/ts-10GB-4-2-512
Deleted /user/einsamkeid/yarntest/tg-10G-4-2-1024
Deleted /user/einsamkeid/yarntest/ts-10GB-4-2-1024
^CDeleted /user/einsamkeid/yarntest/tg-10G-4-2-1536
Deleted /user/einsamkeid/yarntest/ts-10GB-4-2-1536
Testing loop ended on Wed Dec 7 07:05:40 UTC 2016

```

## Fastest run
```
---------------------------------------
-               NEW RUN               -
---------------------------------------
-Dmapreduce.job.maps=2
-Dmapreduce.map.memory.mb=512
-Dmapreduce.map.java.opts.max.heap=409
-Dmapreduce.job.reduces=2
-Dmapreduce.reduce.java.opts.max.heap=409
TERAGEN time: 2:43.87 real,128.78 user,9.30 sys
TERASORT time: 15:48.53 real,786.45 user,180.97 sys
```

## Slowest run

```
---------------------------------------
-               NEW RUN               -
---------------------------------------
-Dmapreduce.job.maps=4
-Dmapreduce.map.memory.mb=1024
-Dmapreduce.map.java.opts.max.heap=819
-Dmapreduce.job.reduces=1
-Dmapreduce.reduce.java.opts.max.heap=819
TERAGEN time: 2:38.80 real,125.51 user,8.37 sys
TERASORT time: 17:23.23 real,877.38 user,179.46 sys

```