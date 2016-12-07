## As George after kinit
<pre><code>
[santosh015@ip-172-31-24-59 ~]$ kinit george
Password for george@KSECURITY.COM:
[santosh015@ip-172-31-24-59 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1260
Default principal: george@KSECURITY.COM

Valid starting     Expires            Service principal
12/07/16 10:50:32  12/08/16 10:50:32  krbtgt/KSECURITY.COM@KSECURITY.COM
	renew until 12/14/16 10:50:32
[santosh015@ip-172-31-24-59 ~]$ beeline -u "jdbc:hive2://ip-172-31-24-58.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-24-58.ap-southeast-1.compute.internal@KSECURITY.COM"
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
2016-12-07 10:50:44,020 WARN  [main] mapreduce.TableMapReduceUtil: The hbase-prefix-tree module jar containing PrefixTreeCodec is not present.  Continuing without it.
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-24-58.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-24-58.ap-southeast-1.compute.internal@KSECURITY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.0)
Driver: Hive JDBC (version 1.1.0-cdh5.9.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.9.0 by Apache Hive
0: jdbc:hive2://ip-172-31-24-58.ap-southeast-> show tables;
INFO  : Compiling command(queryId=hive_20161207105050_2cb0cabe-57cc-4abb-a598-d6667cc97766): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161207105050_2cb0cabe-57cc-4abb-a598-d6667cc97766); Time taken: 0.128 seconds
INFO  : Executing command(queryId=hive_20161207105050_2cb0cabe-57cc-4abb-a598-d6667cc97766): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207105050_2cb0cabe-57cc-4abb-a598-d6667cc97766); Time taken: 0.201 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.49 seconds)
0: jdbc:hive2://ip-172-31-24-58.ap-southeast-> !quit
</code></pre>

## Now ferdinand
<pre><code>
[santosh015@ip-172-31-24-59 ~]$ kinit ferdinand
Password for ferdinand@KSECURITY.COM:
[santosh015@ip-172-31-24-59 ~]$ beeline -u "jdbc:hive2://ip-172-31-24-58.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-24-58.ap-southeast-1.compute.internal@KSECURITY.COM"
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
2016-12-07 10:51:36,716 WARN  [main] mapreduce.TableMapReduceUtil: The hbase-prefix-tree module jar containing PrefixTreeCodec is not present.  Continuing without it.
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-24-58.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-24-58.ap-southeast-1.compute.internal@KSECURITY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.0)
Driver: Hive JDBC (version 1.1.0-cdh5.9.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.9.0 by Apache Hive
0: jdbc:hive2://ip-172-31-24-58.ap-southeast-> show tables;
INFO  : Compiling command(queryId=hive_20161207105151_c7d746bf-d61d-43ac-8b2d-16c3849020d8): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161207105151_c7d746bf-d61d-43ac-8b2d-16c3849020d8); Time taken: 0.109 seconds
INFO  : Executing command(queryId=hive_20161207105151_c7d746bf-d61d-43ac-8b2d-16c3849020d8): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207105151_c7d746bf-d61d-43ac-8b2d-16c3849020d8); Time taken: 0.219 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.478 seconds)
0: jdbc:hive2://ip-172-31-24-58.ap-southeast->
</code></pre>
