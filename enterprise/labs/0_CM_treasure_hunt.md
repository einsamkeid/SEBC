## What is ubertask optimization?
Uber jobs run in a single container (Application Master's) without firing up any additional mapper of reducer containers. They are ideal for jobs that will run for a short duration. At least in theory. 
## Where in CM is the Kerberos Security Realm value displayed?
Search for "default_realm" in the CM searchbox
default_realm = HADOOP.COM
## Which CDH service(s) host a property for enabling Kerberos authentication?
HDFS, YARN, Zookeeper, Solr, Impala, HBase
## How do you upgrade the CM agents?
 Changing CM OS repo and manully upgrading them using the package manager of the OS
 After a CM upgrade, CM will prompt you to automatically upgrade CM agents
## Give the tsquery statement used to chart Hue's CPU utilization?
```
select cpu_user_rate + cpu_system_rate where roleType=HUE_SERVER
```
## Name all the roles that make up the Hive service
* Hive metastore
* HiveServer2
* WebHCat Server
* Hive gateway (client config)

## What steps must be completed before integrating Cloudera Manager with Kerberos?
* Make the communication between CM and CM agents secure 
* Working KDC (AD or MIT)
* JDKs with unlimited strength encryption
* Client libraries on all Hadoop nodes
* KDC should be configured for renewable tickets
* Need to create an admin principal for Cloudera Manager