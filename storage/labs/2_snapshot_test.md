# Creación de Snapshots

## Create a precious directory in HDFS; copy the ZIP course file into it
```
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -mkdir /user/dobeslao/precious

[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -put SEBC-master.zip /user/dobeslao/precious
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -ls -h /user/dobeslao/precious
Found 1 items
-rw-r--r--   3 dobeslao hadoop    463.7 K 2017-11-28 20:14 /user/dobeslao/precious/SEBC-master.zip
```

## Enable snapshots for precious
```
[dobeslao@ip-172-31-18-218 ~]$ sudo -u hdfs hdfs dfsadmin -allowSnapshot /user/dobeslao/precious
Allowing snaphot on /user/dobeslao/precious succeeded
```

## Create a snapshot called sebc-hdfs-test
```
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -createSnapshot /user/dobeslao/precious sebc-hdfs-test
Created snapshot /user/dobeslao/precious/.snapshot/sebc-hdfs-test
```

## Delete the directory
```
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -rm -R -f -skipTrash /user/dobeslao/precious
rm: The directory /user/dobeslao/precious cannot be deleted since /user/dobeslao/precious is snapshottable and already has snapshots
```

## Delete the ZIP file
```
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -rm -R -f -skipTrash /user/dobeslao/precious/SEBC-master.zip
Deleted /user/dobeslao/precious/SEBC-master.zip
```

## Restore the deleted file
```
# Review
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -ls -h /user/dobeslao/precious/.snapshot
Found 1 items
drwxr-xr-x   - dobeslao hadoop          0 2017-11-28 20:09 /user/dobeslao/precious/.snapshot/sebc-hdfs-test
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -ls -h /user/dobeslao/precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 dobeslao hadoop    463.7 K 2017-11-28 20:00 /user/dobeslao/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip

# Restore
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -cp -p /user/dobeslao/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /user/dobeslao/precious
[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -ls -h /user/dobeslao/precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 dobeslao hadoop    463.7 K 2017-11-28 20:00 /user/dobeslao/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip
```
