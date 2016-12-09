### Running terasort as raffles
<pre><code>
[raffles@ip-172-31-9-248 ~]$ kinit raffles
Password for raffles@SANTOSH015.SG:
[raffles@ip-172-31-9-248 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_2700
Default principal: raffles@SANTOSH015.SG

Valid starting     Expires            Service principal
12/09/16 03:42:41  12/10/16 03:42:41  krbtgt/SANTOSH015.SG@SANTOSH015.SG
	renew until 12/09/16 03:42:41
[raffles@ip-172-31-9-248 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=80 -Dmapreduce.job.reduces=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 -Dmapreduce.input.fileinputformat.split.minsize=134217728 -Dmapreduce.input.fileinputformat.split.maxsize=134217728 /user/raffles/tgen512m /user/raffles/tsort512m
16/12/09 03:42:53 INFO terasort.TeraSort: starting
16/12/09 03:42:54 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@SANTOSH015.SG, renewer=yarn, realUser=, issueDate=1481254974363, maxDate=1481859774363, sequenceNumber=1, masterKeyId=6 on 172.31.9.246:8020
16/12/09 03:42:54 INFO security.TokenCache: Got dt for hdfs://ip-172-31-9-246.ap-southeast-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.9.246:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@SANTOSH015.SG, renewer=yarn, realUser=, issueDate=1481254974363, maxDate=1481859774363, sequenceNumber=1, masterKeyId=6)
16/12/09 03:42:54 INFO input.FileInputFormat: Total input paths to process : 8
Spent 470ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 474ms
Sampling 10 splits of 40
Making 8 from 100000 sampled records
Computing parititions took 685ms
Spent 1160ms computing partitions.
16/12/09 03:42:55 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-9-246.ap-southeast-1.compute.internal/172.31.9.246:8032
16/12/09 03:42:55 INFO mapreduce.JobSubmitter: number of splits:40
16/12/09 03:42:55 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1481254796672_0001
16/12/09 03:42:55 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.9.246:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@SANTOSH015.SG, renewer=yarn, realUser=, issueDate=1481254974363, maxDate=1481859774363, sequenceNumber=1, masterKeyId=6)
16/12/09 03:42:57 INFO impl.YarnClientImpl: Submitted application application_1481254796672_0001
16/12/09 03:42:57 INFO mapreduce.Job: The url to track the job: http://ip-172-31-9-246.ap-southeast-1.compute.internal:8088/proxy/application_1481254796672_0001/
16/12/09 03:42:57 INFO mapreduce.Job: Running job: job_1481254796672_0001
16/12/09 03:43:07 INFO mapreduce.Job: Job job_1481254796672_0001 running in uber mode : false
16/12/09 03:43:07 INFO mapreduce.Job:  map 0% reduce 0%
16/12/09 03:43:20 INFO mapreduce.Job:  map 2% reduce 0%
16/12/09 03:43:21 INFO mapreduce.Job:  map 5% reduce 0%
16/12/09 03:43:24 INFO mapreduce.Job:  map 8% reduce 0%
16/12/09 03:43:28 INFO mapreduce.Job:  map 13% reduce 0%
16/12/09 03:43:29 INFO mapreduce.Job:  map 28% reduce 0%
16/12/09 03:43:33 INFO mapreduce.Job:  map 37% reduce 0%
16/12/09 03:43:34 INFO mapreduce.Job:  map 38% reduce 0%
16/12/09 03:43:36 INFO mapreduce.Job:  map 41% reduce 0%
16/12/09 03:43:37 INFO mapreduce.Job:  map 43% reduce 0%
16/12/09 03:43:38 INFO mapreduce.Job:  map 44% reduce 0%
16/12/09 03:43:39 INFO mapreduce.Job:  map 45% reduce 0%
16/12/09 03:43:46 INFO mapreduce.Job:  map 47% reduce 0%
16/12/09 03:43:47 INFO mapreduce.Job:  map 52% reduce 0%
16/12/09 03:43:48 INFO mapreduce.Job:  map 65% reduce 0%
16/12/09 03:43:49 INFO mapreduce.Job:  map 67% reduce 0%
16/12/09 03:43:50 INFO mapreduce.Job:  map 69% reduce 0%
16/12/09 03:43:51 INFO mapreduce.Job:  map 79% reduce 0%
16/12/09 03:43:52 INFO mapreduce.Job:  map 82% reduce 0%
16/12/09 03:44:01 INFO mapreduce.Job:  map 86% reduce 0%
16/12/09 03:44:05 INFO mapreduce.Job:  map 93% reduce 0%
16/12/09 03:44:07 INFO mapreduce.Job:  map 98% reduce 7%
16/12/09 03:44:08 INFO mapreduce.Job:  map 99% reduce 20%
16/12/09 03:44:09 INFO mapreduce.Job:  map 100% reduce 20%
16/12/09 03:44:10 INFO mapreduce.Job:  map 100% reduce 28%
16/12/09 03:44:11 INFO mapreduce.Job:  map 100% reduce 34%
16/12/09 03:44:13 INFO mapreduce.Job:  map 100% reduce 47%
16/12/09 03:44:14 INFO mapreduce.Job:  map 100% reduce 62%
16/12/09 03:44:16 INFO mapreduce.Job:  map 100% reduce 67%
16/12/09 03:44:17 INFO mapreduce.Job:  map 100% reduce 70%
16/12/09 03:44:19 INFO mapreduce.Job:  map 100% reduce 73%
16/12/09 03:44:20 INFO mapreduce.Job:  map 100% reduce 75%
16/12/09 03:44:21 INFO mapreduce.Job:  map 100% reduce 76%
16/12/09 03:44:22 INFO mapreduce.Job:  map 100% reduce 78%
16/12/09 03:44:23 INFO mapreduce.Job:  map 100% reduce 81%
16/12/09 03:44:24 INFO mapreduce.Job:  map 100% reduce 82%
16/12/09 03:44:25 INFO mapreduce.Job:  map 100% reduce 87%
16/12/09 03:44:26 INFO mapreduce.Job:  map 100% reduce 88%
16/12/09 03:44:27 INFO mapreduce.Job:  map 100% reduce 89%
16/12/09 03:44:28 INFO mapreduce.Job:  map 100% reduce 92%
16/12/09 03:44:29 INFO mapreduce.Job:  map 100% reduce 93%
16/12/09 03:44:30 INFO mapreduce.Job:  map 100% reduce 96%
16/12/09 03:44:31 INFO mapreduce.Job:  map 100% reduce 99%
16/12/09 03:44:33 INFO mapreduce.Job:  map 100% reduce 100%
16/12/09 03:44:34 INFO mapreduce.Job: Job job_1481254796672_0001 completed successfully
16/12/09 03:44:34 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=2292029424
		FILE: Number of bytes written=4552233489
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=5120006360
		HDFS: Number of bytes written=5120000000
		HDFS: Number of read operations=144
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters
		Launched map tasks=40
		Launched reduce tasks=8
		Data-local map tasks=40
		Total time spent by all maps in occupied slots (ms)=721264
		Total time spent by all reduces in occupied slots (ms)=276253
		Total time spent by all map tasks (ms)=721264
		Total time spent by all reduce tasks (ms)=276253
		Total vcore-seconds taken by all map tasks=721264
		Total vcore-seconds taken by all reduce tasks=276253
		Total megabyte-seconds taken by all map tasks=738574336
		Total megabyte-seconds taken by all reduce tasks=282883072
	Map-Reduce Framework
		Map input records=51200000
		Map output records=51200000
		Map output bytes=5222400000
		Map output materialized bytes=2254176403
		Input split bytes=6360
		Combine input records=0
		Combine output records=0
		Reduce input groups=51200000
		Reduce shuffle bytes=2254176403
		Reduce input records=51200000
		Reduce output records=51200000
		Spilled Records=102400000
		Shuffled Maps =320
		Failed Shuffles=0
		Merged Map outputs=320
		GC time elapsed (ms)=18412
		CPU time spent (ms)=582220
		Physical memory (bytes) snapshot=27032260608
		Virtual memory (bytes) snapshot=133459099648
		Total committed heap usage (bytes)=27149729792
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=5120000000
	File Output Format Counters
		Bytes Written=5120000000
16/12/09 03:44:34 INFO terasort.TeraSort: done

real	1m42.724s
user	0m9.917s
sys	0m1.073s
[raffles@ip-172-31-9-248 ~] 


</code></pre>
