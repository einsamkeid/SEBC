## 1. Check `vm.swappiness` on all your nodes

### Checking current vm.swappiness value
```
[root@ip-10-0-0-213 ~]# cat /proc/sys/vm/swappiness
60
```

### Making it to be ```1``` (effective at next reboot)
```
[root@ip-10-0-0-213 ~]# echo 'vm.swappiness=1' >> /etc/sysctl.conf
```

### Making it to be ```1``` (immedeately)
```
[root@ip-10-0-0-213 ~]# echo 1 > /proc/sys/vm/swappiness
```

### Checking current value again after reboot
```
[root@ip-10-0-0-213 ~]# cat /proc/sys/vm/swappiness
1
```

## 2. Show the mount attributes of all volumes

```
[root@ip-10-0-0-213 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       7.9G  650M  6.9G   9% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
```

## 3. Show the reserve space of any non-root, ext-based volumes

There are no non-root ext-based volumes

## 4. Show that transparent hugepages is disabled

## 5. Report the network interface attributes
```
[root@ip-10-0-0-213 ~]# ip route
10.0.0.0/24 dev eth0  proto kernel  scope link  src 10.0.0.213
169.254.0.0/16 dev eth0  scope link  metric 1002
default via 10.0.0.1 dev eth0
```

```
[root@ip-10-0-0-213 ~]# ifconfig eth0
eth0      Link encap:Ethernet  HWaddr 02:F5:1F:A4:B5:B7
          inet addr:10.0.0.213  Bcast:10.0.0.255  Mask:255.255.255.0
          inet6 addr: fe80::f5:1fff:fea4:b5b7/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:1390 errors:0 dropped:0 overruns:0 frame:0
          TX packets:1070 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:118225 (115.4 KiB)  TX bytes:154142 (150.5 KiB)
          Interrupt:24
```

```
[root@ip-10-0-0-213 ~]# cat /etc/sysconfig/network-scripts/ifcfg-eth0
DEVICE=eth0
BOOTPROTO=dhcp
ONBOOT=on
```
## 6. Show forward and reverse host lookups using `getent` and `nslookup`

### getent
 
#### forward host lookups
```
root@ip-10-0-0-213 ~]# getent hosts ip-10-0-0-212
10.0.0.212      ip-10-0-0-212.ap-southeast-1.compute.internal ip-10-0-0-212
```

#### reverse host lookups
```
[root@ip-10-0-0-213 ~]# getent hosts 10.0.0.212
10.0.0.212      ip-10-0-0-212.ap-southeast-1.compute.internal ip-10-0-0-212
```

### forward host lookups
```
[root@ip-10-0-0-213 ~]# nslookup ip-10-0-0-213.ap-southeast-1.compute.internal
Server:         10.0.0.2
Address:        10.0.0.2#53

Non-authoritative answer:
Name:   ip-10-0-0-213.ap-southeast-1.compute.internal
Address: 10.0.0.213
```

### reverse host lookups
```
[root@ip-10-0-0-213 ~]# nslookup 10.0.0.212
Server:         10.0.0.2
Address:        10.0.0.2#53

Non-authoritative answer:
212.0.0.10.in-addr.arpa name = ip-10-0-0-212.ap-southeast-1.compute.internal.

Authoritative answers can be found from:
```

## 7. Verify the <code>nscd</code> service is running


### Install and start `nscd`
```
[root@ip-10-0-0-213 ~]# yum -y install nscd; chkconfig nscd on; service nscd start;
```
### Check if the service will start at next reboot
```
[root@ip-10-0-0-213 ~]# chkconfig --list nscd
nscd            0:off   1:off   2:on    3:on    4:on    5:on    6:off
```
### Check `nscd` status
```
[root@ip-10-0-0-213 ~]# service nscd status
nscd (pid 4628) is running...

[root@ip-10-0-0-213 ~]# nscd -g | grep 'number of cached values'
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
root@ip-10-0-0-213 ~]# yum -y install ntp ntpdate; chkconfig ntpd on; service ntpd start;

```

### List `ntp` servers and their known states
```
[root@ip-10-0-0-213 ~]# ntpq -p
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
-188.166.245.58  107.56.218.242   3 u    9   64    3    0.702    0.283   0.269
+ntp01.cosmicflu 27.114.150.13    3 u   11   64    3    0.836  -21.412   0.167
*210.23.25.77    .GPS.            1 u   12   64    3   46.179  -24.583   1.707
+ec2-52-220-0-87 118.189.138.5    2 u   76   64    2    1.290  -12.138   0.001
```










