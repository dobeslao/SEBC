# Kerberize the cluster

## Run the terasort program as user saturn

### Teragen

```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 10000000 /user/saturn/tgen2
```

```
17/12/01 13:32:44 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-21-54.ec2.internal/172.31.21.54:8032
17/12/01 13:32:44 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512156764504, maxDate=1512761564504, sequenceNumber=5, masterKeyId=2 on 172.31.21.54:8020
17/12/01 13:32:44 INFO security.TokenCache: Got dt for hdfs://ip-172-31-21-54.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.21.54:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512156764504, maxDate=1512761564504, sequenceNumber=5, masterKeyId=2)
17/12/01 13:32:44 INFO terasort.TeraSort: Generating 10000000 using 4
17/12/01 13:32:44 INFO mapreduce.JobSubmitter: number of splits:4
17/12/01 13:32:44 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/12/01 13:32:44 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 13:32:45 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154882708_0005
17/12/01 13:32:45 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.21.54:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512156764504, maxDate=1512761564504, sequenceNumber=5, masterKeyId=2)
17/12/01 13:32:45 INFO impl.YarnClientImpl: Submitted application application_1512154882708_0005
17/12/01 13:32:45 INFO mapreduce.Job: The url to track the job: http://ip-172-31-21-54.ec2.internal:8088/proxy/application_1512154882708_0005/
17/12/01 13:32:45 INFO mapreduce.Job: Running job: job_1512154882708_0005
17/12/01 13:32:53 INFO mapreduce.Job: Job job_1512154882708_0005 running in uber mode : false
17/12/01 13:32:53 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:33:07 INFO mapreduce.Job:  map 61% reduce 0%
17/12/01 13:33:08 INFO mapreduce.Job:  map 79% reduce 0%
17/12/01 13:33:09 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:33:10 INFO mapreduce.Job: Job job_1512154882708_0005 completed successfully
17/12/01 13:33:10 INFO mapreduce.Job: Counters: 31
    File System Counters
        FILE: Number of bytes read=0
        FILE: Number of bytes written=493184
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=337
        HDFS: Number of bytes written=1000000000
        HDFS: Number of read operations=16
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=8
    Job Counters 
        Launched map tasks=4
        Other local map tasks=4
        Total time spent by all maps in occupied slots (ms)=57927
        Total time spent by all reduces in occupied slots (ms)=0
        Total time spent by all map tasks (ms)=57927
        Total vcore-seconds taken by all map tasks=57927
        Total megabyte-seconds taken by all map tasks=59317248
    Map-Reduce Framework
        Map input records=10000000
        Map output records=10000000
        Input split bytes=337
        Spilled Records=0
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=460
        CPU time spent (ms)=29570
        Physical memory (bytes) snapshot=1461469184
        Virtual memory (bytes) snapshot=6333292544
        Total committed heap usage (bytes)=2409627648
    org.apache.hadoop.examples.terasort.TeraGen$Counters
        CHECKSUM=21472776955442690
    File Input Format Counters 
        Bytes Read=0
    File Output Format Counters 
        Bytes Written=1000000000

real    0m28.836s
user    0m4.985s
sys 0m0.273s
```

### Terasort

```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/saturn/tgen2/* /user/saturn/tsort
```

```
17/12/01 13:37:07 INFO terasort.TeraSort: starting
17/12/01 13:37:08 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512157028577, maxDa
te=1512761828577, sequenceNumber=8, masterKeyId=2 on 172.31.21.54:8020
17/12/01 13:37:08 INFO security.TokenCache: Got dt for hdfs://ip-172-31-21-54.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.21.54:8020, Ident: (token
for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512157028577, maxDate=1512761828577, sequenceNumber=8, masterKeyId=2)
17/12/01 13:37:08 INFO input.FileInputFormat: Total input paths to process : 4
Spent 253ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 256ms
Sampling 10 splits of 32
Making 16 from 100000 sampled records
Computing parititions took 544ms
Spent 802ms computing partitions.
17/12/01 13:37:09 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-21-54.ec2.internal/172.31.21.54:8032
17/12/01 13:37:09 INFO mapreduce.JobSubmitter: number of splits:32
17/12/01 13:37:09 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154882708_0007
17/12/01 13:37:09 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.21.54:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DOB
ESLAO.HQ, renewer=yarn, realUser=, issueDate=1512157028577, maxDate=1512761828577, sequenceNumber=8, masterKeyId=2)
17/12/01 13:37:10 INFO impl.YarnClientImpl: Submitted application application_1512154882708_0007
17/12/01 13:37:10 INFO mapreduce.Job: The url to track the job: http://ip-172-31-21-54.ec2.internal:8088/proxy/application_1512154882708_0007/
17/12/01 13:37:10 INFO mapreduce.Job: Running job: job_1512154882708_0007
17/12/01 13:37:17 INFO mapreduce.Job: Job job_1512154882708_0007 running in uber mode : false
17/12/01 13:37:17 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:37:24 INFO mapreduce.Job:  map 9% reduce 0%
17/12/01 13:37:25 INFO mapreduce.Job:  map 13% reduce 0%
17/12/01 13:37:30 INFO mapreduce.Job:  map 16% reduce 0%
17/12/01 13:37:31 INFO mapreduce.Job:  map 25% reduce 0%
17/12/01 13:37:34 INFO mapreduce.Job:  map 72% reduce 0%
17/12/01 13:37:35 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:37:43 INFO mapreduce.Job:  map 100% reduce 38%
17/12/01 13:37:45 INFO mapreduce.Job:  map 100% reduce 56%
17/12/01 13:37:46 INFO mapreduce.Job:  map 100% reduce 100%
17/12/01 13:37:46 INFO mapreduce.Job: Job job_1512154882708_0007 completed successfully
17/12/01 13:37:46 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=439899224
                FILE: Number of bytes written=879963633
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1000004352
                HDFS: Number of bytes written=1000000000
                HDFS: Number of read operations=144
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=32
        Job Counters
                Launched map tasks=32
                Launched reduce tasks=16
                Data-local map tasks=31
                Rack-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=416500
                Total time spent by all reduces in occupied slots (ms)=116832
                Total time spent by all map tasks (ms)=416500
                Total time spent by all reduce tasks (ms)=116832
                Total vcore-seconds taken by all map tasks=416500
                Total vcore-seconds taken by all reduce tasks=116832
                Total megabyte-seconds taken by all map tasks=426496000
                Total megabyte-seconds taken by all reduce tasks=119635968
        Map-Reduce Framework
                Map input records=10000000
                Map output records=10000000
                Map output bytes=1020000000
                Map output materialized bytes=434073421
                Input split bytes=4352
                Combine input records=0
                Combine output records=0
                Reduce input groups=10000000
                Reduce shuffle bytes=434073421
                Reduce input records=10000000
                Reduce output records=10000000
                Spilled Records=20000000
                Shuffled Maps =512
                Failed Shuffles=0
                Merged Map outputs=512
                GC time elapsed (ms)=3996
                CPU time spent (ms)=189750
                Physical memory (bytes) snapshot=22341206016
                Virtual memory (bytes) snapshot=76716990464
                Total committed heap usage (bytes)=25589448704
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1000000000
        File Output Format Counters
                Bytes Written=1000000000
17/12/01 13:37:46 INFO terasort.TeraSort: done

real    0m40.195s
user    0m6.490s
sys     0m0.294s
```
