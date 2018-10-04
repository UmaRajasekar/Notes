# Notes

NoSQL is the alternate database system like SQL which can perform analysis on large amount of data very quickly.\
Tools available in NoSQL
a. HBase

NoSql is also called as Random Access to Planet Size Data
Scaling up MySQL etc. to massive loads requires extreme measures
a. Denormalization
b. Caching Layer (Memcached)
c. Master/Slave Setup
d. Sharding
e. Materialized Viws
f. Removing stored procedures

For scenarios like retriving certain information, a simple get/put API may meet your needs.
Looking up values for given key is simple, fast and scalable.

Sample Architecture
-> Client and Request Router
  -> Shard1
  -> Shard2
  -> Shard3
  -> Shardn
  
Use case of NoSQL database
-> When you are working at gaint scale - export your data to non-relational database for fast and scalable serving of data to web applications etc..

HBASE
-> This is non relational, scalable database built on HDFS.
-> This is basically built on the Google's BigTable
-> There is no query language. Only CRUD API
  -> Create
  -> Read
  -> Update
  -> Delete
There is  no query language, only CRUD API
-> HBASE Architecture
  ->ZooKeeper      HMaster
  ->Region Server1, Region Server2, Region Servern [Auto Sharding]
  ->HDFS
 HBase automatically distributes data based on the 
 HBase takes individual rows available in each region and copy them into single file which is well managed by HDFS
 Web server talking to HBase talks directly to region nodes instead of HBASE master node.
 HBASE master keeps track on the data on how data is partitioned.
 
 HBASE data model
 -> Fast acccess to any given row
 -> A row is reference by unique key
 -> Each row has small number of column families
 -> A column family consist of arbitary columns
 -> You can have very large number of columns in a column family
 -> Each cell can have many versions with given timestamps.
 -> Sparse data is A-Ok - missing columns in a row consume no storage.
 
 Some ways to access HBASE
 -> HBASE shell
 -> JAVA API. Wrappers available for Python, Scala, etc.
 -> Spark, Pig, Hive
 -> Rest Service
 -> Thrift Service
 -> Avro Service
 
