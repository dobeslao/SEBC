# Install CDH 5.9

## The command and output for hdfs dfs -ls /user

```
[root@ip-172-31-30-84 ~]# sudo -u hdfs hdfs dfs -ls /user
Found 7 items
drwxr-xr-x   - hdfs   supergroup          0 2017-12-01 12:05 /user/haley
drwxrwxrwx   - mapred hadoop              0 2017-12-01 11:59 /user/history
drwxrwxr-t   - hive   hive                0 2017-12-01 12:00 /user/hive
drwxrwxr-x   - hue    hue                 0 2017-12-01 12:01 /user/hue
drwxrwxr-x   - oozie  oozie               0 2017-12-01 12:01 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2017-12-01 12:05 /user/saturn
drwxr-x--x   - spark  spark               0 2017-12-01 11:59 /user/spark
```


## The command and output from the CM API call ../api/v14/hosts

```
curl -u admin:admin "http://$(hostname -f):7180/api/v14/hosts"
```

```
{
  "items" : [ {
    "hostId" : "8e02b9c1-4abf-4b13-ba42-26e77c621a4c",
    "ipAddress" : "172.31.21.169",
    "hostname" : "ip-172-31-21-169.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/hostRedirect/8e02b9c1-4abf-4b13-ba42-26e77c621a4c",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "ce9ddcad-991e-4013-a167-140442eca238",
    "ipAddress" : "172.31.21.54",
    "hostname" : "ip-172-31-21-54.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/hostRedirect/ce9ddcad-991e-4013-a167-140442eca238",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "6dd9450d-45f3-4b71-bcca-cc8f9a602dc0",
    "ipAddress" : "172.31.26.92",
    "hostname" : "ip-172-31-26-92.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/hostRedirect/6dd9450d-45f3-4b71-bcca-cc8f9a602dc0",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "bc612728-6b0c-48aa-b7bc-e82e088d53d1",
    "ipAddress" : "172.31.30.84",
    "hostname" : "ip-172-31-30-84.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/hostRedirect/bc612728-6b0c-48aa-b7bc-e82e088d53d1",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "41e2cca8-85e1-476a-8d28-78b32155af6a",
    "ipAddress" : "172.31.31.176",
    "hostname" : "ip-172-31-31-176.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/hostRedirect/41e2cca8-85e1-476a-8d28-78b32155af6a",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  } ]
}
```


## The command and output from the CM API call ../api/v8/clusters/<githubName>/services

```
curl -u admin:admin "http://$(hostname -f):7180/api/v8/clusters/dobeslao/services"
```

```
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-84.ec2.internal:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  } ]
}
```
