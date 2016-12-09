## Command and output for hdfs dfs -ls /user
```
[root@ip-10-0-0-137 java]# hdfs dfs -ls /user
Found 6 items
drwxrwxrwx   - mapred  hadoop           0 2016-12-09 03:46 /user/history
drwxrwxr-t   - hive    hive             0 2016-12-09 03:46 /user/hive
drwxrwxr-x   - hue     hue              0 2016-12-09 03:47 /user/hue
drwxrwxr-x   - oozie   oozie            0 2016-12-09 03:47 /user/oozie
drwxr-xr-x   - orchard orchard          0 2016-12-09 03:50 /user/orchard
drwxr-xr-x   - raffles raffles          0 2016-12-09 03:50 /user/raffles

```


## The output from the CM API call ../api/v14/hosts
```
[root@ip-10-0-0-137 java]# curl -X GET -u  "admin:admin" http://54.254.138.127:7180/api/v14/hosts
{
  "items" : [ {
    "hostId" : "i-0c2540dbbffba7606",
    "ipAddress" : "10.0.0.137",
    "hostname" : "ip-10-0-0-137.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-0-0-137.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-0c2540dbbffba7606",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "i-00470ff0bf519092f",
    "ipAddress" : "10.0.0.138",
    "hostname" : "ip-10-0-0-138.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-0-0-137.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-00470ff0bf519092f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "i-0e02784e6365c8440",
    "ipAddress" : "10.0.0.139",
    "hostname" : "ip-10-0-0-139.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-0-0-137.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-0e02784e6365c8440",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "i-02d02633752a54d5b",
    "ipAddress" : "10.0.0.140",
    "hostname" : "ip-10-0-0-140.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-0-0-137.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-02d02633752a54d5b",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "i-0431d2a3d9c82a956",
    "ipAddress" : "10.0.0.141",
    "hostname" : "ip-10-0-0-141.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-0-0-137.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-0431d2a3d9c82a956",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  } ]
}[root@ip-10-0-0-137 java]#

```