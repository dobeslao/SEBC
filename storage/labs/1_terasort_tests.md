# Teragen Test

## Teragen, archivo=10GB / block=32MB / mappers=4
```
[dobeslao@ip-172-31-18-218 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 110374182 /user/dobeslao/teragen
```

## Teragen, resultados
```
[dobeslao@ip-172-31-18-218 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 107374183 /user/dobeslao/teragen
17/11/29 04:48:53 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-52.ec2.internal/172.31.24.52:8032
17/11/29 04:48:54 INFO terasort.TeraGen: Generating 107374183 using 4
17/11/29 04:48:54 INFO mapreduce.JobSubmitter: number of splits:4
17/11/29 04:48:54 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/29 04:48:54 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/29 04:48:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511911765062_0008
17/11/29 04:48:54 INFO impl.YarnClientImpl: Submitted application application_1511911765062_0008
17/11/29 04:48:55 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-52.ec2.internal:8088/proxy/application_1511911765062_0008/
17/11/29 04:48:55 INFO mapreduce.Job: Running job: job_1511911765062_0008
17/11/29 04:49:01 INFO mapreduce.Job: Job job_1511911765062_0008 running in uber mode : false
17/11/29 04:49:01 INFO mapreduce.Job:  map 0% reduce 0%
17/11/29 04:49:17 INFO mapreduce.Job:  map 5% reduce 0%
17/11/29 04:49:18 INFO mapreduce.Job:  map 19% reduce 0%
17/11/29 04:49:23 INFO mapreduce.Job:  map 21% reduce 0%
17/11/29 04:49:24 INFO mapreduce.Job:  map 27% reduce 0%
17/11/29 04:49:29 INFO mapreduce.Job:  map 28% reduce 0%
17/11/29 04:49:30 INFO mapreduce.Job:  map 32% reduce 0%
17/11/29 04:49:35 INFO mapreduce.Job:  map 33% reduce 0%
17/11/29 04:49:36 INFO mapreduce.Job:  map 37% reduce 0%
17/11/29 04:49:42 INFO mapreduce.Job:  map 38% reduce 0%
17/11/29 04:49:47 INFO mapreduce.Job:  map 39% reduce 0%
17/11/29 04:49:48 INFO mapreduce.Job:  map 42% reduce 0%
17/11/29 04:49:53 INFO mapreduce.Job:  map 45% reduce 0%
17/11/29 04:49:54 INFO mapreduce.Job:  map 51% reduce 0%
17/11/29 04:49:59 INFO mapreduce.Job:  map 52% reduce 0%
17/11/29 04:50:00 INFO mapreduce.Job:  map 56% reduce 0%
17/11/29 04:50:05 INFO mapreduce.Job:  map 58% reduce 0%
17/11/29 04:50:06 INFO mapreduce.Job:  map 63% reduce 0%
17/11/29 04:50:11 INFO mapreduce.Job:  map 64% reduce 0%
17/11/29 04:50:12 INFO mapreduce.Job:  map 65% reduce 0%
17/11/29 04:50:17 INFO mapreduce.Job:  map 67% reduce 0%
17/11/29 04:50:18 INFO mapreduce.Job:  map 72% reduce 0%
17/11/29 04:50:23 INFO mapreduce.Job:  map 74% reduce 0%
17/11/29 04:50:24 INFO mapreduce.Job:  map 78% reduce 0%
17/11/29 04:50:29 INFO mapreduce.Job:  map 80% reduce 0%
17/11/29 04:50:30 INFO mapreduce.Job:  map 84% reduce 0%
17/11/29 04:50:35 INFO mapreduce.Job:  map 85% reduce 0%
17/11/29 04:50:36 INFO mapreduce.Job:  map 89% reduce 0%
17/11/29 04:50:41 INFO mapreduce.Job:  map 90% reduce 0%
17/11/29 04:50:42 INFO mapreduce.Job:  map 95% reduce 0%
17/11/29 04:50:43 INFO mapreduce.Job:  map 96% reduce 0%
17/11/29 04:50:45 INFO mapreduce.Job:  map 98% reduce 0%
17/11/29 04:50:46 INFO mapreduce.Job:  map 100% reduce 0%
17/11/29 04:50:46 INFO mapreduce.Job: Job job_1511911765062_0008 completed successfully
17/11/29 04:50:46 INFO mapreduce.Job: Counters: 31
    File System Counters
        FILE: Number of bytes read=0
        FILE: Number of bytes written=581520
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=344
        HDFS: Number of bytes written=10737418300
        HDFS: Number of read operations=16
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=8
    Job Counters 
        Launched map tasks=4
        Other local map tasks=4
        Total time spent by all maps in occupied slots (ms)=410574
        Total time spent by all reduces in occupied slots (ms)=0
        Total time spent by all map tasks (ms)=410574
        Total vcore-milliseconds taken by all map tasks=410574
        Total megabyte-milliseconds taken by all map tasks=420427776
    Map-Reduce Framework
        Map input records=107374183
        Map output records=107374183
        Input split bytes=344
        Spilled Records=0
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=799
        CPU time spent (ms)=149750
        Physical memory (bytes) snapshot=746999808
        Virtual memory (bytes) snapshot=6382608384
        Total committed heap usage (bytes)=1682440192
    org.apache.hadoop.examples.terasort.TeraGen$Counters
        CHECKSUM=230593860607047066
    File Input Format Counters 
        Bytes Read=0
    File Output Format Counters 
        Bytes Written=10737418300

real    1m55.033s
user    0m5.179s
sys     0m0.322s

[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -ls -h /user/dobeslao/teragen
Found 5 items
-rw-r--r--   3 dobeslao hadoop          0 2017-11-29 04:50 /user/dobeslao/teragen/_SUCCESS
-rw-r--r--   3 dobeslao hadoop      2.5 G 2017-11-29 04:50 /user/dobeslao/teragen/part-m-00000
-rw-r--r--   3 dobeslao hadoop      2.5 G 2017-11-29 04:50 /user/dobeslao/teragen/part-m-00001
-rw-r--r--   3 dobeslao hadoop      2.5 G 2017-11-29 04:50 /user/dobeslao/teragen/part-m-00002
-rw-r--r--   3 dobeslao hadoop      2.5 G 2017-11-29 04:50 /user/dobeslao/teragen/part-m-00003

[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -du -s -h /user/dobeslao/teragen
10.0 G  30.0 G  /user/dobeslao/teragen
```

# Terasort Test

## Teragen, directorio=teragen
```
[dobeslao@ip-172-31-18-218 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/dobeslao/teragen /user/dobeslao/terasort
```

## Terasort, resultados
```
17/11/29 05:09:48 INFO terasort.TeraSort: starting
17/11/29 05:09:49 INFO input.FileInputFormat: Total input paths to process : 4
Spent 194ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 200ms
Sampling 10 splits of 320
Making 16 from 100000 sampled records
Computing parititions took 657ms
Spent 859ms computing partitions.
17/11/29 05:09:50 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-52.ec2.internal/172.31.24.52:8032
17/11/29 05:09:50 INFO mapreduce.JobSubmitter: number of splits:320
17/11/29 05:09:51 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511911765062_0010
17/11/29 05:09:51 INFO impl.YarnClientImpl: Submitted application application_1511911765062_0010
17/11/29 05:09:51 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-52.ec2.internal:8088/proxy/application_1511911765062_0010/
17/11/29 05:09:51 INFO mapreduce.Job: Running job: job_1511911765062_0010
17/11/29 05:09:56 INFO mapreduce.Job: Job job_1511911765062_0010 running in uber mode : false
17/11/29 05:09:56 INFO mapreduce.Job:  map 0% reduce 0%
17/11/29 05:10:05 INFO mapreduce.Job:  map 1% reduce 0%
17/11/29 05:10:06 INFO mapreduce.Job:  map 2% reduce 0%
17/11/29 05:10:07 INFO mapreduce.Job:  map 3% reduce 0%
17/11/29 05:10:08 INFO mapreduce.Job:  map 5% reduce 0%
17/11/29 05:10:09 INFO mapreduce.Job:  map 7% reduce 0%
17/11/29 05:10:10 INFO mapreduce.Job:  map 8% reduce 0%
17/11/29 05:10:12 INFO mapreduce.Job:  map 9% reduce 0%
17/11/29 05:10:15 INFO mapreduce.Job:  map 10% reduce 0%
17/11/29 05:10:16 INFO mapreduce.Job:  map 11% reduce 0%
17/11/29 05:10:18 INFO mapreduce.Job:  map 12% reduce 0%
17/11/29 05:10:19 INFO mapreduce.Job:  map 14% reduce 0%
17/11/29 05:10:20 INFO mapreduce.Job:  map 16% reduce 0%
17/11/29 05:10:21 INFO mapreduce.Job:  map 17% reduce 0%
17/11/29 05:10:24 INFO mapreduce.Job:  map 18% reduce 0%
17/11/29 05:10:25 INFO mapreduce.Job:  map 19% reduce 0%
17/11/29 05:10:26 INFO mapreduce.Job:  map 20% reduce 0%
17/11/29 05:10:30 INFO mapreduce.Job:  map 22% reduce 0%
17/11/29 05:10:31 INFO mapreduce.Job:  map 23% reduce 0%
17/11/29 05:10:32 INFO mapreduce.Job:  map 26% reduce 0%
17/11/29 05:10:33 INFO mapreduce.Job:  map 27% reduce 0%
17/11/29 05:10:34 INFO mapreduce.Job:  map 28% reduce 0%
17/11/29 05:10:39 INFO mapreduce.Job:  map 29% reduce 0%
17/11/29 05:10:41 INFO mapreduce.Job:  map 31% reduce 0%
17/11/29 05:10:42 INFO mapreduce.Job:  map 33% reduce 0%
17/11/29 05:10:43 INFO mapreduce.Job:  map 35% reduce 0%
17/11/29 05:10:44 INFO mapreduce.Job:  map 36% reduce 0%
17/11/29 05:10:46 INFO mapreduce.Job:  map 37% reduce 0%
17/11/29 05:10:52 INFO mapreduce.Job:  map 38% reduce 0%
17/11/29 05:10:53 INFO mapreduce.Job:  map 41% reduce 0%
17/11/29 05:10:54 INFO mapreduce.Job:  map 42% reduce 0%
17/11/29 05:10:55 INFO mapreduce.Job:  map 44% reduce 0%
17/11/29 05:10:56 INFO mapreduce.Job:  map 45% reduce 0%
17/11/29 05:11:01 INFO mapreduce.Job:  map 47% reduce 0%
17/11/29 05:11:02 INFO mapreduce.Job:  map 48% reduce 0%
17/11/29 05:11:04 INFO mapreduce.Job:  map 50% reduce 0%
17/11/29 05:11:05 INFO mapreduce.Job:  map 52% reduce 0%
17/11/29 05:11:08 INFO mapreduce.Job:  map 53% reduce 0%
17/11/29 05:11:09 INFO mapreduce.Job:  map 54% reduce 0%
17/11/29 05:11:10 INFO mapreduce.Job:  map 56% reduce 0%
17/11/29 05:11:15 INFO mapreduce.Job:  map 58% reduce 0%
17/11/29 05:11:16 INFO mapreduce.Job:  map 61% reduce 0%
17/11/29 05:11:18 INFO mapreduce.Job:  map 62% reduce 0%
17/11/29 05:11:19 INFO mapreduce.Job:  map 63% reduce 0%
17/11/29 05:11:20 INFO mapreduce.Job:  map 64% reduce 0%
17/11/29 05:11:23 INFO mapreduce.Job:  map 65% reduce 0%
17/11/29 05:11:24 INFO mapreduce.Job:  map 66% reduce 0%
17/11/29 05:11:26 INFO mapreduce.Job:  map 67% reduce 0%
17/11/29 05:11:27 INFO mapreduce.Job:  map 68% reduce 0%
17/11/29 05:11:28 INFO mapreduce.Job:  map 70% reduce 0%
17/11/29 05:11:29 INFO mapreduce.Job:  map 72% reduce 0%
17/11/29 05:11:30 INFO mapreduce.Job:  map 73% reduce 0%
17/11/29 05:11:36 INFO mapreduce.Job:  map 74% reduce 0%
17/11/29 05:11:37 INFO mapreduce.Job:  map 78% reduce 0%
17/11/29 05:11:38 INFO mapreduce.Job:  map 79% reduce 0%
17/11/29 05:11:39 INFO mapreduce.Job:  map 80% reduce 0%
17/11/29 05:11:41 INFO mapreduce.Job:  map 81% reduce 0%
17/11/29 05:11:43 INFO mapreduce.Job:  map 82% reduce 0%
17/11/29 05:11:46 INFO mapreduce.Job:  map 84% reduce 0%
17/11/29 05:11:47 INFO mapreduce.Job:  map 85% reduce 0%
17/11/29 05:11:48 INFO mapreduce.Job:  map 86% reduce 0%
17/11/29 05:11:49 INFO mapreduce.Job:  map 87% reduce 0%
17/11/29 05:11:50 INFO mapreduce.Job:  map 88% reduce 0%
17/11/29 05:11:53 INFO mapreduce.Job:  map 89% reduce 0%
17/11/29 05:11:59 INFO mapreduce.Job:  map 90% reduce 2%
17/11/29 05:12:01 INFO mapreduce.Job:  map 91% reduce 7%
17/11/29 05:12:02 INFO mapreduce.Job:  map 92% reduce 9%
17/11/29 05:12:03 INFO mapreduce.Job:  map 93% reduce 9%
17/11/29 05:12:04 INFO mapreduce.Job:  map 93% reduce 19%
17/11/29 05:12:05 INFO mapreduce.Job:  map 93% reduce 21%
17/11/29 05:12:06 INFO mapreduce.Job:  map 93% reduce 23%
17/11/29 05:12:07 INFO mapreduce.Job:  map 93% reduce 27%
17/11/29 05:12:08 INFO mapreduce.Job:  map 94% reduce 29%
17/11/29 05:12:10 INFO mapreduce.Job:  map 95% reduce 29%
17/11/29 05:12:11 INFO mapreduce.Job:  map 96% reduce 29%
17/11/29 05:12:13 INFO mapreduce.Job:  map 96% reduce 30%
17/11/29 05:12:14 INFO mapreduce.Job:  map 97% reduce 30%
17/11/29 05:12:16 INFO mapreduce.Job:  map 98% reduce 30%
17/11/29 05:12:19 INFO mapreduce.Job:  map 99% reduce 30%
17/11/29 05:12:20 INFO mapreduce.Job:  map 100% reduce 31%
17/11/29 05:12:23 INFO mapreduce.Job:  map 100% reduce 33%
17/11/29 05:12:24 INFO mapreduce.Job:  map 100% reduce 35%
17/11/29 05:12:25 INFO mapreduce.Job:  map 100% reduce 43%
17/11/29 05:12:26 INFO mapreduce.Job:  map 100% reduce 46%
17/11/29 05:12:28 INFO mapreduce.Job:  map 100% reduce 58%
17/11/29 05:12:29 INFO mapreduce.Job:  map 100% reduce 62%
17/11/29 05:12:30 INFO mapreduce.Job:  map 100% reduce 63%
17/11/29 05:12:31 INFO mapreduce.Job:  map 100% reduce 76%
17/11/29 05:12:32 INFO mapreduce.Job:  map 100% reduce 77%
17/11/29 05:12:33 INFO mapreduce.Job:  map 100% reduce 79%
17/11/29 05:12:34 INFO mapreduce.Job:  map 100% reduce 87%
17/11/29 05:12:36 INFO mapreduce.Job:  map 100% reduce 89%
17/11/29 05:12:37 INFO mapreduce.Job:  map 100% reduce 92%
17/11/29 05:12:39 INFO mapreduce.Job:  map 100% reduce 93%
17/11/29 05:12:40 INFO mapreduce.Job:  map 100% reduce 96%
17/11/29 05:12:43 INFO mapreduce.Job:  map 100% reduce 97%
17/11/29 05:12:44 INFO mapreduce.Job:  map 100% reduce 98%
17/11/29 05:12:49 INFO mapreduce.Job:  map 100% reduce 99%
17/11/29 05:12:51 INFO mapreduce.Job:  map 100% reduce 100%
17/11/29 05:12:51 INFO mapreduce.Job: Job job_1511911765062_0010 completed successfully
17/11/29 05:12:51 INFO mapreduce.Job: Counters: 49
    File System Counters
        FILE: Number of bytes read=4763134186
        FILE: Number of bytes written=9475504098
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=10737463100
        HDFS: Number of bytes written=10737418300
        HDFS: Number of read operations=1008
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=32
    Job Counters 
        Launched map tasks=320
        Launched reduce tasks=16
        Data-local map tasks=320
        Total time spent by all maps in occupied slots (ms)=2655418
        Total time spent by all reduces in occupied slots (ms)=882079
        Total time spent by all map tasks (ms)=2655418
        Total time spent by all reduce tasks (ms)=882079
        Total vcore-milliseconds taken by all map tasks=2655418
        Total vcore-milliseconds taken by all reduce tasks=882079
        Total megabyte-milliseconds taken by all map tasks=2719148032
        Total megabyte-milliseconds taken by all reduce tasks=903248896
    Map-Reduce Framework
        Map input records=107374183
        Map output records=107374183
        Map output bytes=10952166666
        Map output materialized bytes=4662927616
        Input split bytes=44800
        Combine input records=0
        Combine output records=0
        Reduce input groups=107374183
        Reduce shuffle bytes=4662927616
        Reduce input records=107374183
        Reduce output records=107374183
        Spilled Records=214748366
        Shuffled Maps =5120
        Failed Shuffles=0
        Merged Map outputs=5120
        GC time elapsed (ms)=35411
        CPU time spent (ms)=1592950
        Physical memory (bytes) snapshot=181549412352
        Virtual memory (bytes) snapshot=536656793600
        Total committed heap usage (bytes)=186448347136
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=10737418300
    File Output Format Counters 
        Bytes Written=10737418300
17/11/29 05:12:51 INFO terasort.TeraSort: done

real    3m4.208s
user    0m8.212s
sys     0m0.353s

[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -ls -h /user/dobeslao/terasort
Found 18 items
-rw-r--r--   1 dobeslao hadoop          0 2017-11-29 05:12 /user/dobeslao/terasort/_SUCCESS
-rw-r--r--  10 dobeslao hadoop        165 2017-11-29 05:09 /user/dobeslao/terasort/_partition.lst
-rw-r--r--   1 dobeslao hadoop    648.5 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00000
-rw-r--r--   1 dobeslao hadoop    630.7 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00001
-rw-r--r--   1 dobeslao hadoop    625.2 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00002
-rw-r--r--   1 dobeslao hadoop    634.9 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00003
-rw-r--r--   1 dobeslao hadoop    638.7 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00004
-rw-r--r--   1 dobeslao hadoop    643.6 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00005
-rw-r--r--   1 dobeslao hadoop    643.6 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00006
-rw-r--r--   1 dobeslao hadoop    645.7 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00007
-rw-r--r--   1 dobeslao hadoop    654.4 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00008
-rw-r--r--   1 dobeslao hadoop    632.1 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00009
-rw-r--r--   1 dobeslao hadoop    654.7 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00010
-rw-r--r--   1 dobeslao hadoop    644.3 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00011
-rw-r--r--   1 dobeslao hadoop    634.5 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00012
-rw-r--r--   1 dobeslao hadoop    627.4 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00013
-rw-r--r--   1 dobeslao hadoop    643.0 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00014
-rw-r--r--   1 dobeslao hadoop    638.8 M 2017-11-29 05:12 /user/dobeslao/terasort/part-r-00015

[dobeslao@ip-172-31-18-218 ~]$ hdfs dfs -du -s -h /user/dobeslao/terasort
10.0 G  10.0 G  /user/dobeslao/terasort
```
