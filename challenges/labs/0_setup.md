## List the region, AMI ID, and OS you are using 
| key |value|
|---|---|
|Region|  Singapore|
|AMI ID| CentOS-6.5-GA-03.3 on EBS x86_64 20140204:2336|
|OS|CentOS 6.5 x64|

## List the volume space you have available on each node

```
[root@ip-10-0-0-137 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       7.9G  694M  6.8G  10% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[root@ip-10-0-0-137 ~]# resize2fs /dev/xvde
resize2fs 1.41.12 (17-May-2010)
Filesystem at /dev/xvde is mounted on /; on-line resizing required
old desc_blocks = 1, new_desc_blocks = 5
Performing an on-line resize of /dev/xvde to 20971520 (4k) blocks.
The filesystem on /dev/xvde is now 20971520 blocks long.

[root@ip-10-0-0-137 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        79G  704M   75G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm

```

```
[root@ip-10-0-0-138 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       7.9G  694M  6.8G  10% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[root@ip-10-0-0-138 ~]# resize2fs /dev/xvde
resize2fs 1.41.12 (17-May-2010)
Filesystem at /dev/xvde is mounted on /; on-line resizing required
old desc_blocks = 1, new_desc_blocks = 5
Performing an on-line resize of /dev/xvde to 20971520 (4k) blocks.
The filesystem on /dev/xvde is now 20971520 blocks long.

[root@ip-10-0-0-138 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        79G  704M   75G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm

```

```
[root@ip-10-0-0-139 ~]# resize2fs /dev/xvde
resize2fs 1.41.12 (17-May-2010)
Filesystem at /dev/xvde is mounted on /; on-line resizing                                  required
old desc_blocks = 1, new_desc_blocks = 5
Performing an on-line resize of /dev/xvde to 20971520 (4k)                                  blocks.
The filesystem on /dev/xvde is now 20971520 blocks long.

[root@ip-10-0-0-139 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        79G  704M   75G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm

```

```
[root@ip-172-30-0-17 centos]# df
[root@ip-10-0-0-140 ~]# resize2fs /dev/xvde
resize2fs 1.41.12 (17-May-2010)
Filesystem at /dev/xvde is mounted on /; on-line resizing                                  required
old desc_blocks = 1, new_desc_blocks = 5
Performing an on-line resize of /dev/xvde to 20971520 (4k)                                  blocks.
The filesystem on /dev/xvde is now 20971520 blocks long.

[root@ip-10-0-0-140 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        79G  704M   75G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm

```

```
[root@ip-10-0-0-141 ~]# resize2fs /dev/xvde
resize2fs 1.41.12 (17-May-2010)
Filesystem at /dev/xvde is mounted on /; on-line resizing                                  required
old desc_blocks = 1, new_desc_blocks = 5
Performing an on-line resize of /dev/xvde to 20971520 (4k)                                  blocks.
The filesystem on /dev/xvde is now 20971520 blocks long.

[root@ip-10-0-0-141 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        79G  704M   75G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm

```

## The command and output for yum repolist enabled

```

[root@ip-10-0-0-137 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirror.readyspace.com
 * extras: mirror.readyspace.com
 * updates: mirror.readyspace.com
repo id                           repo name                                     status
base                              CentOS-6 - Base                               6,696
extras                            CentOS-6 - Extras                                62
updates                           CentOS-6 - Updates                              686
repolist: 7,444
[root@ip-10-0-0-137 ~]#
```


## List the /etc/passwd entries for raffles and orchard in your setup file
```
[root@ip-10-0-0-137 ~]# egrep 'raffles|orchard' /etc/passwd
raffles:x:2700:2700::/home/raffles:/bin/bash
orchard:x:2800:2800::/home/orchard:/bin/bash
```

## List the /etc/group entries for shops and walks in your setup file
```
[root@ip-10-0-0-137 ~]# egrep 'walks|shops' /etc/group
shops:x:500:orchard
walks:x:501:raffles

```

