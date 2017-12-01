# Challenges of the Services Enablement Boot Camp

# List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)
```
AWS - N. Virginia, region=us-east-1
```

# List your instances by IP address and DNS name (don't use /etc/hosts for this)

```
[root@ip-172-31-26-92 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}')
172.31.26.92    ip-172-31-26-92.ec2.internal
fe80::84c:c8ff:feef:d354 ip-172-31-26-92.ec2.internal

172.31.30.84    ip-172-31-30-84.ec2.internal
fe80::8aa:18ff:fe2c:221a ip-172-31-30-84.ec2.internal

172.31.21.169   ip-172-31-21-169.ec2.internal
fe80::880:70ff:fe04:9790 ip-172-31-21-169.ec2.internal

172.31.31.176   ip-172-31-31-176.ec2.internal
fe80::8b8:aeff:fe22:d454 ip-172-31-31-176.ec2.internal

172.31.21.54    ip-172-31-21-54.ec2.internal
fe80::89a:6aff:fe5c:ceee ip-172-31-21-54.ec2.internal
```

# List the Linux release you are using

```
[root@ip-172-31-21-54 ~]# uname -a
Linux ip-172-31-21-54.ec2.internal 3.10.0-693.el7.x86_64 #1 SMP Thu Jul 6 19:56:57 EDT 2017 x86_64 x86_64 x86_64 GNU/Linux

[root@ip-172-31-21-54 ~]# cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.4 (Maipo)
```

# List the file system capacity for the first node

```
[root@ip-172-31-21-54 ~]# lsblk -fm
NAME    FSTYPE LABEL UUID                                 MOUNTPOINT  NAME    SIZE OWNER GROUP MODE
xvda                                                                  xvda     50G root  disk  brw-rw----
├─xvda1                                                               ├─xvda1   1M root  disk  brw-rw----
└─xvda2 xfs          de4def96-ff72-4eb9-ad5e-0847257d1866 /           └─xvda2  50G root  disk  brw-rw----
xvdb    ext4         14bca747-2085-4a40-b0e6-cb8302027f20 /data/disk0 xvdb     80G root  disk  brw-rw----
xvdc    ext4         a09baf82-caeb-4d7a-914b-c2e233e9bfd9 /data/disk1 xvdc     80G root  disk  brw-rw----
```

# List the command and output for yum repolist enabled
```
[root@ip-172-31-21-54 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                                  repo name                                                                                status
rhui-REGION-client-config-server-7/x86_64                                Red Hat Update Infrastructure 2.0 Client Configuration Server 7                               8
rhui-REGION-rhel-server-releases/7Server/x86_64                          Red Hat Enterprise Linux Server 7 (RPMs)                                                 17,521
rhui-REGION-rhel-server-rh-common/7Server/x86_64                         Red Hat Enterprise Linux Server 7 RH Common (RPMs)                                          228
repolist: 17,757
```

# Add the following Linux accounts to all nodes

```
[root@ip-172-31-21-54 ~]# useradd -u 2010 saturn
[root@ip-172-31-21-54 ~]# useradd -u 2016 haley
[root@ip-172-31-21-54 ~]# groupadd comets
[root@ip-172-31-21-54 ~]# usermod -aG comets haley
[root@ip-172-31-21-54 ~]# groupadd planets
[root@ip-172-31-21-54 ~]# usermod -aG planets saturn
```

# List the /etc/passwd entries for saturn and haley

```
[root@ip-172-31-21-54 ~]# tail -n 2 /etc/passwd
saturn:x:2010:2010::/home/saturn:/bin/bash
haley:x:2016:2016::/home/haley:/bin/bash
```

# List the /etc/group entries for comets and planets
```
[root@ip-172-31-21-54 ~]# tail -n 2 /etc/group
comets:x:2017:haley
planets:x:2018:saturn
```
