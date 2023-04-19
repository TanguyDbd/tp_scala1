# Practices - Data engineering

## TP - Data processing with Apache Spark
To process a large amount of data partitioned on a data lake, you can use data processing frameworks such as Apache Spark :
1. Read : https://spark.apache.org/docs/latest/sql-programming-guide.html

Some questions :
* What is Spark RDD API ?
Spark RDD API is a set of operations provided by Apache Spark for creating, transforming, and aggregating RDDs. RDDs are distributed collections of objects that are partitioned across a cluster of machines. The RDD API supports two types of operations: transformations that create a new RDD from an existing RDD, and actions that perform computation on an RDD and return a result.
* What is Spark Dataset API ?
Spark Dataset API is a higher-level API introduced in Apache Spark 2.0 that provides a type-safe, object-oriented programming interface for working with structured and semi-structured data. Datasets are similar to RDDs, but with the additional benefit of being able to use Spark SQL to run SQL-like queries on the data. The Dataset API provides compile-time type safety and allows developers to work with data using objects instead of using low-level RDD transformations. Additionally, Datasets can be serialized more efficiently than RDDs, leading to better performance.
* With which languages can you use Spark ? 
Spark provides APIs in several programming languages, including Java, Scala, Python, and R. Java and Scala are the primary languages for developing Spark applications, while Python and R are also popular choices among data scientists and analysts due to their ease of use and availability of data science libraries. Spark also provides a shell called PySpark, which enables users to run Spark code interactively using the Python language. Additionally, Spark supports SQL-like queries through its Spark SQL module, which can be used with any of the supported programming languages.
* Which data sources or data sinks can Spark work with ?
Spark can work with a variety of data sources and sinks, including Hadoop Distributed File System (HDFS), Apache Cassandra, Apache HBase, Apache Kafka, Amazon S3, and JDBC databases. Spark provides built-in support for these data sources and allows users to easily read and write data from and to these systems. Additionally, Spark supports various file formats, including CSV, JSON, Parquet, ORC, and Avro.

### Analyse data with Apache Spark and Scala 
One engineering team of your company created for you a TV News data stored as JSON inside the folder `data-news-json/`.

Your goal is to analyze it with your savoir-faire, enrich it with metadata, and store it as [a column-oriented format](https://parquet.apache.org/).

1. Look at `src/main/scala/com/github/polomarcus/main/Main.scala` and update the code 

**Important note:** As you work for a top-notch software company following world-class practices, and you care about your project quality, you'll write a test for every function you write.

You can see tests inside `src/test/scala/` and run them with `sbt test`

### How can you deploy your app to a cluster of machines ?
* https://spark.apache.org/docs/latest/cluster-overview.html

### Business Intelligence (BI)
How could use we Spark to display data on a BI tool such as [Metabase](https://www.metabase.com/) ?

Tips: https://github.com/polomarcus/television-news-analyser#spin-up-1-postgres-metabase-nginxand-load-data-to-pg

### Continuous build and test
**Pro Tips** : https://www.scala-sbt.org/1.x/docs/Running.html#Continuous+build+and+test

Make a command run when one or more source files change by prefixing the command with ~. For example, in sbt shell try:
```bash
sbt
> ~ testQuick
```