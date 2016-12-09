### User directories created
<pre><code>
hdfs@ip-172-31-9-248 ~]$ hdfs dfs -ls /user
Found 4 items
drwxrwxrwx   - mapred hadoop          0 2016-12-09 02:07 /user/history
drwxrwxr-t   - hive   hive            0 2016-12-09 02:08 /user/hive
drwxrwxr-x   - hue    hue             0 2016-12-09 02:09 /user/hue
drwxrwxr-x   - oozie  oozie           0 2016-12-09 02:09 /user/oozie
[hdfs@ip-172-31-9-248 ~]$ hdfs dfs -mkdir /user/raffles
[hdfs@ip-172-31-9-248 ~]$ hdfs dfs -mkdir /user/orchard
[hdfs@ip-172-31-9-248 ~]$ hdfs dfs -ls /user
Found 6 items
drwxrwxrwx   - mapred hadoop              0 2016-12-09 02:07 /user/history
drwxrwxr-t   - hive   hive                0 2016-12-09 02:08 /user/hive
drwxrwxr-x   - hue    hue                 0 2016-12-09 02:09 /user/hue
drwxrwxr-x   - oozie  oozie               0 2016-12-09 02:09 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2016-12-09 02:14 /user/orchard
drwxr-xr-x   - hdfs   supergroup          0 2016-12-09 02:14 /user/raffles
[hdfs@ip-172-31-9-248 ~]
</code></pre>

### Getting hosts from API
<pre><code>
curl -u 'admin:admin' http://172.31.9.250:7180/api/v12/hosts
{
  "items" : [ {
    "hostId" : "a39620eb-2407-49a5-8f4c-0a9a750c4098",
    "ipAddress" : "172.31.9.246",
    "hostname" : "ip-172-31-9-246.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-250.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/a39620eb-2407-49a5-8f4c-0a9a750c4098",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "81b0b676-44eb-486e-986d-ac5fb5ad263d",
    "ipAddress" : "172.31.9.247",
    "hostname" : "ip-172-31-9-247.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-250.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/81b0b676-44eb-486e-986d-ac5fb5ad263d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "4e879327-9eb2-45ea-86a9-d5ce1ebade63",
    "ipAddress" : "172.31.9.248",
    "hostname" : "ip-172-31-9-248.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-250.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/4e879327-9eb2-45ea-86a9-d5ce1ebade63",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "c4e32f47-ed0d-4a9f-afe6-c67232ea7a39",
    "ipAddress" : "172.31.9.249",
    "hostname" : "ip-172-31-9-249.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-250.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/c4e32f47-ed0d-4a9f-afe6-c67232ea7a39",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "c2faa86c-e4a8-43e9-864d-5ce1883ffa32",
    "ipAddress" : "172.31.9.250",
    "hostname" : "ip-172-31-9-250.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-250.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/c2faa86c-e4a8-43e9-864d-5ce1883ffa32",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  } ]
}
</code></pre>
