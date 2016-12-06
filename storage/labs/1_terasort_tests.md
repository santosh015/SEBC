```
[hdfs@ip-172-31-10-136 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-examples.jar terasort /tmp/teragen/ /tmp/sorted
16/12/06 02:53:46 INFO terasort.TeraSort: starting
16/12/06 02:53:48 INFO input.FileInputFormat: Total input paths to process : 2
Spent 228ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 234ms
Sampling 8 splits of 8
Making 8 from 100000 sampled records
Computing parititions took 758ms
Spent 996ms computing partitions.
16/12/06 02:53:49 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-10-136.ap-southeast-1.compute.internal/172.31.10.136:8032
16/12/06 02:53:49 INFO mapreduce.JobSubmitter: number of splits:8
16/12/06 02:53:49 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1480927784602_0003
16/12/06 02:53:50 INFO impl.YarnClientImpl: Submitted application application_1480927784602_0003
16/12/06 02:53:50 INFO mapreduce.Job: The url to track the job: http://ip-172-31-10-136.ap-southeast-1.compute.internal:8088/proxy/application_1480927784602_0003/
16/12/06 02:53:50 INFO mapreduce.Job: Running job: job_1480927784602_0003
16/12/06 02:53:56 INFO mapreduce.Job: Job job_1480927784602_0003 running in uber mode : false
16/12/06 02:53:56 INFO mapreduce.Job:  map 0% reduce 0%
16/12/06 02:54:08 INFO mapreduce.Job:  map 75% reduce 0%
16/12/06 02:54:09 INFO mapreduce.Job:  map 100% reduce 0%
16/12/06 02:54:21 INFO mapreduce.Job:  map 100% reduce 100%
16/12/06 02:54:22 INFO mapreduce.Job: Job job_1480927784602_0003 completed successfully
16/12/06 02:54:22 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=464490453
		FILE: Number of bytes written=927677399
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1048577200
		HDFS: Number of bytes written=1048576000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters
		Launched map tasks=8
		Launched reduce tasks=8
		Data-local map tasks=8
		Total time spent by all maps in occupied slots (ms)=82319
		Total time spent by all reduces in occupied slots (ms)=74302
		Total time spent by all map tasks (ms)=82319
		Total time spent by all reduce tasks (ms)=74302
		Total vcore-seconds taken by all map tasks=82319
		Total vcore-seconds taken by all reduce tasks=74302
		Total megabyte-seconds taken by all map tasks=84294656
		Total megabyte-seconds taken by all reduce tasks=76085248
	Map-Reduce Framework
		Map input records=10485760
		Map output records=10485760
		Map output bytes=1069547520
		Map output materialized bytes=461209522
		Input split bytes=1200
		Combine input records=0
		Combine output records=0
		Reduce input groups=10485760
		Reduce shuffle bytes=461209522
		Reduce input records=10485760
		Reduce output records=10485760
		Spilled Records=20971520
		Shuffled Maps =64
		Failed Shuffles=0
		Merged Map outputs=64
		GC time elapsed (ms)=3668
		CPU time spent (ms)=119070
		Physical memory (bytes) snapshot=7829016576
		Virtual memory (bytes) snapshot=44579012608
		Total committed heap usage (bytes)=8683257856
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=1048576000
	File Output Format Counters
		Bytes Written=1048576000
16/12/06 02:54:22 INFO terasort.TeraSort: done

real	0m38.149s
user	0m9.810s
sys	0m1.048s
[hdfs@ip-172-31-10-136 ~]$
```
