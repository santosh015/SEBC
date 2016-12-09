### Running pi as orchard
<pre><code>
[orchard@ip-172-31-9-248 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_2800
Default principal: orchard@SANTOSH015.SG

Valid starting     Expires            Service principal
12/09/16 03:45:33  12/10/16 03:45:33  krbtgt/SANTOSH015.SG@SANTOSH015.SG
	renew until 12/09/16 03:45:33
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar pi -Dmapreduce.job.maps=80 -Dmapreduce.job.reduces=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 16 1000

real	0m35.693s
user	0m5.758s
sys	0m0.299s

</code></pre>
