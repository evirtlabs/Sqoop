## Importing table from postgresql to hdfs using sqoop
sudo ./sqoop import --connect jdbc:postgresql://localhost/dvdrental --username postgres -P --table film_actor --target-dir /opt/sqoop/tables

### Note: Press Enter at password prompt as I have not set password for PostgreSQL.
Warning: /usr/local/hadoop/sqoop/../hbase does not exist! HBase imports will fail. <br>
Please set $HBASE_HOME to the root of your HBase installation. <br>
Warning: /usr/local/hadoop/sqoop/../hcatalog does not exist! HCatalog jobs will fail. <br>
Please set $HCAT_HOME to the root of your HCatalog installation.<br>
Warning: /usr/local/hadoop/sqoop/../accumulo does not exist! Accumulo imports will fail.<br>
Please set $ACCUMULO_HOME to the root of your Accumulo installation.<br>
Warning: /usr/local/hadoop/sqoop/../zookeeper does not exist! Accumulo imports will fail.<br>
Please set $ZOOKEEPER_HOME to the root of your Zookeeper installation.<br>
2020-09-07 16:48:33,609 INFO sqoop.Sqoop: Running Sqoop version: 1.4.7<br>
#### Enter password:<br>
2020-09-07 16:48:35,353 INFO manager.SqlManager: Using default fetchSize of 1000<br>
2020-09-07 16:48:35,355 INFO tool.CodeGenTool: Beginning code generation<br>
2020-09-07 16:48:35,610 INFO manager.SqlManager: Executing SQL statement: SELECT t.* FROM "film_actor" AS t LIMIT 1<br>
2020-09-07 16:48:35,701 INFO orm.CompilationManager: HADOOP_MAPRED_HOME is /usr/local/hadoop<br>
Note: /tmp/sqoop-root/compile/66d8122fcf2a82e9283ffe1198a6b1f9/film_actor.java uses or overrides a deprecated API.<br>
Note: Recompile with -Xlint:deprecation for details.<br>
2020-09-07 16:48:38,616 INFO orm.CompilationManager: Writing jar file: /tmp/sqoop-root/compile/66d8122fcf2a82e9283ffe1198a6b1f9/film_actor.jar<br>
2020-09-07 16:48:38,639 WARN manager.PostgresqlManager: It looks like you are importing from postgresql.<br>
2020-09-07 16:48:38,641 WARN manager.PostgresqlManager: This transfer can be faster! Use the --direct<br>
2020-09-07 16:48:38,642 WARN manager.PostgresqlManager: option to exercise a postgresql-specific fast path.<br>
2020-09-07 16:48:38,647 WARN manager.CatalogQueryManager: The table film_actor contains a multi-column primary key. Sqoop will default to the column actor_id only for this job.<br>
2020-09-07 16:48:38,650 WARN manager.CatalogQueryManager: The table film_actor contains a multi-column primary key. Sqoop will default to the column actor_id only for this job.<br>
2020-09-07 16:48:38,650 INFO mapreduce.ImportJobBase: Beginning import of film_actor<br>
2020-09-07 16:48:38,651 INFO Configuration.deprecation: mapred.job.tracker is deprecated. Instead, use mapreduce.jobtracker.address<br>
2020-09-07 16:48:38,916 INFO Configuration.deprecation: mapred.jar is deprecated. Instead, use mapreduce.job.jar<br>
2020-09-07 16:48:40,117 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps<br>
2020-09-07 16:48:40,346 INFO client.DefaultNoHARMFailoverProxyProvider: Connecting to ResourceManager at /0.0.0.0:8032<br>
2020-09-07 16:48:41,618 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /tmp/hadoop-yarn/staging/root/.staging/job_1599506854254_0004<br>
2020-09-07 16:48:43,063 INFO db.DBInputFormat: Using read commited transaction isolation<br>
2020-09-07 16:48:43,066 INFO db.DataDrivenDBInputFormat: BoundingValsQuery: SELECT MIN("actor_id"), MAX("actor_id") FROM "film_actor"<br>
2020-09-07 16:48:43,069 INFO db.IntegerSplitter: Split size: 49; Num splits: 4 from: 1 to: 200<br>
2020-09-07 16:48:43,125 INFO mapreduce.JobSubmitter: number of splits:4<br>
2020-09-07 16:48:43,529 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1599506854254_0004<br>
2020-09-07 16:48:43,529 INFO mapreduce.JobSubmitter: Executing with tokens: []<br>
2020-09-07 16:48:44,004 INFO conf.Configuration: resource-types.xml not found<br>
2020-09-07 16:48:44,005 INFO resource.ResourceUtils: Unable to find 'resource-types.xml'.<br>
2020-09-07 16:48:44,136 INFO impl.YarnClientImpl: Submitted application application_1599506854254_0004<br>
2020-09-07 16:48:44,215 INFO mapreduce.Job: The url to track the job: http://hadoop:8088/proxy/application_1599506854254_0004/<br>
2020-09-07 16:48:44,215 INFO mapreduce.Job: Running job: job_1599506854254_0004<br>
2020-09-07 16:48:56,531 INFO mapreduce.Job: Job job_1599506854254_0004 running in uber mode : false<br>
2020-09-07 16:48:56,532 INFO mapreduce.Job:  map 0% reduce 0%<br>
2020-09-07 16:49:13,747 INFO mapreduce.Job:  map 25% reduce 0%<br>
2020-09-07 16:49:15,771 INFO mapreduce.Job:  map 50% reduce 0%<br>
2020-09-07 16:49:16,780 INFO mapreduce.Job:  map 100% reduce 0%<br>
2020-09-07 16:49:16,796 INFO mapreduce.Job: Job job_1599506854254_0004 completed successfully<br>
2020-09-07 16:49:16,960 INFO mapreduce.Job: Counters: 34<br>
        File System Counters<br>
                FILE: Number of bytes read=0<br>
                FILE: Number of bytes written=1091032<br>
                FILE: Number of read operations=0<br>
                FILE: Number of large read operations=0<br>
                FILE: Number of write operations=0<br>
                HDFS: Number of bytes read=453<br>
                HDFS: Number of bytes written=160388<br>
                HDFS: Number of read operations=24<br>
                HDFS: Number of large read operations=0<br>
                HDFS: Number of write operations=8<br>
                HDFS: Number of bytes read erasure-coded=0<br>
        Job Counters<br>
                Killed map tasks=1<br>
                Launched map tasks=4<br>
                Other local map tasks=4<br>
                Total time spent by all maps in occupied slots (ms)=62201<br>
                Total time spent by all reduces in occupied slots (ms)=0<br>
                Total time spent by all map tasks (ms)=62201<br>
                Total vcore-milliseconds taken by all map tasks=62201<br>
                Total megabyte-milliseconds taken by all map tasks=63693824<br>
        Map-Reduce Framework<br>
                Map input records=5462<br>
                Map output records=5462<br>
                Input split bytes=453<br>
                Spilled Records=0<br>
                Failed Shuffles=0<br>
                Merged Map outputs=0<br>
                GC time elapsed (ms)=211<br>
                CPU time spent (ms)=2790<br>
                Physical memory (bytes) snapshot=572489728<br>
                Virtual memory (bytes) snapshot=11944574976<br>
                Total committed heap usage (bytes)=373555200<br>
                Peak Map Physical memory (bytes)=145305600<br>
                Peak Map Virtual memory (bytes)=2986143744<br>
        File Input Format Counters<br>
                Bytes Read=0<br>
        File Output Format Counters<br>
                Bytes Written=160388<br>
2020-09-07 16:49:16,973 INFO mapreduce.ImportJobBase: Transferred 156.6289 KB in 36.8281 seconds (4.253 KB/sec)<br>
2020-09-07 16:49:16,980 INFO mapreduce.ImportJobBase: Retrieved 5462 records.<br>
[root@hadoop ~]#<br>
### Verify whether table data is moved to hdfs
![Alt text](/screen_shots/Screenshot_Lab1_9.png?raw=true "Simple Code on IPython Notebooks")
