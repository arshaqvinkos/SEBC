#Create Directory

```sh 
[hdfs@ec2-54-208-253-250 ~]$ hdfs dfs -mkdir /user/arshaqvinkos
[hdfs@ec2-54-208-253-250 ~]$ hdfs dfs -chown arshaqvinkos:hadoop /user/arshaqvinkos
```

#Teragen Generate 10GB File

```sh
time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen  -Dmapred.map.tasks=4 -Ddfs.block.size=1048576 100000000 /user/arshaqvinkos/teragen
```

#Teragen Results
```sh
[hdfs@ec2-54-208-253-250 ~]$ time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen  -Dmapred.map.tasks=4 -Ddfs.block.size=1048576 100000000 /user/arshaqvinkos/teragen
17/11/28 11:29:32 INFO client.RMProxy: Connecting to ResourceManager at ec2-34-235-121-19.compute-1.amazonaws.com/172.31.33.222:8032
17/11/28 11:29:33 INFO terasort.TeraGen: Generating 100000000 using 4
17/11/28 11:29:33 INFO mapreduce.JobSubmitter: number of splits:4
17/11/28 11:29:33 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/28 11:29:33 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/28 11:29:33 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511881338020_0006
17/11/28 11:29:33 INFO impl.YarnClientImpl: Submitted application application_1511881338020_0006
17/11/28 11:29:33 INFO mapreduce.Job: The url to track the job: http://ec2-34-235-121-19.compute-1.amazonaws.com:8088/proxy/application_1511881338020_0006/
17/11/28 11:29:33 INFO mapreduce.Job: Running job: job_1511881338020_0006
17/11/28 11:29:38 INFO mapreduce.Job: Job job_1511881338020_0006 running in uber mode : false
17/11/28 11:29:38 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 11:29:55 INFO mapreduce.Job:  map 20% reduce 0%
17/11/28 11:30:01 INFO mapreduce.Job:  map 28% reduce 0%
17/11/28 11:30:13 INFO mapreduce.Job:  map 36% reduce 0%
17/11/28 11:30:19 INFO mapreduce.Job:  map 46% reduce 0%
17/11/28 11:30:25 INFO mapreduce.Job:  map 54% reduce 0%
17/11/28 11:30:31 INFO mapreduce.Job:  map 61% reduce 0%
17/11/28 11:30:37 INFO mapreduce.Job:  map 66% reduce 0%
17/11/28 11:30:43 INFO mapreduce.Job:  map 75% reduce 0%
17/11/28 11:30:49 INFO mapreduce.Job:  map 80% reduce 0%
17/11/28 11:30:55 INFO mapreduce.Job:  map 85% reduce 0%
17/11/28 11:31:01 INFO mapreduce.Job:  map 93% reduce 0%
17/11/28 11:31:06 INFO mapreduce.Job:  map 97% reduce 0%
17/11/28 11:31:07 INFO mapreduce.Job:  map 100% reduce 0%
17/11/28 11:31:10 INFO mapreduce.Job: Job job_1511881338020_0006 completed successfully
17/11/28 11:31:10 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=582316
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=334563
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=334563
		Total vcore-milliseconds taken by all map tasks=334563
		Total megabyte-milliseconds taken by all map tasks=342592512
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=712
		CPU time spent (ms)=168580
		Physical memory (bytes) snapshot=1349611520
		Virtual memory (bytes) snapshot=11268665344
		Total committed heap usage (bytes)=1468530688
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=214760662691937609
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10000000000

real	1m40.153s
user	0m6.387s
sys	0m0.328s
```

#Terasort

```sh
 time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapred.map.tasks=4 /user/arshaqvinkos/teragen/*   /user/arshaqvinkos/terasort
```

#Terasort Results

```sh
[hdfs@ec2-54-208-253-250 ~]$  time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapred.map.tasks=4 /user/arshaqvinkos/teragen/*   /user/arshaqvinkos/terasort
17/11/28 12:56:43 INFO terasort.TeraSort: starting
17/11/28 12:56:44 INFO input.FileInputFormat: Total input paths to process : 4
Spent 585ms computing base-splits.
Spent 45ms computing TeraScheduler splits.
Computing input splits took 630ms
Sampling 10 splits of 9540
Making 16 from 100000 sampled records
Computing parititions took 569ms
Spent 1201ms computing partitions.
17/11/28 12:56:45 INFO client.RMProxy: Connecting to ResourceManager at ec2-34-235-121-19.compute-1.amazonaws.com/172.31.33.222:8032
17/11/28 12:56:45 INFO mapreduce.JobSubmitter: number of splits:9540
17/11/28 12:56:45 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/28 12:56:45 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511894187200_0001
17/11/28 12:56:46 INFO impl.YarnClientImpl: Submitted application application_1511894187200_0001
17/11/28 12:56:46 INFO mapreduce.Job: The url to track the job: http://ec2-34-235-121-19.compute-1.amazonaws.com:8088/proxy/application_1511894187200_0001/
17/11/28 12:56:46 INFO mapreduce.Job: Running job: job_1511894187200_0001
17/11/28 12:56:52 INFO mapreduce.Job: Job job_1511894187200_0001 running in uber mode : false
17/11/28 12:56:52 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 12:57:14 INFO mapreduce.Job:  map 1% reduce 0%
17/11/28 12:57:44 INFO mapreduce.Job:  map 2% reduce 0%
17/11/28 12:58:13 INFO mapreduce.Job:  map 3% reduce 0%
17/11/28 12:58:40 INFO mapreduce.Job:  map 4% reduce 0%
17/11/28 12:59:11 INFO mapreduce.Job:  map 5% reduce 0%
17/11/28 12:59:41 INFO mapreduce.Job:  map 6% reduce 0%
17/11/28 13:00:09 INFO mapreduce.Job:  map 7% reduce 0%
17/11/28 13:00:38 INFO mapreduce.Job:  map 8% reduce 0%
17/11/28 13:01:08 INFO mapreduce.Job:  map 9% reduce 0%
17/11/28 13:01:37 INFO mapreduce.Job:  map 10% reduce 0%
17/11/28 13:02:07 INFO mapreduce.Job:  map 11% reduce 0%
17/11/28 13:02:35 INFO mapreduce.Job:  map 12% reduce 0%
17/11/28 13:03:06 INFO mapreduce.Job:  map 13% reduce 0%
17/11/28 13:03:35 INFO mapreduce.Job:  map 14% reduce 0%
17/11/28 13:04:02 INFO mapreduce.Job:  map 15% reduce 0%
17/11/28 13:04:31 INFO mapreduce.Job:  map 16% reduce 0%
17/11/28 13:04:59 INFO mapreduce.Job:  map 17% reduce 0%
17/11/28 13:05:28 INFO mapreduce.Job:  map 18% reduce 0%
17/11/28 13:05:57 INFO mapreduce.Job:  map 19% reduce 0%
17/11/28 13:06:26 INFO mapreduce.Job:  map 20% reduce 0%
17/11/28 13:06:53 INFO mapreduce.Job:  map 21% reduce 0%
17/11/28 13:07:21 INFO mapreduce.Job:  map 22% reduce 0%
17/11/28 13:07:50 INFO mapreduce.Job:  map 23% reduce 0%
17/11/28 13:08:18 INFO mapreduce.Job:  map 24% reduce 0%
17/11/28 13:08:46 INFO mapreduce.Job:  map 25% reduce 0%
17/11/28 13:09:16 INFO mapreduce.Job:  map 26% reduce 0%
17/11/28 13:09:44 INFO mapreduce.Job:  map 27% reduce 0%
17/11/28 13:10:12 INFO mapreduce.Job:  map 28% reduce 0%
17/11/28 13:10:41 INFO mapreduce.Job:  map 29% reduce 0%
17/11/28 13:11:11 INFO mapreduce.Job:  map 30% reduce 0%
17/11/28 13:11:38 INFO mapreduce.Job:  map 31% reduce 0%
17/11/28 13:12:07 INFO mapreduce.Job:  map 32% reduce 0%
17/11/28 13:12:36 INFO mapreduce.Job:  map 33% reduce 0%
17/11/28 13:13:06 INFO mapreduce.Job:  map 34% reduce 0%
17/11/28 13:13:35 INFO mapreduce.Job:  map 35% reduce 0%
17/11/28 13:14:05 INFO mapreduce.Job:  map 36% reduce 0%
17/11/28 13:14:34 INFO mapreduce.Job:  map 37% reduce 0%
17/11/28 13:15:05 INFO mapreduce.Job:  map 38% reduce 0%
17/11/28 13:15:32 INFO mapreduce.Job:  map 39% reduce 0%
17/11/28 13:16:02 INFO mapreduce.Job:  map 40% reduce 0%
17/11/28 13:16:30 INFO mapreduce.Job:  map 41% reduce 0%
17/11/28 13:16:58 INFO mapreduce.Job:  map 42% reduce 0%
17/11/28 13:17:28 INFO mapreduce.Job:  map 43% reduce 0%
17/11/28 13:17:55 INFO mapreduce.Job:  map 44% reduce 0%
17/11/28 13:18:24 INFO mapreduce.Job:  map 45% reduce 0%
17/11/28 13:18:53 INFO mapreduce.Job:  map 46% reduce 0%
17/11/28 13:19:23 INFO mapreduce.Job:  map 47% reduce 0%
17/11/28 13:19:50 INFO mapreduce.Job:  map 48% reduce 0%
17/11/28 13:20:18 INFO mapreduce.Job:  map 49% reduce 0%
17/11/28 13:20:47 INFO mapreduce.Job:  map 50% reduce 0%
17/11/28 13:21:15 INFO mapreduce.Job:  map 51% reduce 0%
17/11/28 13:21:44 INFO mapreduce.Job:  map 52% reduce 0%
17/11/28 13:22:11 INFO mapreduce.Job:  map 53% reduce 0%
17/11/28 13:22:40 INFO mapreduce.Job:  map 54% reduce 0%
17/11/28 13:23:10 INFO mapreduce.Job:  map 55% reduce 0%
17/11/28 13:23:39 INFO mapreduce.Job:  map 56% reduce 0%
17/11/28 13:24:07 INFO mapreduce.Job:  map 57% reduce 0%
17/11/28 13:24:38 INFO mapreduce.Job:  map 58% reduce 0%
17/11/28 13:25:07 INFO mapreduce.Job:  map 59% reduce 0%
17/11/28 13:25:36 INFO mapreduce.Job:  map 60% reduce 0%
17/11/28 13:26:06 INFO mapreduce.Job:  map 61% reduce 0%
17/11/28 13:26:36 INFO mapreduce.Job:  map 62% reduce 0%
17/11/28 13:27:06 INFO mapreduce.Job:  map 63% reduce 0%
17/11/28 13:27:34 INFO mapreduce.Job:  map 64% reduce 0%
17/11/28 13:28:03 INFO mapreduce.Job:  map 65% reduce 0%
17/11/28 13:28:32 INFO mapreduce.Job:  map 66% reduce 0%
17/11/28 13:29:00 INFO mapreduce.Job:  map 67% reduce 0%
17/11/28 13:29:28 INFO mapreduce.Job:  map 68% reduce 0%
17/11/28 13:29:56 INFO mapreduce.Job:  map 69% reduce 0%
17/11/28 13:30:26 INFO mapreduce.Job:  map 70% reduce 0%
17/11/28 13:30:55 INFO mapreduce.Job:  map 71% reduce 0%
17/11/28 13:31:22 INFO mapreduce.Job:  map 72% reduce 0%
17/11/28 13:31:51 INFO mapreduce.Job:  map 73% reduce 0%
17/11/28 13:32:20 INFO mapreduce.Job:  map 74% reduce 0%
17/11/28 13:32:48 INFO mapreduce.Job:  map 75% reduce 0%
17/11/28 13:33:16 INFO mapreduce.Job:  map 76% reduce 0%
17/11/28 13:33:44 INFO mapreduce.Job:  map 77% reduce 0%
17/11/28 13:34:12 INFO mapreduce.Job:  map 78% reduce 0%
17/11/28 13:34:40 INFO mapreduce.Job:  map 79% reduce 0%
17/11/28 13:35:10 INFO mapreduce.Job:  map 80% reduce 0%
17/11/28 13:35:41 INFO mapreduce.Job:  map 80% reduce 1%
17/11/28 13:35:42 INFO mapreduce.Job:  map 80% reduce 2%
17/11/28 13:35:43 INFO mapreduce.Job:  map 80% reduce 3%
17/11/28 13:35:44 INFO mapreduce.Job:  map 80% reduce 5%
17/11/28 13:35:45 INFO mapreduce.Job:  map 80% reduce 11%
17/11/28 13:35:46 INFO mapreduce.Job:  map 80% reduce 13%
17/11/28 13:35:47 INFO mapreduce.Job:  map 80% reduce 15%
17/11/28 13:35:48 INFO mapreduce.Job:  map 80% reduce 17%
17/11/28 13:35:49 INFO mapreduce.Job:  map 80% reduce 18%
17/11/28 13:35:51 INFO mapreduce.Job:  map 80% reduce 19%
17/11/28 13:35:52 INFO mapreduce.Job:  map 80% reduce 21%
17/11/28 13:35:53 INFO mapreduce.Job:  map 81% reduce 21%
17/11/28 13:35:57 INFO mapreduce.Job:  map 81% reduce 23%
17/11/28 13:35:59 INFO mapreduce.Job:  map 81% reduce 24%
17/11/28 13:36:01 INFO mapreduce.Job:  map 81% reduce 25%
17/11/28 13:36:44 INFO mapreduce.Job:  map 82% reduce 25%
17/11/28 13:36:51 INFO mapreduce.Job:  map 82% reduce 26%
17/11/28 13:37:32 INFO mapreduce.Job:  map 83% reduce 26%
17/11/28 13:38:18 INFO mapreduce.Job:  map 84% reduce 26%
17/11/28 13:39:05 INFO mapreduce.Job:  map 85% reduce 26%
17/11/28 13:39:22 INFO mapreduce.Job:  map 85% reduce 27%
17/11/28 13:39:52 INFO mapreduce.Job:  map 86% reduce 27%
17/11/28 13:40:40 INFO mapreduce.Job:  map 87% reduce 27%
17/11/28 13:41:26 INFO mapreduce.Job:  map 88% reduce 27%
17/11/28 13:41:53 INFO mapreduce.Job:  map 88% reduce 28%
17/11/28 13:42:13 INFO mapreduce.Job:  map 89% reduce 28%
17/11/28 13:43:00 INFO mapreduce.Job:  map 90% reduce 28%
17/11/28 13:43:46 INFO mapreduce.Job:  map 91% reduce 28%
17/11/28 13:44:23 INFO mapreduce.Job:  map 91% reduce 29%
17/11/28 13:44:35 INFO mapreduce.Job:  map 92% reduce 29%
17/11/28 13:45:22 INFO mapreduce.Job:  map 93% reduce 29%
17/11/28 13:46:07 INFO mapreduce.Job:  map 94% reduce 29%
17/11/28 13:46:53 INFO mapreduce.Job:  map 94% reduce 30%
17/11/28 13:46:55 INFO mapreduce.Job:  map 95% reduce 30%
17/11/28 13:47:40 INFO mapreduce.Job:  map 96% reduce 30%
17/11/28 13:48:28 INFO mapreduce.Job:  map 97% reduce 30%
17/11/28 13:49:14 INFO mapreduce.Job:  map 98% reduce 30%
17/11/28 13:49:22 INFO mapreduce.Job:  map 98% reduce 31%
17/11/28 13:50:00 INFO mapreduce.Job:  map 99% reduce 31%
17/11/28 13:50:48 INFO mapreduce.Job:  map 100% reduce 31%
17/11/28 13:51:11 INFO mapreduce.Job:  map 100% reduce 32%
17/11/28 13:51:12 INFO mapreduce.Job:  map 100% reduce 34%
17/11/28 13:51:13 INFO mapreduce.Job:  map 100% reduce 35%
17/11/28 13:51:14 INFO mapreduce.Job:  map 100% reduce 37%
17/11/28 13:51:15 INFO mapreduce.Job:  map 100% reduce 42%
17/11/28 13:51:16 INFO mapreduce.Job:  map 100% reduce 44%
17/11/28 13:51:17 INFO mapreduce.Job:  map 100% reduce 50%
17/11/28 13:51:18 INFO mapreduce.Job:  map 100% reduce 57%
17/11/28 13:51:19 INFO mapreduce.Job:  map 100% reduce 58%
17/11/28 13:51:20 INFO mapreduce.Job:  map 100% reduce 61%
17/11/28 13:51:21 INFO mapreduce.Job:  map 100% reduce 66%
17/11/28 13:51:22 INFO mapreduce.Job:  map 100% reduce 68%
17/11/28 13:51:23 INFO mapreduce.Job:  map 100% reduce 72%
17/11/28 13:51:24 INFO mapreduce.Job:  map 100% reduce 75%
17/11/28 13:51:25 INFO mapreduce.Job:  map 100% reduce 78%
17/11/28 13:51:26 INFO mapreduce.Job:  map 100% reduce 80%
17/11/28 13:51:27 INFO mapreduce.Job:  map 100% reduce 84%
17/11/28 13:51:28 INFO mapreduce.Job:  map 100% reduce 85%
17/11/28 13:51:29 INFO mapreduce.Job:  map 100% reduce 86%
17/11/28 13:51:30 INFO mapreduce.Job:  map 100% reduce 87%
17/11/28 13:51:31 INFO mapreduce.Job:  map 100% reduce 88%
17/11/28 13:51:33 INFO mapreduce.Job:  map 100% reduce 91%
17/11/28 13:51:34 INFO mapreduce.Job:  map 100% reduce 92%
17/11/28 13:51:36 INFO mapreduce.Job:  map 100% reduce 95%
17/11/28 13:51:37 INFO mapreduce.Job:  map 100% reduce 97%
17/11/28 13:51:39 INFO mapreduce.Job:  map 100% reduce 99%
17/11/28 13:51:45 INFO mapreduce.Job:  map 100% reduce 100%
17/11/28 13:51:48 INFO mapreduce.Job: Job job_1511894187200_0001 completed successfully
17/11/28 13:51:48 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4434238972
		FILE: Number of bytes written=10167987272
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10001173420
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=28668
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=32
	Job Counters 
		Launched map tasks=9540
		Launched reduce tasks=16
		Data-local map tasks=9540
		Total time spent by all maps in occupied slots (ms)=53123694
		Total time spent by all reduces in occupied slots (ms)=14551140
		Total time spent by all map tasks (ms)=53123694
		Total time spent by all reduce tasks (ms)=14551140
		Total vcore-milliseconds taken by all map tasks=53123694
		Total vcore-milliseconds taken by all reduce tasks=14551140
		Total megabyte-milliseconds taken by all map tasks=54398662656
		Total megabyte-milliseconds taken by all reduce tasks=14900367360
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Map output bytes=10200000000
		Map output materialized bytes=4306106164
		Input split bytes=1173420
		Combine input records=0
		Combine output records=0
		Reduce input groups=100000000
		Reduce shuffle bytes=4306106164
		Reduce input records=100000000
		Reduce output records=100000000
		Spilled Records=200000000
		Shuffled Maps =152640
		Failed Shuffles=0
		Merged Map outputs=152640
		GC time elapsed (ms)=1092904
		CPU time spent (ms)=19378980
		Physical memory (bytes) snapshot=5064149966848
		Virtual memory (bytes) snapshot=26863220731904
		Total committed heap usage (bytes)=6207524831232
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10000000000
	File Output Format Counters 
		Bytes Written=10000000000
17/11/28 13:51:48 INFO terasort.TeraSort: done

real	55m6.210s
user	0m20.392s
sys	0m1.390s
[hdfs@ec2-54-208-253-250 ~]$ 
```



