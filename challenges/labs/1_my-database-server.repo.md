# Install a MySQL server

## Install MySQL 5.6 or MariaDB 5.5 server on the first node listed in

```
[root@ip-172-31-26-92 ~]# cat /etc/yum.repos.d/MariaDB10.repo
# MariaDB 10.1 CentOS repository list - created 2016-01-18 09:58 UTC
# http://mariadb.org/mariadb/repositories/
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.1/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
enablerepo=1
```

# A command and output that shows the hostname of your database server

```
MariaDB [(none)]> SHOW VARIABLES like 'hostname';
+---------------+------------------------------+
| Variable_name | Value                        |
+---------------+------------------------------+
| hostname      | ip-172-31-26-92.ec2.internal |
+---------------+------------------------------+

yum install MariaDB-server MariaDB-client -y
```

# A command and output that reports the database server version
```
MariaDB [(none)]> select version();
+-----------------+
| version()       |
+-----------------+
| 10.1.29-MariaDB |
+-----------------+
```

# A command and output that lists all the databases in the server
```
MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| amon               |
| hive               |
| hue                |
| information_schema |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| sentry             |
+--------------------+
```

