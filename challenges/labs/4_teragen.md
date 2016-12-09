### Running Teragen
<pre><code>
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 -D dfs.blocksize=16m -Dmapred.map.tasks.speculative.execution=false 51200000 tgen512m

real	1m8.079s
user	0m6.489s
sys	0m0.833s
</code></pre>

### 8 files as output
<pre><code>
[raffles@ip-172-31-9-248 ~]$ hadoop fs -ls /user/raffles/tgen512m
Found 9 items
-rw-r--r--   3 raffles shops          0 2016-12-09 02:29 /user/raffles/tgen512m/_SUCCESS
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00000
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00001
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00002
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00003
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00004
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00005
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00006
-rw-r--r--   3 raffles shops  640000000 2016-12-09 02:29 /user/raffles/tgen512m/part-m-00007
[raffles@ip-172-31-9-248 ~]
</code></pre>

### Block information
<pre><code>
[raffles@ip-172-31-9-248 ~]$ hdfs fsck  /user/raffles/tgen512m
Connecting to namenode via http://ip-172-31-9-246.ap-southeast-1.compute.internal:50070
FSCK started by raffles (auth:SIMPLE) from /172.31.9.248 for path /user/raffles/tgen512m at Fri Dec 09 02:31:37 UTC 2016
.........Status: HEALTHY
 Total size:	5120000000 B
 Total dirs:	1
 Total files:	9
 Total symlinks:		0
 Total blocks (validated):	312 (avg. block size 16410256 B)
 Minimally replicated blocks:	312 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Dec 09 02:31:37 UTC 2016 in 6 milliseconds


The filesystem under path '/user/raffles/tgen512m' is HEALTHY
[raffles@ip-172-31-9-248 ~]$

</code></pre>
