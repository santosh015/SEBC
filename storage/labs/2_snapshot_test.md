```
[root@ip-172-31-10-136 SEBC]# su - hdfs
[hdfs@ip-172-31-10-136 ~]$ hadoop fs -put SEBC/ /precious
put: `SEBC/': No such file or directory
[hdfs@ip-172-31-10-136 ~]$ hadoop fs -put /home/SEBC/ /precious
[hdfs@ip-172-31-10-136 ~]$ hadoop fs -ls /precious
Found 1 items
drwxr-xr-x   - hdfs supergroup          0 2016-12-06 03:02 /precious/SEBC
```
