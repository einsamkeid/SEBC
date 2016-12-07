## Stop Hive

```
[root@ip-10-0-0-73 ~]# curl -X POST -u "einsamkeid:cloudera" http://54.254.211.76:7180/api/v12/clusters/einsamkeid/services/hive/commands/stop
{
  "id" : 633,
  "name" : "Stop",
  "startTime" : "2016-12-07T07:59:18.900Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

```

## Start Hive

```
[root@ip-10-0-0-73 ~]# curl -X POST -u "einsamkeid:cloudera" http://54.254.211.76:7180/api/v12/custers/einsamkeid/services/hive/commands/start
{
  "id" : 637,
  "name" : "Start",
  "startTime" : "2016-12-07T08:01:01.433Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

## Check state of Hive
```
[root@ip-10-0-0-73 ~]# curl -s -X GET -u "einsamkeid:cloudera" http://54.254.211.76:7180/api/v12/clusters/einsamkeid/services/hive/ | grep serviceState
  "serviceState" : "STARTED",

```