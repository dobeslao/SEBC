# Kerberize the cluster

## Run the Hadoop pi program as user haley

```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 10 100
```

```
17/12/01 13:44:48 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-21-54.ec2.internal/172.31.21.54:8032
17/12/01 13:44:48 INFO hdfs.DFSClient: Created token for haley: HDFS_DELEGATION_TOKEN owner=haley@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512157488416, maxDate=1512762288416, sequenceNumber=9, masterKeyId=2 on 172.31.21.54:8020
17/12/01 13:44:48 INFO security.TokenCache: Got dt for hdfs://ip-172-31-21-54.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.21.54:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512157488416, maxDate=1512762288416, sequenceNumber=9, masterKeyId=2)
17/12/01 13:44:48 INFO input.FileInputFormat: Total input paths to process : 10
17/12/01 13:44:48 INFO mapreduce.JobSubmitter: number of splits:10
17/12/01 13:44:48 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154882708_0008
17/12/01 13:44:48 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.21.54:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@DOBESLAO.HQ, renewer=yarn, realUser=, issueDate=1512157488416, maxDate=1512762288416, sequenceNumber=9, masterKeyId=2)
17/12/01 13:44:49 INFO impl.YarnClientImpl: Submitted application application_1512154882708_0008
17/12/01 13:44:49 INFO mapreduce.Job: The url to track the job: http://ip-172-31-21-54.ec2.internal:8088/proxy/application_1512154882708_0008/
17/12/01 13:44:49 INFO mapreduce.Job: Running job: job_1512154882708_0008
17/12/01 13:44:56 INFO mapreduce.Job: Job job_1512154882708_0008 running in uber mode : false
17/12/01 13:44:56 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:45:06 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:45:11 INFO mapreduce.Job:  map 100% reduce 100%
17/12/01 13:45:11 INFO mapreduce.Job: Job job_1512154882708_0008 completed successfully
17/12/01 13:45:11 INFO mapreduce.Job: Counters: 50
    File System Counters
        FILE: Number of bytes read=94
        FILE: Number of bytes written=1364093
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=2840
        HDFS: Number of bytes written=215
        HDFS: Number of read operations=43
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=3
    Job Counters 
        Launched map tasks=10
        Launched reduce tasks=1
        Data-local map tasks=7
        Rack-local map tasks=3
        Total time spent by all maps in occupied slots (ms)=86465
        Total time spent by all reduces in occupied slots (ms)=2651
        Total time spent by all map tasks (ms)=86465
        Total time spent by all reduce tasks (ms)=2651
        Total vcore-seconds taken by all map tasks=86465
        Total vcore-seconds taken by all reduce tasks=2651
        Total megabyte-seconds taken by all map tasks=88540160
        Total megabyte-seconds taken by all reduce tasks=2714624
    Map-Reduce Framework
        Map input records=10
        Map output records=20
        Map output bytes=180
        Map output materialized bytes=340
        Input split bytes=1660
        Combine input records=0
        Combine output records=0
        Reduce input groups=2
        Reduce shuffle bytes=340
        Reduce input records=20
        Reduce output records=0
        Spilled Records=40
        Shuffled Maps =10
        Failed Shuffles=0
        Merged Map outputs=10
        GC time elapsed (ms)=398
        CPU time spent (ms)=6640
        Physical memory (bytes) snapshot=5314052096
        Virtual memory (bytes) snapshot=17610465280
        Total committed heap usage (bytes)=5536481280
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=1180
    File Output Format Counters 
        Bytes Written=97

real    0m25.861s
user    0m4.633s
sys 0m0.296s
```
