# Use the API on the command line

## Report the latest available version of the API

```
[root@ip-172-31-22-38.ec2 ~]# curl -u dobeslao:cloudera 'http://ip-172-31-22-38.ec2.internal:7180/api/version'
```

```
v18%
```

## Report the CM version

```
[root@ip-172-31-22-38.ec2 ~]# curl -X GET -u dobeslao:cloudera 'http://ip-172-31-22-38.ec2.internal:7180/api/v18/cm/version'
```

```
{
  "version" : "5.13.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20171002-1719",
  "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
  "snapshot" : false
}%
```

List all CM users

```
[root@ip-172-31-22-38.ec2 ~]# curl -u dobeslao:cloudera 'http://ip-172-31-22-38.ec2.internal:7180/api/v18/users'
```

```
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "dobeslao",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}%  
```

Report the database server in use by CM

```
[root@ip-172-31-22-38.ec2 ~]# curl -u dobeslao:cloudera 'http://ip-172-31-22-38.ec2.internal:7180/api/v18/cm/scmDbInfo'
```

```
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}%
```
