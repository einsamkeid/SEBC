## Report the latest available version of the API
```
[root@ip-10-0-0-73 ~]# curl -X GET -u  "einsamkeid:cloudera" http://54.254.211.76:7180/api/version
v14
```

## Report the CM version
```
[root@ip-10-0-0-73 ~]# curl -s GET -u  "einsamkeid:cloudera" http://54.254.211.76:7180/api/v14/cm/version | grep version
  "version" : "5.9.0",

```

## List all CM users
```
[root@ip-10-0-0-73 ~]# curl -s GET -u  "einsamkeid:cloudera" http://54.254.211.76:7180/api/v14/users
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "einsamkeid",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```
## Report the database server in use by CM
```
[root@ip-10-0-0-73 ~]# curl -s GET -u  "einsamkeid:cloudera" http://54.254.211.76:7180/api/v14/cm/log 2>&1 | grep -o 'jdbcUrl":"[^"]*'
jdbcUrl":"jdbc:mysql://localhost/scm?useUnicode=true&characterEncoding=UTF-8


```