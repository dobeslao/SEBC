# Call API Hive Service 

## Call API Hive status

```
[root@ip-172-31-22-38.ec2 ~]# curl -u dobeslao:cloudera 'http://ip-172-31-22-38.ec2.internal:7180/api/v12/clusters/Cluster%201/services/hive'
```

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-17-126.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-17-126.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}%   
```

## Call API Hive stop

```
[root@ip-172-31-22-38.ec2 ~]# curl -X POST -u dobeslao:cloudera 'http://ip-172-31-22-38.ec2.internal:7180/api/v12/clusters/Cluster%201/services/hive/commands/stop'
```

```
{
  "id" : 887,
  "name" : "Stop",
  "startTime" : "2017-12-01T02:05:57.860Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}%
```

## Call API Hive start

```
[root@ip-172-31-22-38.ec2 ~]# curl -X POST -u landyrt:cloudera 'http://ip-172-31-22-38.ec2.internal:7180/api/v18/clusters/Cluster%201/services/hive/commands/start'
```

```
{
  "id" : 892,
  "name" : "Start",
  "startTime" : "2017-12-01T02:06:15.370Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}%       
```
