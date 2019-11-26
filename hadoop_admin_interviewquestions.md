
1.How can you increase storage capacity in HDFS? What compression tools (or mechanism ) you have used in your projects so far?

ans: By using hdfs compression,Gzipcodec is used for hdfs compression

2.Have you used ORC or Parquet? What are they?

ans: We used orc file format,It is a file format to store data Used in hive

3.why do I need it? What is the full form of ORC?why do I need it?

ans: Optimizer row columner Imporves performance in hive while reading, writing or processing the data

4.How does ORC improve?

ans:
*ORC stands for Optimized Row Columnar which means it can store data in an optimized way than the other file formats. 
*ORC reduces the size of the original data up to 75%. As a result the speed of data processing also increases. 
*ORC shows better performance than Text, Sequence and RC file formats.
*An ORC file contains rows data in groups called as Stripes along with a file footer. 
*ORC format improves the performance when Hive is processing the data.

5.What do you do to improve Hive performance? Tell me 5-6 points on this.

ans: 
*Apache Tez Engine is an extensible framework for building high-performance batch processing and interactive data processing. 
*Vectorization improves the performance by fetching 1,024 rows in a single operation instead of fetching single row each time. 
*Optimized Row Columnar format provides highly efficient ways of storing the hive data by reducing the data storage format by 75% of the original.
*With partitioning, data is stored in separate individual folders on HDFS. Instead of querying the whole dataset, it will query partitioned dataset.
*The Hive table is divided into a number of partitions and is called Hive Partition. Hive Partition is further subdivided into clusters or buckets and is called bucketing or clustering.
*CBO(Cost-Based Query Optimization) in hive helps in generating effective execution plan by scanning query .

6. If I delete a hive table, does the data also get deleted?

ans:
* If we create an External table, after deleting the table only the meta data related to table is deleted but not the contents of the table.
* in managed table if you delete the table, data will be deleted.

7.Where the metadata stored?

ans: I am using MySQL so the metadata stores there

8. One of your users deleted a dataset in HDFS, how do you recover that dataset?

ans: 
* we can recover by using trash policy in hdfs
*if trash policy is enabled the file is in location /user/username/.trash
*if it is not enabled we can recover by configuring fs.trash.interval in core-site.xml and set the value in minutes how much we need by this way we can recover the deleted dataset

9. What services will be installed when you install HDFS?

ans: 
For hdfs 
Datanode 
Name node 
Secondary namenode

For yarn 

Resource manager
Node manager
Application master

### 10. what is the use of NameNode SAFE MODE ON / OFF? 

* if safemode is on we cannot do any changes to the file system
*it is maintenance state of namenode

##### To know the status of Safemode, use command:
`hadoop dfsadmin –safemode get`
##### To enter Safemode, use command:
`bin/hadoop dfsadmin –safemode enter`
##### To come out of Safemode, use command:
`hadoop dfsadmin -safemode leave`

### 11. what are the options you know in cluster upgrade ?

* the migration options - 1. Express Upgrade. 2. Rolling Ugrades

### 12. what are the key parameters you know in HDFS configuration?

* dfs.name.dir  gives you the location where NameNode stores the metadata
* dfs.data.dir  gives the location of DataNodes where it stores the data.
* fs.checkpoint.dir  is the directory on the file system. On which secondary NameNode stores the temporary images of edit logs.