# Meet the Pre-Requisites
# --------------------------
## Connect to Postgresql database
![Alt text](/screen_shots/Screenshot_Lab1_1.png?raw=true "Simple Code on IPython Notebooks")

## Verify whether sample database exists and if not create one
![Alt text](/screen_shots/Screenshot_Lab1_2.png?raw=true "Simple Code on IPython Notebooks")

## Load the data in sample database
![Alt text](/screen_shots/Screenshot_Lab1_3.png?raw=true "Simple Code on IPython Notebooks")

## verify metadata definition of table
![Alt text](/screen_shots/Screenshot_Lab1_4.png?raw=true "Simple Code on IPython Notebooks")

# ************************************Lets now begin with Sqoop operations ********************************* <br>

[root@hadoop ~]# sqoop import --connect jdbc:postgresql://localhost/dvdrental --username postgres -P --split-by actor_id --columns actor_id,first_name,last_name,last_update --table actor --target-dir /opt/sqoop/hivetable --hive-import --create-hive-table --hive-table actor -m 1 <br>

##  For non-root sudoer execution <br>
### Goto $SQOOP_HOME/bin <br> 
[hdeveloper@hadoop bin]$ sudo  ./sqoop import --connect jdbc:postgresql://localhost/dvdrental --username postgres -P --split-by actor_id --columns actor_id,first_name,last_name,last_update --table actor --target-dir /opt/sqoop/hivetable --hive-import --create-hive-table --hive-table actor -m 1 <br>

## Note: For password prompt press enter, as I have not configured password for postgres
Warning: /usr/local/hadoop/sqoop/../hbase does not exist! HBase imports will fail.<br> 
Please set $HBASE_HOME to the root of your HBase installation.<br> 
Warning: /usr/local/hadoop/sqoop/../hcatalog does not exist! HCatalog jobs will fail.<br> 
Please set $HCAT_HOME to the root of your HCatalog installation.<br> 
Warning: /usr/local/hadoop/sqoop/../accumulo does not exist! Accumulo imports will fail.<br> 
Please set $ACCUMULO_HOME to the root of your Accumulo installation.<br> 
Warning: /usr/local/hadoop/sqoop/../zookeeper does not exist! Accumulo imports will fail.<br> 
Please set $ZOOKEEPER_HOME to the root of your Zookeeper installation.<br> 
2020-09-07 17:49:41,487 INFO sqoop.Sqoop: Running Sqoop version: 1.4.7<br> 
#### Enter password:<br> 
2020-09-07 17:49:43,627 INFO tool.BaseSqoopTool: Using Hive-specific delimiters for output. You can override<br>
2020-09-07 17:49:43,627 INFO tool.BaseSqoopTool: delimiters with --fields-terminated-by, etc.<br>
2020-09-07 17:49:43,828 INFO manager.SqlManager: Using default fetchSize of 1000<br>
2020-09-07 17:49:43,832 INFO tool.CodeGenTool: Beginning code generation<br>
2020-09-07 17:49:44,091 INFO manager.SqlManager: Executing SQL statement: SELECT t.* FROM "actor" AS t LIMIT 1<br>
2020-09-07 17:49:44,166 INFO orm.CompilationManager: HADOOP_MAPRED_HOME is /usr/local/hadoop<br>
Note: /tmp/sqoop-root/compile/d0bad826dd5623b22b7d913b9e96103b/actor.java uses or overrides a deprecated API.<br>
Note: Recompile with -Xlint:deprecation for details.<br>
2020-09-07 17:49:47,104 INFO orm.CompilationManager: Writing jar file: /tmp/sqoop-root/compile/d0bad826dd5623b22b7d913b9e96103b/actor.jar<br>
2020-09-07 17:49:47,133 WARN manager.PostgresqlManager: It looks like you are importing from postgresql.<br>
2020-09-07 17:49:47,136 WARN manager.PostgresqlManager: This transfer can be faster! Use the --direct<br>
2020-09-07 17:49:47,136 WARN manager.PostgresqlManager: option to exercise a postgresql-specific fast path.<br>
2020-09-07 17:49:47,137 INFO mapreduce.ImportJobBase: Beginning import of actor<br>
2020-09-07 17:49:47,140 INFO Configuration.deprecation: mapred.job.tracker is deprecated. Instead, use mapreduce.jobtracker.address<br>
2020-09-07 17:49:47,450 INFO Configuration.deprecation: mapred.jar is deprecated. Instead, use mapreduce.job.jar<br>
2020-09-07 17:49:48,799 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps<br>
2020-09-07 17:49:49,051 INFO client.DefaultNoHARMFailoverProxyProvider: Connecting to ResourceManager at /0.0.0.0:8032<br>
2020-09-07 17:49:50,938 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /tmp/hadoop-yarn/staging/root/.staging/job_1599506854254_0008<br>
2020-09-07 17:49:52,715 INFO db.DBInputFormat: Using read commited transaction isolation<br>
2020-09-07 17:49:52,776 INFO mapreduce.JobSubmitter: number of splits:1<br>
2020-09-07 17:49:53,274 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1599506854254_0008<br>
2020-09-07 17:49:53,274 INFO mapreduce.JobSubmitter: Executing with tokens: []<br>
2020-09-07 17:49:53,797 INFO conf.Configuration: resource-types.xml not found<br>
2020-09-07 17:49:53,799 INFO resource.ResourceUtils: Unable to find 'resource-types.xml'.<br>
2020-09-07 17:49:53,937 INFO impl.YarnClientImpl: Submitted application application_1599506854254_0008<br>
2020-09-07 17:49:53,996 INFO mapreduce.Job: The url to track the job: http://hadoop:8088/proxy/application_1599506854254_0008/<br>
2020-09-07 17:49:54,002 INFO mapreduce.Job: Running job: job_1599506854254_0008<br>
2020-09-07 17:50:06,297 INFO mapreduce.Job: Job job_1599506854254_0008 running in uber mode : false<br>
2020-09-07 17:50:06,298 INFO mapreduce.Job:  map 0% reduce 0%<br>
2020-09-07 17:50:14,398 INFO mapreduce.Job:  map 100% reduce 0%<br>
2020-09-07 17:50:14,413 INFO mapreduce.Job: Job job_1599506854254_0008 completed successfully<br>
2020-09-07 17:50:14,532 INFO mapreduce.Job: Counters: 33<br>
        File System Counters<br>
                FILE: Number of bytes read=0<br>
                FILE: Number of bytes written=272908<br>
                FILE: Number of read operations=0<br>
                FILE: Number of large read operations=0<br>
                FILE: Number of write operations=0<br>
                HDFS: Number of bytes read=87<br>
                HDFS: Number of bytes written=7999<br>
                HDFS: Number of read operations=6<br>
                HDFS: Number of large read operations=0<br>
                HDFS: Number of write operations=2<br>
                HDFS: Number of bytes read erasure-coded=0<br>
        Job Counters<br>
                Launched map tasks=1<br>
                Other local map tasks=1<br>
                Total time spent by all maps in occupied slots (ms)=5380<br>
                Total time spent by all reduces in occupied slots (ms)=0<br>
                Total time spent by all map tasks (ms)=5380<br>
                Total vcore-milliseconds taken by all map tasks=5380<br>
                Total megabyte-milliseconds taken by all map tasks=5509120<br>
        Map-Reduce Framework<br>
                Map input records=200<br>
                Map output records=200<br>
                Input split bytes=87<br>
                Spilled Records=0<br>
                Failed Shuffles=0<br>
                Merged Map outputs=0<br>
                GC time elapsed (ms)=43<br>
                CPU time spent (ms)=530<br>
                Physical memory (bytes) snapshot=145199104<br>
                Virtual memory (bytes) snapshot=2986172416<br>
                Total committed heap usage (bytes)=93388800<br>
                Peak Map Physical memory (bytes)=145199104<br>
                Peak Map Virtual memory (bytes)=2986172416<br>
        File Input Format Counters<br>
                Bytes Read=0<br>
        File Output Format Counters<br>
                Bytes Written=7999<br>
2020-09-07 17:50:14,551 INFO mapreduce.ImportJobBase: Transferred 7.8115 KB in 25.7298 seconds (310.8844 bytes/sec)<br>
2020-09-07 17:50:14,559 INFO mapreduce.ImportJobBase: Retrieved 200 records.<br>
2020-09-07 17:50:14,605 INFO manager.SqlManager: Executing SQL statement: SELECT t.* FROM "actor" AS t LIMIT 1<br>
2020-09-07 17:50:14,611 WARN hive.TableDefWriter: Column last_update had to be cast to a less precise type in Hive<br>
#### 2020-09-07 17:50:14,632 INFO hive.HiveImport: Loading uploaded data into Hive<br>
2020-09-07 17:50:14,638 INFO conf.HiveConf: Found configuration file file:/usr/local/hadoop/hive/conf/hive-site.xml<br>
2020-09-07 17:50:16,062 INFO hive.HiveImport: which: no hbase in (/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/usr/java/jdk1.8.0_261-amd64/jre/bin:/usr/java/jdk1.8.0_261-amd64//bin:/usr/local/hadoop/sbin:/usr/local/hadoop/bin:/usr/local/hadoop/hive/bin:/usr/local/hadoop/hive/bin:/usr/local/hadoop/pig/bin:/root/bin:/usr/java/jdk1.8.0_261-amd64/jre/bin:/usr/java/jdk1.8.0_261-amd64//bin:/usr/local/hadoop/sbin:/usr/local/hadoop/bin:/usr/local/hadoop/hive/bin:/usr/local/hadoop/hive/bin:/usr/local/hadoop/pig/bin:/usr/local/hadoop/sqoop/bin:/usr/local/hadoop/sbin:/usr/local/hadoop/bin)<br>
2020-09-07 17:50:16,956 INFO hive.HiveImport: SLF4J: Class path contains multiple SLF4J bindings.<br>
2020-09-07 17:50:16,960 INFO hive.HiveImport: SLF4J: Found binding in [jar:file:/usr/local/hadoop/hive/lib/log4j-slf4j-impl-2.10.0.jar!/org/slf4j/impl/StaticLoggerBinder.class]<br>
2020-09-07 17:50:16,960 INFO hive.HiveImport: SLF4J: Found binding in [jar:file:/usr/local/hadoop/share/hadoop/common/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]<br>
2020-09-07 17:50:16,960 INFO hive.HiveImport: SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.<br>
2020-09-07 17:50:16,972 INFO hive.HiveImport: SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]<br>
2020-09-07 17:50:22,255 INFO hive.HiveImport: Hive Session ID = c502afe5-d19b-4612-9cc2-2e9c35c3bc06<br>
2020-09-07 17:50:22,404 INFO hive.HiveImport:<br>
2020-09-07 17:50:22,406 INFO hive.HiveImport: Logging initialized using configuration in jar:file:/usr/local/hadoop/hive/lib/hive-common-3.1.2.jar!/hive-log4j2.properties Async: true<br>
2020-09-07 17:50:34,825 INFO hive.HiveImport: Hive Session ID = 8d4ec639-4a9c-4fb4-a56f-9123aab110d8<br>
2020-09-07 17:50:38,250 INFO hive.HiveImport: OK<br>
2020-09-07 17:50:38,251 INFO hive.HiveImport: Time taken: 3.272 seconds<br>
2020-09-07 17:50:38,898 INFO hive.HiveImport: Loading data to table default.actor<br>
2020-09-07 17:50:39,335 INFO hive.HiveImport: OK<br>
2020-09-07 17:50:39,335 INFO hive.HiveImport: Time taken: 1.079 seconds<br>
2020-09-07 17:50:39,810 INFO hive.HiveImport: Hive import complete.<br>
2020-09-07 17:50:39,834 INFO hive.HiveImport: Export directory is contains the _SUCCESS file only, removing the directory.<br>
