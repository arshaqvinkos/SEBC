

## Teragen Commands and Results

```sh
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-exames.jar teragen -Dmapred.map.tasks=12 -Ddfs.block.size=33554432 -Dmapreduce.map.memory.mb=512 65536000 /user/saturn/tgen
17/12/01 12:40:32 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-42.ec2.internal/172.31.24.42:8032
17/12/01 12:40:32 INFO terasort.TeraSort: Generating 65536000 using 12
17/12/01 12:40:32 INFO mapreduce.JobSubmitter: number of splits:12
17/12/01 12:40:32 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/12/01 12:40:32 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 12:40:32 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512152276215_0001
17/12/01 12:40:33 INFO impl.YarnClientImpl: Submitted application application_1512152276215_0001
17/12/01 12:40:33 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-42.ec2.internal:8088/proxy/application_1512152276215_0001/
17/12/01 12:40:33 INFO mapreduce.Job: Running job: job_1512152276215_0001
17/12/01 12:40:39 INFO mapreduce.Job: Job job_1512152276215_0001 running in uber mode : false
17/12/01 12:40:39 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 12:40:50 INFO mapreduce.Job:  map 9% reduce 0%
17/12/01 12:40:52 INFO mapreduce.Job:  map 25% reduce 0%
17/12/01 12:40:53 INFO mapreduce.Job:  map 26% reduce 0%
17/12/01 12:40:55 INFO mapreduce.Job:  map 34% reduce 0%
17/12/01 12:40:56 INFO mapreduce.Job:  map 35% reduce 0%
17/12/01 12:40:58 INFO mapreduce.Job:  map 42% reduce 0%
17/12/01 12:40:59 INFO mapreduce.Job:  map 43% reduce 0%
17/12/01 12:41:01 INFO mapreduce.Job:  map 50% reduce 0%
17/12/01 12:41:02 INFO mapreduce.Job:  map 52% reduce 0%
17/12/01 12:41:04 INFO mapreduce.Job:  map 58% reduce 0%
17/12/01 12:41:05 INFO mapreduce.Job:  map 59% reduce 0%
17/12/01 12:41:07 INFO mapreduce.Job:  map 67% reduce 0%
17/12/01 12:41:08 INFO mapreduce.Job:  map 68% reduce 0%
17/12/01 12:41:10 INFO mapreduce.Job:  map 75% reduce 0%
17/12/01 12:41:14 INFO mapreduce.Job:  map 83% reduce 0%
17/12/01 12:41:17 INFO mapreduce.Job:  map 91% reduce 0%
17/12/01 12:41:18 INFO mapreduce.Job:  map 92% reduce 0%
17/12/01 12:41:20 INFO mapreduce.Job:  map 98% reduce 0%
17/12/01 12:41:21 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 12:41:22 INFO mapreduce.Job: Job job_1512152276215_0001 completed successfully
17/12/01 12:41:22 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1471838
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
		Total time spent by all maps in occupied slots (ms)=432924
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=432924
		Total vcore-seconds taken by all map tasks=432924
		Total megabyte-seconds taken by all map tasks=443314176
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=2109
		CPU time spent (ms)=135900
		Physical memory (bytes) snapshot=2410225664
		Virtual memory (bytes) snapshot=13746806784
		Total committed heap usage (bytes)=4485808128
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000

```

## Time Results

```sh
real	0m51.850s
user	0m4.503s
sys	0m0.269s
```

## HDFS DFS

```sh
hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn hadoop          0 2017-12-01 12:41 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:41 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:41 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:41 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn hadoop  546133400 2017-12-01 12:41 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn hadoop  546133300 2017-12-01 12:41 /user/saturn/tgen/part-m-00011

```

## HDFS fsck

```sh
hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-24-42.ec2.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.26.197 for path /user/saturn at Fri Dec 01 18:43:28 UTC 2017
.............Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	3
 Total files:	13
 Total symlinks:		0
 Total blocks (validated):	204 (avg. block size 32125490 B)
 Minimally replicated blocks:	204 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Dec 01 18:43:28 UTC 2017 in 10 milliseconds


The filesystem under path '/user/saturn' is HEALTHY

```