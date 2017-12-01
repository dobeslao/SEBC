# HDFS Testing

# The full teragen command and output
```
[saturn@ip-172-31-30-84 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=12 -Ddfs.block.size=33554432 -Dmapreduce.map.memory.mb=512 65536000 /user/saturn/tgen
```

```


17/12/01 12:29:23 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-21-54.ec2.internal/172.31.21.54:8032
17/12/01 12:29:24 INFO terasort.TeraSort: Generating 65536000 using 12
17/12/01 12:29:24 INFO mapreduce.JobSubmitter: number of splits:12
17/12/01 12:29:24 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/12/01 12:29:24 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 12:29:24 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512151168866_0001
17/12/01 12:29:24 INFO impl.YarnClientImpl: Submitted application application_1512151168866_0001
17/12/01 12:29:24 INFO mapreduce.Job: The url to track the job: http://ip-172-31-21-54.ec2.internal:8088/proxy/application_1512151168866_0001/
17/12/01 12:29:24 INFO mapreduce.Job: Running job: job_1512151168866_0001
17/12/01 12:29:31 INFO mapreduce.Job: Job job_1512151168866_0001 running in uber mode : false
17/12/01 12:29:31 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 12:29:42 INFO mapreduce.Job:  map 8% reduce 0%
17/12/01 12:29:44 INFO mapreduce.Job:  map 21% reduce 0%
17/12/01 12:29:45 INFO mapreduce.Job:  map 24% reduce 0%
17/12/01 12:29:47 INFO mapreduce.Job:  map 30% reduce 0%
17/12/01 12:29:48 INFO mapreduce.Job:  map 33% reduce 0%
17/12/01 12:29:50 INFO mapreduce.Job:  map 37% reduce 0%
17/12/01 12:29:51 INFO mapreduce.Job:  map 40% reduce 0%
17/12/01 12:29:53 INFO mapreduce.Job:  map 47% reduce 0%
17/12/01 12:29:54 INFO mapreduce.Job:  map 48% reduce 0%
17/12/01 12:29:56 INFO mapreduce.Job:  map 54% reduce 0%
17/12/01 12:29:57 INFO mapreduce.Job:  map 56% reduce 0%
17/12/01 12:29:59 INFO mapreduce.Job:  map 62% reduce 0%
17/12/01 12:30:00 INFO mapreduce.Job:  map 64% reduce 0%
17/12/01 12:30:01 INFO mapreduce.Job:  map 65% reduce 0%
17/12/01 12:30:02 INFO mapreduce.Job:  map 72% reduce 0%
17/12/01 12:30:03 INFO mapreduce.Job:  map 74% reduce 0%
17/12/01 12:30:05 INFO mapreduce.Job:  map 81% reduce 0%
17/12/01 12:30:06 INFO mapreduce.Job:  map 82% reduce 0%
17/12/01 12:30:08 INFO mapreduce.Job:  map 86% reduce 0%
17/12/01 12:30:09 INFO mapreduce.Job:  map 87% reduce 0%
17/12/01 12:30:11 INFO mapreduce.Job:  map 89% reduce 0%
17/12/01 12:30:17 INFO mapreduce.Job:  map 92% reduce 0%
17/12/01 12:30:20 INFO mapreduce.Job:  map 95% reduce 0%
17/12/01 12:30:21 INFO mapreduce.Job:  map 96% reduce 0%
17/12/01 12:30:23 INFO mapreduce.Job:  map 98% reduce 0%
17/12/01 12:30:26 INFO mapreduce.Job: Job job_1512151168866_0001 completed successfully
17/12/01 12:30:26 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1470626
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=553218
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=553218
                Total vcore-seconds taken by all map tasks=553218
                Total megabyte-seconds taken by all map tasks=566495232
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1907
                CPU time spent (ms)=137040
                Physical memory (bytes) snapshot=2366447616
                Virtual memory (bytes) snapshot=13759848448
                Total committed heap usage (bytes)=4423942144
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000
```

# The result of the time command
```
real    1m4.731s
user    0m4.450s
sys     0m0.240s
```

# The command and output of hdfs dfs -ls /user/saturn/tgen
```
[saturn@ip-172-31-30-84 ~]$ hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn hadoop          0 2017-12-01 12:30 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:30 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:30 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:30 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:30 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:30 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:30 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:30 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:30 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:30 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:30 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:29 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:30 /user/saturn/tgen/part-m-00011
```

# The command and output of hadoop fsck -blocks /user/saturn
```
[saturn@ip-172-31-30-84 ~]$ hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-21-54.ec2.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.30.84 for path /user/saturn at Fri Dec 01 18:37:56 UTC 2017
.............Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    3
 Total files:   13
 Total symlinks:                0
 Total blocks (validated):      204 (avg. block size 32125490 B)
 Minimally replicated blocks:   204 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Fri Dec 01 18:37:56 UTC 2017 in 14 milliseconds


The filesystem under path '/user/saturn' is HEALTHY
```
