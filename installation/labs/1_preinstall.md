## 1. Check `vm.swappiness` on all your nodes

### Checking current vm.swappiness value
```
[root@ip-10-0-0-73 ~]# cat /proc/sys/vm/swappiness
60
```

### Making it to be ```1``` (effective at next reboot)
```
[root@ip-10-0-0-73 ~]# echo 'vm.swappiness=1' >> /etc/sysctl.conf
```

### Making it to be ```1``` (immedeately)
```
[root@ip-10-0-0-73 ~]# echo 1 > /proc/sys/vm/swappiness
```

### Checking current value again after reboot
```
[root@ip-10-0-0-73 ~]# cat /proc/sys/vm/swappiness
1
```

## 2. Show the mount attributes of all volumes

```
[root@ip-10-0-0-73 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        30G   12G   17G  43% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
cm_processes    7.4G   18M  7.4G   1% /var/run/cloudera-scm-agent/process

```

## 3. Show the reserve space of any non-root, ext-based volumes

There are no non-root ext-based volumes

## 4. Show that transparent hugepages is disabled


## 5. Report the network interface attributes
```
[root@ip-10-0-0-73 ~]# ip route
10.0.0.0/24 dev eth0  proto kernel  scope link  src 10.0.0.73
169.254.0.0/16 dev eth0  scope link  metric 1002
default via 10.0.0.1 dev eth0

```

```
[root@ip-10-0-0-73 ~]# ifconfig eth0
eth0      Link encap:Ethernet  HWaddr 02:10:15:47:DA:1B
          inet addr:10.0.0.73  Bcast:10.0.0.255  Mask:255.255.255.0
          inet6 addr: fe80::10:15ff:fe47:da1b/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:4105174 errors:0 dropped:0 overruns:0 frame:0
          TX packets:1153782 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:5703393172 (5.3 GiB)  TX bytes:2901339199 (2.7 GiB)
          Interrupt:24
```

```
[root@ip-10-0-0-73 ~]# cat /etc/sysconfig/network-scripts/ifcfg-eth0
DEVICE=eth0
BOOTPROTO=dhcp
ONBOOT=on

```
## 6. Show forward and reverse host lookups using `getent` and `nslookup`

### getent
 
#### forward host lookups
```
[root@ip-10-0-0-73 ~]# getent hosts ip-10-0-0-73
10.0.0.73       ip-10-0-0-73.ap-southeast-1.compute.internal ip-10-0-0-73

```

#### reverse host lookups
```
[root@ip-10-0-0-73 ~]# getent hosts 10.0.0.73
10.0.0.73       ip-10-0-0-73.ap-southeast-1.compute.internal ip-10-0-0-73

```

### forward host lookups
```
[root@ip-10-0-0-73 ~]# nslookup ip-10-0-0-73.ap-southeast-1.compute.internal
Server:         10.0.0.2
Address:        10.0.0.2#53

Non-authoritative answer:
Name:   ip-10-0-0-73.ap-southeast-1.compute.internal
Address: 10.0.0.73
```

### reverse host lookups
```
[root@ip-10-0-0-73 ~]# nslookup 10.0.0.73
Server:         10.0.0.2
Address:        10.0.0.2#53

Non-authoritative answer:
73.0.0.10.in-addr.arpa  name = ip-10-0-0-73.ap-southeast-1.compute.internal.

Authoritative answers can be found from:
```

## 7. Verify the <code>nscd</code> service is running


### Install and start `nscd`
```
[root@ip-10-0-0-73 ~]# yum -y install nscd; chkconfig nscd on; service nscd start;
```
### Check if the service will start at next reboot
```
[root@ip-10-0-0-73 ~]# chkconfig --list nscd
nscd            0:off   1:off   2:on    3:on    4:on    5:on    6:off
```
### Check `nscd` status
```
[root@ip-10-0-0-73 ~]# service nscd status
nscd (pid 4628) is running...

[root@ip-10-0-0-73 ~]# nscd -g | grep 'number of cached values'
              2  current number of cached values
              2  maximum number of cached values
             14  current number of cached values
             14  maximum number of cached values
              4  current number of cached values
              4  maximum number of cached values
              1  current number of cached values
              1  maximum number of cached values
              0  current number of cached values
              0  maximum number of cached values
```

# 8. Verify the <code>ntpd</code> service is running<br>
### Install and start `ntpd`
```
root@ip-10-0-0-73 ~]# yum -y install ntp ntpdate; chkconfig ntpd on; service ntpd start;
```

### List `ntp` servers and their known states
```
[root@ip-10-0-0-73 ~]# ntpq -p
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
+233.176.146.58. .PPS.            1 u  265  512  377    5.563   -3.279   3.151
*time2.maxonline .GPS.            1 u  485  512  377    2.670   -1.802   0.571
-gandhari.thirde 80.94.65.10      2 u  408  512  377    0.510    3.160   0.070
+ntpmon.dcs1.biz .PPS.            1 u  498  512  377    6.815   -1.624  13.648
```










