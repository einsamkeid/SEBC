### Browse
```
http://54.254.211.76:7180/api/v2/cm/deployment
```

```
{
  "timestamp" : "2016-12-07T07:49:37.609Z",
  "clusters" : [ {
    "name" : "einsamkeid",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "920649728"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "920649728"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3571397427"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "601"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-10-0-0-73.ap-southeast-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-08d874b4a77874c9351a7824443176df",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-05acc850b52113ebd"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-371caa0bf5a6f25276c445f43e9742cf",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-037a5ce2efa90685e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-7a48e896bc73142888ed3bff08cdf7e1",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0e3bfa028e0f9406f"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-c87d277f62bfa30ec3b1f91678c0941f",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0c89c675e75ee1e20"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1v4udswy9rum8n0um4qay09zj"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "47m7huxf09tskpqkyci7lq54x"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-08d874b4a77874c9351a7824443176df",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-05acc850b52113ebd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "hxt6jvckdstucr5x1mjv4rp7"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-371caa0bf5a6f25276c445f43e9742cf",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-037a5ce2efa90685e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1kdsvqyq65my9kmx0jmqtpm6i"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-c87d277f62bfa30ec3b1f91678c0941f",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0c89c675e75ee1e20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3ihdbictodcsy5o32469x4r77"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-10-0-0-73.ap-southeast-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-ece44999254bda7280a5d05dcb9bcb52"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9phitj0lfgn3tcp2at5zqfkkj"
          }, {
            "name" : "secret_key",
            "value" : "HPNSFWNPSdOo9YouCcl6HAkY6TkKpf"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-10-0-0-73.ap-southeast-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "920649728"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cwo7n03ejh9fnuc4rsphhwotq"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3253"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "3253"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "AYPq9gLE4vTiSKuWXJwDVW5WRlE35V"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-7a48e896bc73142888ed3bff08cdf7e1",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-0e3bfa028e0f9406f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "79ix4n433lctitaauq6kw9dno"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-08d874b4a77874c9351a7824443176df",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-05acc850b52113ebd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "yiryskmy2u9yq86urqjk4l9i"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-371caa0bf5a6f25276c445f43e9742cf",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-037a5ce2efa90685e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6znimnxucnnrgdmsxrya39l3g"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-c87d277f62bfa30ec3b1f91678c0941f",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0c89c675e75ee1e20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9m4x7zza4bive9fxh71jmeky8"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-7a48e896bc73142888ed3bff08cdf7e1",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-0e3bfa028e0f9406f"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "50"
          }, {
            "name" : "role_jceks_password",
            "value" : "4gwzyjdoo8hfmiixiwl75ung4"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3170683699"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "sBCrZdp6NgONSdyKOPl9yJU2zfnxue"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "M6JCk50xvRc9RgFygbWFEdl8rBP76G"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "7niME7WGbxqw4smzrfxBKyrAjakHsB"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-7a48e896bc73142888ed3bff08cdf7e1",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-0e3bfa028e0f9406f"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-08d874b4a77874c9351a7824443176df",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-05acc850b52113ebd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5jh1sdtzjv88202lby1ocz8dk"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-371caa0bf5a6f25276c445f43e9742cf",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-037a5ce2efa90685e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cn53ku5a5c2t7tvf1ge4uu4du"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-c87d277f62bfa30ec3b1f91678c0941f",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0c89c675e75ee1e20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bl35xzgd319vqcoefoq9zkpbs"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-7a48e896bc73142888ed3bff08cdf7e1",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0e3bfa028e0f9406f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "43a9fhdtr7d5rdt63j16sjjla"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6tidjc73liyzbz5dbuwm36qcv"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "151t9s69q47u2jiyde1oqtd03"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-08d874b4a77874c9351a7824443176df",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-05acc850b52113ebd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3grr7oodm513dczd4zojtmuk1"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-371caa0bf5a6f25276c445f43e9742cf",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-037a5ce2efa90685e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2chx5o9vb9o2o35nrmq1s5dcb"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c87d277f62bfa30ec3b1f91678c0941f",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0c89c675e75ee1e20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "gw161kj8r481ab3a9p7k1nmn"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-7a48e896bc73142888ed3bff08cdf7e1",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0e3bfa028e0f9406f"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "52"
          }, {
            "name" : "role_jceks_password",
            "value" : "ayuko9s25ybqiu0uudp5gyffm"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-ece44999254bda7280a5d05dcb9bcb52",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0bb76cf5c3f6e59a0"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "927fs8cb4p3nwcedknamt5xa9"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0bb76cf5c3f6e59a0",
    "ipAddress" : "10.0.0.73",
    "hostname" : "ip-10-0-0-73.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9"
      } ]
    }
  }, {
    "hostId" : "i-0e3bfa028e0f9406f",
    "ipAddress" : "10.0.0.74",
    "hostname" : "ip-10-0-0-74.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-037a5ce2efa90685e",
    "ipAddress" : "10.0.0.75",
    "hostname" : "ip-10-0-0-75.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0c89c675e75ee1e20",
    "ipAddress" : "10.0.0.76",
    "hostname" : "ip-10-0-0-76.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-05acc850b52113ebd",
    "ipAddress" : "10.0.0.77",
    "hostname" : "ip-10-0-0-77.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__c938f140-bd43-4304-ba04-094da2257811",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "257ec96a1d2cab4f46d34d4f319a5e4fcf2eec5b1b478e4ec0c18f2c5b6c99bf",
    "pwSalt" : -14126784850053767,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-ece44999254bda7280a5d05dcb9bcb52",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "8af667722f574708203f272f02ebb50072abc2c0cbd72be95a36d0ab7d3322cb",
    "pwSalt" : 2651357402149755849,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-ece44999254bda7280a5d05dcb9bcb52",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1069fc2892b8d15a7b7d7198094f13f30777505f5a7a9e32e040fee3d90c61b1",
    "pwSalt" : -9172154136384109727,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-ece44999254bda7280a5d05dcb9bcb52",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7a7fcd5f31c23acbe310fc8ce8e7b5a7f0c8a6e1019d4f3e91cd5e145205c1d0",
    "pwSalt" : -3578288674928906070,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-ece44999254bda7280a5d05dcb9bcb52",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "87743177309120991b9b1f5493fff9621d40afea07a81c2cfa6cdc47fa692617",
    "pwSalt" : -2330800540736435337,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "3e7b7f55bc022cbf0bbd9546fb1538a358f63c84836785abf80f6200bfcb3cf3",
    "pwSalt" : -239706534202875362,
    "pwLogin" : true
  }, {
    "name" : "einsamkeid",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "cbfa817b64cdfc0fec8396d4fb8da81e7c8a8e13e62df0068bbdc34e7a05280a",
    "pwSalt" : 2177581293788398330,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "5f74a86f325d1aa5699d401fda87758f2942593754865c2b49992af69151fd84",
    "pwSalt" : 718609774559872654,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20160916-1426",
    "gitHash" : "d23c620f3a3bbd85d8511d6ebba49beaaab14b75",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "920649728"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-10-0-0-73.ap-southeast-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "920649728"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-ece44999254bda7280a5d05dcb9bcb52",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-0bb76cf5c3f6e59a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "a473pnkuf0jj5w75o9wo9v26v"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-ece44999254bda7280a5d05dcb9bcb52",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-0bb76cf5c3f6e59a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7h0e0kx3zzaglo8pcdaqi0es6"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-ece44999254bda7280a5d05dcb9bcb52",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-0bb76cf5c3f6e59a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3j03yty8pij51mzcvos2rkher"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-ece44999254bda7280a5d05dcb9bcb52",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-0bb76cf5c3f6e59a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d12afgzbwss6l4xmftwg77y4p"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-ece44999254bda7280a5d05dcb9bcb52",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-0bb76cf5c3f6e59a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3hdv4nabifwuan4vn2tjtiyv6"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/24/2012 4:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://10.0.0.73/cdh5.8/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```