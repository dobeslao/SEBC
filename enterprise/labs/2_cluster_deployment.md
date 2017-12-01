# API Call ./api/v2/cm/deployment

```
{
  "timestamp" : "2017-11-29T10:13:62.124Z",
  "clusters" : [ {
    "name" : "Cluster 1",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_enable_db_notification",
            "value" : "true"
          }, {
            "name" : "hive_metastore_java_heapsize",
            "value" : "5454692352"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "545469235"
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
            "value" : "3013895782"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "507"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-22-38.ec2.internal"
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
          "name" : "hive_service_config_safety_valve",
          "value" : "<property><name>hive.server2.authentication</name><value>KERBEROS</value></property>\n<property>  <name>hive.server2.authentication.kerberos.principal</name> <value>hive/ip-172-31-24-52.ec2.internal@VINKOS.COM</value></property>\n<property> <name>hive.stats.ndv.error</name> <value>5.0</value></property>\n"
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
        "name" : "hive-GATEWAY-35812a9edba9b2239c57dce1004e1e38",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-5147e609303aee1163da6b5a982396a5",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9khjix0809iwk4rtzlzz9fdhp"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9ghrvvb374qrs3m9e7ox3edfl"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
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
        "name" : "zookeeper-SERVER-35812a9edba9b2239c57dce1004e1e38",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9kqpuaps2urzhzxovhn4z455b"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2z05kzfqviw62s7rv7po5ff39"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1xmytie4sra3zhxkmc0owdrem"
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
          "value" : "ip-172-31-22-38.ec2.internal"
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
          "value" : "hdfs-HTTPFS-7dfcef43b14e331d1982a8d7e1ad3082"
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
        "name" : "hue-HUE_LOAD_BALANCER-5147e609303aee1163da6b5a982396a5",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4vjn0vnvgs7pmr92dolynexf"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-5147e609303aee1163da6b5a982396a5",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "37d730f4-7ebe-46bc-8284-2febe5a038ef"
          }, {
            "name" : "role_jceks_password",
            "value" : "8hij79dtbe1wvvryt35im6o0u"
          }, {
            "name" : "secret_key",
            "value" : "r4APzhTtI1FX4twrqfVK3d49FCSk70"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "0621abe8-d593-4841-9710-ce27ea10303f"
          }, {
            "name" : "role_jceks_password",
            "value" : "492llu196nx1ffvzejb18gmbn"
          }, {
            "name" : "secret_key",
            "value" : "Q55FWmIzBuvtyrz9H52iBDlQ9Lj56l"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-5147e609303aee1163da6b5a982396a5",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7rxnzlcb39b88vgaadjasceyf"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9z0co5bl1wx0vlwqbqiw6wdyj"
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
            "value" : "ip-172-31-22-38.ec2.internal"
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
        "name" : "oozie-OOZIE_SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6so2rlt22985pr4tj2gbgbpiw"
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
            "value" : "16"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/disk0/yarn/nm,/data/disk1/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/disk0/yarn/container-logs,/data/disk1/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "9865"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "16189"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "8"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "7X2vBEYKesbiGptWYowvL5r3FCzvch"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ccx6o96exae0z3o3e4eb45itp"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-5147e609303aee1163da6b5a982396a5",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bbdko0abwump17izpxjfgyz2k"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eevfbq1t5dzt1jm0adm6tuejj"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2f6gdz1l2f2hg1jmbbhjt5f1o"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "azu65ujbasjgvh5mlmi1fjs2e"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "53"
          }, {
            "name" : "role_jceks_password",
            "value" : "8o5x0sq6jfvansh8epra8o2o7"
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
            "name" : "dfs_datanode_port",
            "value" : "1004"
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
            "value" : "/data/jn"
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
          "name" : "dfs_block_size",
          "value" : "268435456"
        }, {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "eccjgEvRHhhDrmPM0WhnvTXSYLDGdB"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "TyQEF8IAJxCmY3wLeJM1jKZIPhOKRK"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "OnlHrLq8tpK6gNg0TKMs3Syz8SXFIM"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-5147e609303aee1163da6b5a982396a5",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a1c9oc2aug0yalfq0lyfqs0j7"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "44mnufcah3rovrhqp62dyv6yw"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "25h6lx667pj0gh5m021vmqbjn"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dshn5zhh1waatnsd6sjxud31j"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-35812a9edba9b2239c57dce1004e1e38",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "57dmct2b5q1zeih5l9bs9k5ze"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ci6e0ej0ze6vgg8o3nq9m618"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bdxkcm4s7ogn92o5jtgu02482"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-35812a9edba9b2239c57dce1004e1e38",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dtzftkg9o9qkndox5r06lli2i"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8qtr8ojid9q93afw17k7ibqni"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dywdgeyfsp047ymh6dbqnfwm1"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-35812a9edba9b2239c57dce1004e1e38",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
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
            "value" : "61"
          }, {
            "name" : "role_jceks_password",
            "value" : "4imjlq2ftkontmv49elormh63"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
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
            "value" : "55"
          }, {
            "name" : "role_jceks_password",
            "value" : "189vzgosooa5x0qb78vsdqy41"
          } ]
        }
      } ],
      "displayName" : "HDFS"
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
          "value" : "ip-172-31-22-38.ec2.internal"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,dobeslao"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-35812a9edba9b2239c57dce1004e1e38",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7wg3hspx3l58ncqd5822vzbb6"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2",
    "ipAddress" : "172.31.18.127",
    "hostname" : "ip-172-31-18-127.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd",
    "ipAddress" : "172.31.17.126",
    "hostname" : "ip-172-31-17-126.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6",
    "ipAddress" : "172.31.26.122",
    "hostname" : "ip-172-31-26-122.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d",
    "ipAddress" : "172.31.29.75",
    "hostname" : "ip-172-31-24-52.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf",
    "ipAddress" : "172.31.30.26",
    "hostname" : "ip-172-31-22-38.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "b656c428363a9cd17b9a01ba7e5f6d46aed18d5622339c6c993fdbca56ddb3d3",
    "pwSalt" : -7960178241060479133,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "a2e91148d6fca6df19a0914cf27788c940d567d8faab44234d03a5c36c60bad2",
    "pwSalt" : 6093032718641343622,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "9c1ffa470c57e388021f3e8cca47478587657f7c4eb097d4322127cf368a4150",
    "pwSalt" : -2767860179583090069,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ac70d26eef1b9e677f5bd67e63582ddbf32e306989a51c638a278473887288fb",
    "pwSalt" : 1784663776125803710,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "956e03e2661e058976584bdf3fd138d48f8a4aa982e7b7388978d2fa65465334",
    "pwSalt" : 1639009620632732889,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "45b54a3aea635dd2bfef4f36b79e924fedfed0f29afaf23b4db0fdfef60ac901",
    "pwSalt" : -611183836882923071,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "154c75b86b1488ee6918c20a1e23c0e34d973dc4c77d46451efef274147ec5f6",
    "pwSalt" : -1603343470102836567,
    "pwLogin" : true
  }, {
    "name" : "dobeslao",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "f42df10f5c6f8811c2f7838c247e25ba948ca1a268f587005debf4b3e229e226",
    "pwSalt" : -8584677058958715444,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "e05ff550d7e5232205e1321f31ce7ef39132fb3209962bf15d42c89a686dc877",
    "pwSalt" : 1724677452638589553,
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
          "value" : "ip-172-31-22-38.ec2.internal"
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
      "name" : "mgmt-ALERTPUBLISHER-5147e609303aee1163da6b5a982396a5",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8of0lcj6ghyj58pghlqx3x2cp"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-5147e609303aee1163da6b5a982396a5",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "654ugz01zre7yehkcym84bdw7"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-5147e609303aee1163da6b5a982396a5",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3xejkiys48vv41tp2o342jsbu"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-5147e609303aee1163da6b5a982396a5",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5sz29m23j2wz93qgwkfuehn56"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-5147e609303aee1163da6b5a982396a5",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "14vo93kra17xtvkdwomfzvzfs"
        } ]
      }
    } ],
    "displayName" : "Dobeslao Hernandez"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 2:10"
    }, {
      "name" : "KDC_ADMIN_HOST",
      "value" : "ip-172-31-22-38.ec2.internal"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA9AAEAClZJTktPUy5DT00ADGNsb3VkZXJhLXNjbQAAAAFaHvJ8AQAXABCIRvfq7o+xF60Gvdgwt1hsAAAAAQ=="
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@VINKOS.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-31-22-38.ec2.internal"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "MAX_RENEW_LIFE",
      "value" : "604800"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://ip-172-31-22-38.ec2.internal/parcels/cdh5/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,http://ip-172-31-22-38.ec2.internal/parcels/spark2/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "VINKOS.COM"
    } ]
  }
}
```
