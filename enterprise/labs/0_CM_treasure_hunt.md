# What is ubertask optimization?

Ubertask optimization is a efficient strategy, that lets within a single JVM, run a sequentially list of small jobs.

This jobs can be defined using the properties of YARN defined as:

    * mapreduce.job.ubertask.maxmaps
        Threshold for number of maps, beyond which a job is considered too big for ubertask optimization.
    * mapreduce.job.ubertask.maxreduces
        Threshold for number of reduces, beyond which a job is considered too big for ubertask optimization.
    * mapreduce.job.ubertask.maxbytes
        Threshold for number of input bytes, beyond which a job is considered too big for ubertask optimization. If no value is specified, dfs.block.size is used as a default.

# Where in CM is the Kerberos Security Realm value displayed?

    Is defined in the [Configuration of Cloudera Manager Administration](http://ip-172-31-22-38.ec2.internal:7180/cmf/settings?groupKey=config.common.kerberos.display_group&groupParent=#filtercategory=Settings&filterdisplayGroup=Kerberos)

    Look for the property: Kerberos Security Realm (default_realm)

    My current value is: VINKOS.COM

# Which CDH service(s) host a property for enabling Kerberos authentication?

    * HDFS
    * YARN (MR2 Included)
    * ZooKeeper

# How do you upgrade the CM agents?

    The suggested way is runing the wizard again and choose update.

    [Upgrade Wizard](http://ip-172-31-22-38.ec2.internal:7180/cmf/upgrade-wizard/welcome)

    You cand find on Hosts and All Hosts. Select Re-run Upgrade Wizard.

# Give the tsquery statement used to chart Hue's CPU utilization?

**tsquery**
```
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
```

# Name all the roles that make up the Hive service

Going to Hive > Instances > Add Role Instances you can get:

    * Hive Metastore Server
    * WebHCat Server
    * HiveServer2

# What steps must be completed before integrating Cloudera Manager with Kerberos?

* Working Kerberos Server
    - Supports authentication with MIT KDC and Active Directory.
* Kerberos configurations
    - Configure the KDC to allow renewable tickets with non-zero ticket lifetimes.
    - For MIT KDC, make sure you have the following lines in the kdc.conf
    max_life = 1d  
    max_renewable_life = 7d
    kdc_tcp_ports = 88
    - If you are using Active Directory, make sure LDAP over TLS/SSL (LDAPS) is enabled for the Domain Controllers.
* Kerberos client in all nodes
    - openldap-clients on the Cloudera Manager Server host (if use AD)
    - krb5-workstation, krb5-libs on ALL hosts 
* Get privileges, creating */admin and cloudera-scm ACL
* Adds the password policy to the database

