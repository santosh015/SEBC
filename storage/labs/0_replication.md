```
[hdfs@ip-172-31-10-136 ~]$ hadoop distcp hdfs://54.254.163.203:8020/santosh015/* hdfs://ip-172-31-10-136/tmp/dist
16/12/06 03:50:23 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://54.254.163.203:8020/santosh015/*], targetPath=hdfs://ip-172-31-10-136/tmp/dist, targetPathExists=false, filtersFile='null'}
16/12/06 03:50:23 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-10-136.ap-southeast-1.compute.internal/172.31.10.136:8032
16/12/06 03:50:23 ERROR tools.DistCp: Invalid input:
org.apache.hadoop.tools.CopyListing$InvalidInputException: hdfs://54.254.163.203:8020/santosh015/* doesn't exist
	at org.apache.hadoop.tools.GlobbedCopyListing.doBuildListing(GlobbedCopyListing.java:84)
	at org.apache.hadoop.tools.CopyListing.buildListing(CopyListing.java:86)
	at org.apache.hadoop.tools.DistCp.createInputFileListing(DistCp.java:372)
	at org.apache.hadoop.tools.DistCp.execute(DistCp.java:172)
	at org.apache.hadoop.tools.DistCp.run(DistCp.java:123)
	at org.apache.hadoop.util.ToolRunner.run(ToolRunner.java:70)
	at org.apache.hadoop.tools.DistCp.main(DistCp.java:436)
[hdfs@ip-172-31-10-136 ~]$ hadoop distcp hdfs://54.254.163.203:8020/tmp/santosh015/* hdfs://ip-172-31-10-136/tmp/dist
16/12/06 03:50:40 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://54.254.163.203:8020/tmp/santosh015/*], targetPath=hdfs://ip-172-31-10-136/tmp/dist, targetPathExists=false, filtersFile='null'}
16/12/06 03:50:40 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-10-136.ap-southeast-1.compute.internal/172.31.10.136:8032
16/12/06 03:50:41 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 3; dirCnt = 0
16/12/06 03:50:41 INFO tools.SimpleCopyListing: Build file listing completed.
16/12/06 03:50:41 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
16/12/06 03:50:41 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
16/12/06 03:50:41 INFO tools.DistCp: Number of paths in the copy list: 3
16/12/06 03:50:41 INFO tools.DistCp: Number of paths in the copy list: 3
16/12/06 03:50:41 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-10-136.ap-southeast-1.compute.internal/172.31.10.136:8032
16/12/06 03:50:42 INFO mapreduce.JobSubmitter: number of splits:3
16/12/06 03:50:42 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1480994945346_0001
16/12/06 03:50:42 INFO impl.YarnClientImpl: Submitted application application_1480994945346_0001
16/12/06 03:50:42 INFO mapreduce.Job: The url to track the job: http://ip-172-31-10-136.ap-southeast-1.compute.internal:8088/proxy/application_1480994945346_0001/
16/12/06 03:50:42 INFO tools.DistCp: DistCp job-id: job_1480994945346_0001
16/12/06 03:50:42 INFO mapreduce.Job: Running job: job_1480994945346_0001
16/12/06 03:50:49 INFO mapreduce.Job: Job job_1480994945346_0001 running in uber mode : false
16/12/06 03:50:49 INFO mapreduce.Job:  map 0% reduce 0%
16/12/06 03:50:57 INFO mapreduce.Job:  map 100% reduce 0%
16/12/06 03:50:58 INFO mapreduce.Job: Job job_1480994945346_0001 completed successfully
16/12/06 03:50:58 INFO mapreduce.Job: Counters: 33
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=381102
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=52430246
		HDFS: Number of bytes written=52428800
		HDFS: Number of read operations=54
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=12
	Job Counters
		Launched map tasks=3
		Other local map tasks=3
		Total time spent by all maps in occupied slots (ms)=13663
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=13663
		Total vcore-seconds taken by all map tasks=13663
		Total megabyte-seconds taken by all map tasks=13990912
	Map-Reduce Framework
		Map input records=3
		Map output records=0
		Input split bytes=348
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=210
		CPU time spent (ms)=4750
		Physical memory (bytes) snapshot=542298112
		Virtual memory (bytes) snapshot=8332693504
		Total committed heap usage (bytes)=570949632
	File Input Format Counters
		Bytes Read=1098
	File Output Format Counters
		Bytes Written=0
	org.apache.hadoop.tools.mapred.CopyMapper$Counter
		BYTESCOPIED=52428800
		BYTESEXPECTED=52428800
		COPY=3
[hdfs@ip-172-31-10-136 ~]$
```
