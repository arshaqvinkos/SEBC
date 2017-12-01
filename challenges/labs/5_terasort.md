```sh
 time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen 10000000 /user/saturn/tgen/new3
17/12/01 13:36:00 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-42.ec2.internal/172.31.24.42:8032
17/12/01 13:36:01 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ARSHAQVINKOS.HQ, renewer=yarn, realUser=, issueDate=1512156961068, maxDate=1512761761068, sequenceNumber=12, masterKeyId=2 on 172.31.24.42:8020
17/12/01 13:36:01 INFO security.TokenCache: Got dt for hdfs://ip-172-31-24-42.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.24.42:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ARSHAQVINKOS.HQ, renewer=yarn, realUser=, issueDate=1512156961068, maxDate=1512761761068, sequenceNumber=12, masterKeyId=2)
17/12/01 13:36:01 INFO terasort.TeraSort: Generating 10000000 using 2
17/12/01 13:36:01 INFO mapreduce.JobSubmitter: number of splits:2
17/12/01 13:36:01 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154909366_0010
17/12/01 13:36:01 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.24.42:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ARSHAQVINKOS.HQ, renewer=yarn, realUser=, issueDate=1512156961068, maxDate=1512761761068, sequenceNumber=12, masterKeyId=2)
17/12/01 13:36:01 INFO impl.YarnClientImpl: Submitted application application_1512154909366_0010
17/12/01 13:36:01 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-42.ec2.internal:8088/proxy/application_1512154909366_0010/
17/12/01 13:36:01 INFO mapreduce.Job: Running job: job_1512154909366_0010
17/12/01 13:36:09 INFO mapreduce.Job: Job job_1512154909366_0010 running in uber mode : false
17/12/01 13:36:09 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:36:22 INFO mapreduce.Job:  map 82% reduce 0%
17/12/01 13:36:23 INFO mapreduce.Job:  map 92% reduce 0%
17/12/01 13:36:24 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:36:25 INFO mapreduce.Job: Job job_1512154909366_0010 completed successfully
17/12/01 13:36:25 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=246852
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=167
		HDFS: Number of bytes written=1000000000
		HDFS: Number of read operations=8
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=4
	Job Counters 
		Launched map tasks=2
		Other local map tasks=2
		Total time spent by all maps in occupied slots (ms)=26395
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=26395
		Total vcore-seconds taken by all map tasks=26395
		Total megabyte-seconds taken by all map tasks=27028480
	Map-Reduce Framework
		Map input records=10000000
		Map output records=10000000
		Input split bytes=167
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=156
		CPU time spent (ms)=20500
		Physical memory (bytes) snapshot=721522688
		Virtual memory (bytes) snapshot=3191283712
		Total committed heap usage (bytes)=1179648000
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=21472776955442690
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=1000000000

real	0m26.540s
user	0m4.328s
sys	0m0.250s


-bash-4.2$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/saturn/tgen/new3/* /user/saturn/tsort 
17/12/01 13:36:42 INFO terasort.TeraSort: starting
17/12/01 13:36:43 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ARSHAQVINKOS.HQ, renewer=yarn, realUser=, issueDate=1512157003645, maxDate=1512761803645, sequenceNumber=13, masterKeyId=2 on 172.31.24.42:8020
17/12/01 13:36:43 INFO security.TokenCache: Got dt for hdfs://ip-172-31-24-42.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.24.42:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ARSHAQVINKOS.HQ, renewer=yarn, realUser=, issueDate=1512157003645, maxDate=1512761803645, sequenceNumber=13, masterKeyId=2)
17/12/01 13:36:43 INFO input.FileInputFormat: Total input paths to process : 2
Spent 225ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 227ms
Sampling 8 splits of 8
Making 16 from 100000 sampled records
Computing parititions took 519ms
Spent 749ms computing partitions.
17/12/01 13:36:44 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-24-42.ec2.internal/172.31.24.42:8032
17/12/01 13:36:44 INFO mapreduce.JobSubmitter: number of splits:8
17/12/01 13:36:44 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154909366_0011
17/12/01 13:36:44 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.24.42:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ARSHAQVINKOS.HQ, renewer=yarn, realUser=, issueDate=1512157003645, maxDate=1512761803645, sequenceNumber=13, masterKeyId=2)
17/12/01 13:36:45 INFO impl.YarnClientImpl: Submitted application application_1512154909366_0011
17/12/01 13:36:45 INFO mapreduce.Job: The url to track the job: http://ip-172-31-24-42.ec2.internal:8088/proxy/application_1512154909366_0011/
17/12/01 13:36:45 INFO mapreduce.Job: Running job: job_1512154909366_0011
17/12/01 13:36:52 INFO mapreduce.Job: Job job_1512154909366_0011 running in uber mode : false
17/12/01 13:36:52 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:37:05 INFO mapreduce.Job:  map 13% reduce 0%
17/12/01 13:37:06 INFO mapreduce.Job:  map 63% reduce 0%
17/12/01 13:37:07 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:37:31 INFO mapreduce.Job:  map 25% reduce 0%
17/12/01 13:37:31 INFO mapreduce.Job: Job job_1512154909366_0011 failed with state FAILED due to: Invalid event TA_TOO_MANY_FETCH_FAILURE on TaskAttempt attempt_1512154909366_0011_m_000007_1

17/12/01 13:37:31 INFO mapreduce.Job: Counters: 42
	File System Counters
		FILE: Number of bytes read=330
		FILE: Number of bytes written=85290826
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=194693880
		HDFS: Number of bytes written=0
		HDFS: Number of read operations=6
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=0
	Job Counters 
		Failed map tasks=8
		Failed reduce tasks=9
		Killed map tasks=6
		Killed reduce tasks=13
		Launched map tasks=16
		Launched reduce tasks=22
		Other local map tasks=8
		Data-local map tasks=4
		Rack-local map tasks=4
		Total time spent by all maps in occupied slots (ms)=191985
		Total time spent by all reduces in occupied slots (ms)=334180
		Total time spent by all map tasks (ms)=191985
		Total time spent by all reduce tasks (ms)=334180
		Total vcore-seconds taken by all map tasks=191985
		Total vcore-seconds taken by all reduce tasks=334180
		Total megabyte-seconds taken by all map tasks=196592640
		Total megabyte-seconds taken by all reduce tasks=342200320
	Map-Reduce Framework
		Map input records=1946936
		Map output records=1946936
		Map output bytes=198587472
		Map output materialized bytes=85040436
		Input split bytes=280
		Combine input records=0
		Spilled Records=1946936
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=168
		CPU time spent (ms)=10810
		Physical memory (bytes) snapshot=1141653504
		Virtual memory (bytes) snapshot=3175227392
		Total committed heap usage (bytes)=1229979648
	File Input Format Counters 
		Bytes Read=194693600
17/12/01 13:37:31 INFO terasort.TeraSort: done

real	0m50.152s
user	0m6.390s
sys	0m0.265s
```