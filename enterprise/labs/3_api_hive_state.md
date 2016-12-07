## Stop hive
<pre><code>
curl -u 'santosh015:********' -X POST "http://54.254.163.203:7180/api/v14/clusters/artcluster/services/hive/commands/stop"
</code></pre>

## Start hive
<pre><code>
curl -u 'santosh015:********' -X POST "http://54.254.163.203:7180/api/v14/clusters/artcluster/services/hive/commands/start"
</code></pre>

## Hive check
<pre><code>
curl -u 'santosh015:********' -X GET "http://54.254.163.203:7180/api/v14/clusters/artcluster/services/hive"
</code></pre>
