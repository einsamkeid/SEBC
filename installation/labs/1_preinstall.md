## 1. Check `vm.swappiness` on all your nodes

### Checking current vm.swappiness value
```
[root@ip-10-0-0-122 ~]# cat /proc/sys/vm/swappiness
60
```

### Making it to be ```1``` (effective at next reboot)
```
[root@ip-10-0-0-122 ~]# echo 'vm.swappiness=1' >> /etc/sysctl.conf
```

### Making it to be ```1``` (immedeately)
```
[root@ip-10-0-0-122 ~]# echo 1 > /proc/sys/vm/swappiness
```

### Checking current value again after reboot
```
[root@ip-10-0-0-122 ~]# cat /proc/sys/vm/swappiness
1
```

## 2. Show the mount attributes of all volumes

```
[root@ip-10-0-0-122 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       7.9G  650M  6.9G   9% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
```

## 3. Show the reserve space of any non-root, ext-based volumes

There are no non-root ext-based volumes

## 4. Show that transparent hugepages is disabled


## 5. Report the network interface attributes
```
[root@ip-10-0-0-122 ~]# ip route
10.0.0.0/24 dev eth0  proto kernel  scope link  src 10.0.0.122
169.254.0.0/16 dev eth0  scope link  metric 1002
default via 10.0.0.1 dev eth0
```

```
[root@ip-10-0-0-122 ~]# ifconfig eth0
eth0      Link encap:Ethernet  HWaddr 02:73:7D:39:F2:63
          inet addr:10.0.0.122  Bcast:10.0.0.255  Mask:255.255.255.0
          inet6 addr: fe80::73:7dff:fe39:f263/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:529728 errors:0 dropped:0 overruns:0 frame:0
          TX packets:68551 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:765757554 (730.2 MiB)  TX bytes:5169889 (4.9 MiB)
          Interrupt:24

```

```
[root@ip-10-0-0-122 ~]# cat /etc/sysconfig/network-scripts/ifcfg-eth0
DEVICE=eth0
BOOTPROTO=dhcp
ONBOOT=on

```
## 6. Show forward and reverse host lookups using `getent` and `nslookup`

### getent
 
#### forward host lookups
```
[root@ip-10-0-0-122 ~]# getent hosts ip-10-0-0-212
10.0.0.212      ip-10-0-0-212.ap-southeast-1.compute.internal

```

#### reverse host lookups
```
[root@ip-10-0-0-122 ~]# getent hosts 10.0.0.122
10.0.0.122      ip-10-0-0-122.ap-southeast-1.compute.internal ip-10-0-0-122

```

### forward host lookups
```
[root@ip-10-0-0-122 ~]# nslookup ip-10-0-0-126.ap-southeast-1.compute.internal
Server:         10.0.0.2
Address:        10.0.0.2#53

Non-authoritative answer:
Name:   ip-10-0-0-126.ap-southeast-1.compute.internal
Address: 10.0.0.126

```

### reverse host lookups
```
[root@ip-10-0-0-122 ~]# nslookup 10.0.0.122
Server:         10.0.0.2
Address:        10.0.0.2#53

Non-authoritative answer:
122.0.0.10.in-addr.arpa name = ip-10-0-0-122.ap-southeast-1.compute.internal.

Authoritative answers can be found from:

```

## 7. Verify the <code>nscd</code> service is running


### Install and start `nscd`
```
[root@ip-10-0-0-122 ~]# yum -y install nscd; chkconfig nscd on; service nscd start;
```
### Check if the service will start at next reboot
```
[root@ip-10-0-0-122 ~]# chkconfig --list nscd
nscd            0:off   1:off   2:on    3:on    4:on    5:on    6:off
```
### Check `nscd` status
```
[root@ip-10-0-0-122 ~]# service nscd status
nscd (pid 4628) is running...

[root@ip-10-0-0-122 ~]# nscd -g | grep 'number of cached values'
              4  current number of cached values
              4  maximum number of cached values
              0  current number of cached values
              0  maximum number of cached values
              0  current number of cached values
              0  maximum number of cached values
              0  current number of cached values
              0  maximum number of cached values
              0  current number of cached values
              0  maximum number of cached values

```

# 8. Verify the <code>ntpd</code> service is running<br>
### Install and start `ntpd`
```
root@ip-10-0-0-122 ~]# yum -y install ntp ntpdate; chkconfig ntpd on; service ntpd start;

```

### List `ntp` servers and their known states
```
[root@ip-10-0-0-122 ~]# ntpq -p
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
+ntpmon.dcs1.biz .PPS.            1 u   68  256  377   51.217  -30.553   3.591
x210.23.18.200   .PPS.            1 u   75  256  377   50.262  -31.268   3.709
+233.176.146.58. .PPS.            1 u  129  256  377    8.636  -14.650   3.033
*fnet70-f101-acc .GPS.            1 u  179  256  377    4.333   -7.777   4.278

```










