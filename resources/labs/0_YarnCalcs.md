### OS memery assigned too low for computation job
### default for OS memory is down : 10% => 5%
* now our job is computing oriented job
* Datanode and Datanode Memory ( 1G => 2G )
* other Services don't use (Impala, Solr, Hbase service is stopped)
* Application Master container is assigned ( 1mb => 1Gb )
* mappers is assigned ( 1gb => 4gb )

### What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
* Computing job is affected by workload factor
* Compute for IO time ratio
