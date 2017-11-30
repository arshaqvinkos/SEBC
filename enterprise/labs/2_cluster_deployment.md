```
{
  "timestamp" : "2017-11-30T17:33:09.585Z",
  "clusters" : [ {
    "name" : "Cluster_SEBC",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-5af92c16f38754096b1344ff116606e7",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6059erlgitmtlcjxy3fzcigea"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "f57g3uav9d2o48p0jz60qnuqq"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d3sfcnr3jsy6bmmal4832c6a8"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ec2-54-208-253-250.compute-1.amazonaws.com"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
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
        "name" : "oozie-OOZIE_SERVER-f2776cb674286694171bf004da0fcd00",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5mrp7ou2xjnypl9cgzr1uhilt"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ec2-54-208-253-250.compute-1.amazonaws.com"
        }, {
          "name" : "database_password",
          "value" : "hue_password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-f2776cb674286694171bf004da0fcd00"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-5af92c16f38754096b1344ff116606e7",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ahkpfk6p981w7gh6gofk8u5mu"
          } ]
        }
      }, {
        "name" : "hue-HUE_LOAD_BALANCER-9592a7b42b20fa021fd804726625dbb0",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "47zif4t0qqkefwjg90olcifjq"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-5af92c16f38754096b1344ff116606e7",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "05face2d-fb60-4801-afc8-20b945d4858a"
          }, {
            "name" : "role_jceks_password",
            "value" : "1r7kt5qhd3581f72o4y71h1ho"
          }, {
            "name" : "secret_key",
            "value" : "3F8XbTwM7gB7kQzVuqsW6sQ1XiJn7e"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-9592a7b42b20fa021fd804726625dbb0",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "02fda1f6-e898-442e-854c-087f5b554e29"
          }, {
            "name" : "role_jceks_password",
            "value" : "atnrycbr1yb435q20j84cko3l"
          }, {
            "name" : "secret_key",
            "value" : "qavKTtp5fcticU7scQEfUzxTayN4Ro"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-5af92c16f38754096b1344ff116606e7",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e9pamxtcr08rw92if29nefpob"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-9592a7b42b20fa021fd804726625dbb0",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bcjmlrtntit3kuz511zhpjx3q"
          } ]
        }
      } ],
      "displayName" : "Hue"
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
            "value" : "/data/disk0/dfs/dn,/data/disk1/dfs/dn"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "8441707724"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4296015872"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
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
            "value" : "/data/disk0/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/data/disk0/dfs/nn,/data/disk1/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/data/disk0/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "FQHeh4A7pUi8jA0rcfP60HBuuddLdz"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "K2huQ0iio4IaVsv09EMNBnJsqDIn3T"
        }, {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "lc9Vyi7fmue2DcWrCwyNEHKSW4LAh6"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-5af92c16f38754096b1344ff116606e7",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "86yyb1nbe2ml5cpamu82ccynm"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-9592a7b42b20fa021fd804726625dbb0",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "49bwg28acbbxozy4nl05zdon9"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4cqmkcrhwely24dgdbpkokwle"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-f2776cb674286694171bf004da0fcd00",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7po5q5pxicduxu8b517dmajmo"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-5af92c16f38754096b1344ff116606e7",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "35ukqc2kfpqv4f878lxq1bv7o"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7jlnu1peysplgeeynuz32fdjb"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-5af92c16f38754096b1344ff116606e7",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "91v24p30p2sq0otl6rizgfafe"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-9592a7b42b20fa021fd804726625dbb0",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_health_suppression_httpfs_scm_health",
            "value" : "true"
          }, {
            "name" : "role_jceks_password",
            "value" : "akwbbzwio102hy5g0709s0f68"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b7ah4n5my5ewpxzr6uuumablu"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-f2776cb674286694171bf004da0fcd00",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2uxqkjps1tk3vnxpubwd427lh"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-5af92c16f38754096b1344ff116606e7",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9kksmbb62pn50f8ymndltd2ct"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-9592a7b42b20fa021fd804726625dbb0",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bklgm9pwnencr3xolotpzm3i5"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4wtc3zzqc92mmxiiv5aj09pba"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-5af92c16f38754096b1344ff116606e7",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
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
            "value" : "71"
          }, {
            "name" : "role_jceks_password",
            "value" : "a2g2js4avfh7hf1qfp32bw2ic"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
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
            "value" : "92m8yduymummfzpjjyyuz9nha"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "16"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "container_executor_allowed_system_users",
            "value" : "nobody,impala,hive,llama,hbase,hdfs"
          }, {
            "name" : "container_executor_banned_users",
            "value" : "yarn,mapred,bin"
          }, {
            "name" : "container_executor_min_user_id",
            "value" : "995"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1600"
          }, {
            "name" : "rm_io_weight",
            "value" : "800"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/disk0/yarn/nm,/data/disk1/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/disk0/yarn/container-logs,/data/disk1/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "10350"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "17339"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6"
          } ]
        } ],
        "items" : [ {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "1e17zFxQWLKBeN5CDiJSvWFpnFt7Im"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1buj78norsshzgqjgmdpj8jc2"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-5af92c16f38754096b1344ff116606e7",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a647zwwmlfrtgiuprd70ws4nm"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ayupyeeoadzsevpiyft8jg6ui"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-f2776cb674286694171bf004da0fcd00",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9moqw823fx22gv5lc2hz9zc0m"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "59"
          }, {
            "name" : "role_jceks_password",
            "value" : "eh5ekri5p03c952up0v9e3hp2"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "4917821440"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "491782144"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2099878297"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "353"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ec2-54-208-253-250.compute-1.amazonaws.com"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "hive_proxy_user_groups_list",
          "value" : "hive,hue,sentry"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-5af92c16f38754096b1344ff116606e7",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-9592a7b42b20fa021fd804726625dbb0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-f2776cb674286694171bf004da0fcd00",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4mykvr3urp2o38gl0vhk8mftt"
          } ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-f2776cb674286694171bf004da0fcd00",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "49ux3pekykzihu8e9lw1wo6tq"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9w42l2aqy1cdmaa2gdv3dkfqe"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-f2776cb674286694171bf004da0fcd00",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dadu58p5s43n1emax39krdvog"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ec2-54-208-253-250.compute-1.amazonaws.com"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,hadoop"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-5af92c16f38754096b1344ff116606e7",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-9592a7b42b20fa021fd804726625dbb0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-9e48af3e0b1f24ea8bfef006a75faf49",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-GATEWAY-f2776cb674286694171bf004da0fcd00",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-61429cfdb282fcd85b656aae5a634bfb",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3hpvaxolu6rrfu7agdjdxfrhk"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1",
    "ipAddress" : "172.31.33.222",
    "hostname" : "ec2-34-235-121-19.compute-1.amazonaws.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "625c6d80-1ee8-473a-8d52-8ba920a5a1e7",
    "ipAddress" : "172.31.37.163",
    "hostname" : "ec2-52-203-1-93.compute-1.amazonaws.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "df1f3732-2615-49fd-b986-e519ed3d1109",
    "ipAddress" : "172.31.42.0",
    "hostname" : "ec2-52-90-234-250.compute-1.amazonaws.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "f10f2a88-b1f4-48de-9105-f223103dcd75",
    "ipAddress" : "172.31.46.60",
    "hostname" : "ec2-54-175-91-97.compute-1.amazonaws.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "6ca0ee89-2d3c-4279-9ad0-1d4743abb92e",
    "ipAddress" : "172.31.34.12",
    "hostname" : "ec2-54-208-253-250.compute-1.amazonaws.com",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-5af92c16f38754096b1344ff116606e7",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "b6277c191f6d4d64c272f981fa79e1248726fbcd35107de129a3d5a94e7f36c7",
    "pwSalt" : -8408080021087644553,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-9592a7b42b20fa021fd804726625dbb0",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "da675e98d92a7cb956f0e0eec55a869a69ac51b15452b3c6e28fb38ab04f1b4f",
    "pwSalt" : 1096070671362389291,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-61429cfdb282fcd85b656aae5a634bfb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7cf7593bca632961479b4fbb755a003f61e458412ef17ec7101ebc6025c72738",
    "pwSalt" : 9069094277792742005,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-61429cfdb282fcd85b656aae5a634bfb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "99fe65a34ee57f43c4e33ffd60bcea45600d3762308ac3c784ebd49a4b265771",
    "pwSalt" : -6698947212362208480,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-61429cfdb282fcd85b656aae5a634bfb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "59de9985c1a24a2590f3d6ab5a301831339e364d156fbdb419ded917c5899b7b",
    "pwSalt" : 300865518133958783,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-61429cfdb282fcd85b656aae5a634bfb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "5d66be4498943ba82536b87e57e03e408690dc9e599c1b33a850cfe42249bea0",
    "pwSalt" : 4992491856295365430,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "988af0550d100ccd004de24b2f92b979e02ad53249cf7a10eac8c5599e56c8a3",
    "pwSalt" : -6177056800173986312,
    "pwLogin" : true
  }, {
    "name" : "arshaqvinkos",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "cde9e8b501b7f57587be9150dd4b71e08103139b0a8b3ffcb41ee2a16acc4d2a",
    "pwSalt" : 3744737970226591481,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "a55d185d746a2bef7bd1895ccaddf0c2c4f795a433eb322a1abca8f97a5d9fd2",
    "pwSalt" : -3056702974663076959,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.12.1",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170818-0807",
    "gitHash" : "9bdee611802535491d400e03c98ef694a2c77d0a",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ec2-54-208-253-250.compute-1.amazonaws.com"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
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
      "name" : "mgmt-ALERTPUBLISHER-61429cfdb282fcd85b656aae5a634bfb",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "enscw2sxtnrea38uhql26p510"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-61429cfdb282fcd85b656aae5a634bfb",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ajqmtp6wqkmsrw58t36at03fa"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-61429cfdb282fcd85b656aae5a634bfb",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ey0wr05es1v1u6zzv55cqh673"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-61429cfdb282fcd85b656aae5a634bfb",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ell4m8rw5l2txivhajsem9e2m"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-61429cfdb282fcd85b656aae5a634bfb",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "5806465c-fa2f-4a68-804d-c51b61e805a1"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3vxpaw6l3sbnwmc0o092508jf"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/21/2012 19:10"
    }, {
      "name" : "KDC_ADMIN_HOST",
      "value" : "ec2-54-208-253-250.compute-1.amazonaws.com"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA9AAEAClZJTktPUy5DT00ADGNsb3VkZXJhLXNjbQAAAAFaHueGAQAXABD5AR9JT3btIU0Gm5QjaBRVAAAAAQ=="
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@VINKOS.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "ec2-54-208-253-250.compute-1.amazonaws.com"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/,http://ec2-54-208-253-250.compute-1.amazonaws.com/wheezy/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "VINKOS.COM"
    } ]
    ```
  }
}