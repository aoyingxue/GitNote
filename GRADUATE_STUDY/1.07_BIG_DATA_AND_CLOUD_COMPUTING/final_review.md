#### Big data and cloud 

1. What is Big Data?
   1. Any data that is beyond your computation power can be considered Big Data
2. Which one is a Semi-Structured Data? 
   1. XML file
   2. JSON
3. What are the main 3 Vs of Big Data?
   1. Volume, Variety, Velocity
4. What type of data can be useful for Netflix to collect?
   1. The location of the users
   2. Time users watch
   3. Content users watch
5. What language Hadoop was originally written by?
   1.  JAVA
6. Hadoop has two main components that have been established first. Select them from the following choices.
   1. MapReduce
   2. HDFS
7. What is Dark Data?
   1. Data that we might not been touched at all
8. The fact that data can be from Facebook, Tweeter, Google Search, or Youtube is more highlighting the Variety aspect of data.
   1. True
9. Which one of the following is reflecting the fact that data should be trustworthy? 
   1. Veracity
10. We talked about several business cases using Big Data. Which of the follows did we mention in the Healthcare industry? 
    1. IBM Watson
11. Which one is not a cloud service?
    1. All of them are examples of Cloud services: 
       1. Online Banking
       2. Gmail
       3. Amazon AWS EC2
12. Which one is not an example of public clouds?
    1. <u>WashU CHPC</u>
    2. ~~Amazon AWS~~
    3. ~~Office 360~~
    4. ~~Yahoo Email Service~~
13. Which one is the most basic type of cloud service?
    1. ~~PAAS~~
    2. IAAS
    3. ~~SAAS~~
14. Google Email (Gmail) service is an exam of:
    1. SAAS
15. Amazon AWS EC2 service is an example of
    1. IAAS
16. Public Cloud Services are safe against piracy and data breaches. 
    1. False
17. The software we introduced to connect to AWS on mac OS is MobaXterm.
    1. False
18. What was the command we used to download the content from the AWS EC2 machine to our local machine?
    1. scp
19. What is the command to change the attribute of the file in Linux shell?
    1. chmod
20. What is the OS that CDH5 Cloudera comes preinstalled on top of that? 
    1. CentOS

-------------------

#### bash

1. Which one is the most convenient method to take the second column of a large CSV file stored on the hard disk?
   1. Linux Shell
2. How a CSV file is separated? What is the denotation of the end of a line? Columns in a CSV file are separated with ___ and ___ specifies the end of a line.
   1. ‘,’ and ‘\n’
3. What is the default user name created on AWS EC2?
   1. ubuntu

-----------------

#### Hadoop

1. There is a tool in the Hadoop Ecosystem that is the workflow scheduler for map-reduce jobs. Find it from below
   1. Oozie
2. In which company the Hadoop project initialized?
   1. Yahoo
3. Which one of the following companies is a Hadoop vendor?
   1. Datameer
   2. provide hadoop: [https://cwiki.apache.org/confluence/display/HADOOP2/Distributions%20and%20Commercial%20Support](https://cwiki.apache.org/confluence/display/HADOOP2/Distributions and Commercial Support)
   3. big names use hadoop: https://cwiki.apache.org/confluence/display/HADOOP2/PoweredBy 
4. The command in Linux to add a file into HDFS is **hdfs dfs -put** 
5. To overcome the possible malfunctioning in the nodes, HDFS by default uses **replication** and makes **three** copies of each file.
6. Which node is the metadata keeper in the HDFS structure? 
   1. Name node
7. What is the default port address of Hue in Cloudera CDH5?
   1. 8888
8. Impala shares the same tablespace with Hive.
   1. True
9. Impala is more reliable than Hive.
   1. False
10. Which one is correct?
    1. Impala is faster than Hive.
    2. Impala doesn't use MapReduce.
    3. Impala is originally written in **C++**.
11. The command in Pig-Latin to show the results on the screen is:
    1. **dump**
12. Pig-Latin is essentially designed to make data-analysis reports. 
    1. False
    2. Hive make reports and pig for programming
13. Hive is originally developed in: Facebook; mainly used by Data Analysts
14. Pig is originally developed in: Yahoo; mainly used by programmers
15. Hadoop Table space is shared between Hive, Pig, and Impala
    1. False
    2. Pig is not shared. 
16. In Pig-Latin, UDF stands for <u>User Defined Function</u>
17.  The scripts in the following languages are translated into MapReduce jobs in order to process except: Impala
    1. Hive and pig are all translated into map reduce 
18. Once the data is imported into the Hive tables, it will be removed from the user folder. 
    1. True
19. HDFS does **not** provide a mechanism for **local caching** of data**.** Data should simply be **re-read** from the source.

-------------

1. What was the command we used to download the content from the AWS EC2 machine to our local machine?
   1. scp
2. If I like to change the permission of a file to be only readable by myself (user), what number should I assign to?
   1. 400
3. Among the main attributes of data, the one that speaks out about the trustworthiness is **Data veracity** 
4. What is the command in the Unix terminal to find the current directory?
   1. pwd
5. What is the shortcut to run the third command on history list?
   1. !3
6. What is the command to show the result of a Pig-Latin script on screen?
   1. dump

---------------

1. What is the dictionary identifier in Python?

   1. {}

2. There is a tool in Hadoop to analyze big data where you don't need to program MapReduce or Pig. Name it.

   1. BigSheets

3. Interaction with Zookeeper in Hadoop occurs via

   1. Java or C interfaces

4. There is a dictionary in python called my_dict. The key and value in my_dicts are "name" and "phone number" respectively. The "phone number" is a list that includes 3 items as cell number, home number, and work number. Suppose that we like to retrieve Joe's cell number. The command would be: 

   1. my_dict.get('Joe')[0]

5. What was the example in the MapReduce video by IBM?

   1. Temperature in different cities

6. The lecturer in the IBM Hadoop series mentioned a similar programming structure as Pig. The language was:

   1. JAVA 
   2. Pig latin and pig runtime≈JAVA and JVM

7. According to the lecture in IBM Hadoop series dump command in Pig is mainly used in

   1.  debugging stage

8. Based on the lecture by IBM staff, the failure of Hadoop clusters is similar to:

   1. Failure of a zipper in kids jacket

9. Which one is good at managing sparse data sets?

   1. Hbase

10. What is the Hive shell?

    1. The command line interface of Hive

11. HBase is a relational database system with strict standards.

    1. False

12. The tables of HBase are stored in

    1. HDFS

13. In HBase, you must predefine the table schema. 

    1. True

14. The workflow in <u>Oozie</u> is specified in

    1. <u>Xml based</u> 

15. The index of a value in a dictionary is ___

    1. key

16. ____ is the mechanism to move large volumes of data into Hadoop.

    1. Flume

17.  Bigsheets translate workload into **Pig scripts**

18. Bigsheets can process structured data such as CSV and unstructured data such as JSON.

    1. True

19. Avro stores the data schema (definition) in ____ format. 

    1. JSON

20. One of the Hadoop tools developed by IBM is

    1. Jaql

    

Pig: yahoo; DUMP: send the output to the screen when you are debugging; pig latin and runtime similar to between java virtual machine(JVM) and java application

Hive: Facebook; HQL; hive shell (command line interface)

Oozie: yahoo; XML based called hPDL(Hadoop process definition)

Bigsheets: non-program, browser based; by big insights; can read and process data in JSON, CSV and other delimited formats; translate workload into Pig scripts;

JAQL: BigInsights, Hadoop

Avro: data serialization, data exchange; data schema stored in JSON, data stored in binary format

Flume: a mechanism for moving large volumes of data into Hadoop 

HBase: predefine the schema; tables stored in HDFS; not a relational data store; good at managing sparse data sets 

-------------

#### pyspark

Spark is written in **Scala** 

Spark performs **better for iterative algorithms**.

RDD (**Resilient Distributed Datasets**): read-only

1. It has been said that Spark is much faster than MapReduce. Why is that
   1. Because Spark is **in-memory** computation framework.
2. Which language Spark has been written with?
   1. Scala
3. Spark performs better for iterative algorithms.
   1. True
4. While programming in Spark, we can modify RDDs.
   1. False
5. There is a machine learning library developed in Spark. Can you name it?
   1. MLlib
6. There are multiple approaches to see an example of RDD contents in PySpark. Find them from the follow
   1. take(n) and first()
7. A lambda function in Python can take any number of arguments, but can only have one expression.
   1. True
8. Spark has been developed before MapReduce.
   1. False

##### Standalone spark

```python
#unzip
bzip2 -d /Users/aoyingxue/Downloads/1987.csv.bz2

pyspark

## new version doesn't need this process
#sc.stop()
#conf = SparkConf().setMaster("local").setAppName("WordCount")
#sc = SparkContext(conf = conf)

flight_rdd=sc.textFile("1987.csv")

#first i identify the header
header=flight_rdd.first()

#filter the data to remove it
rows_rdd=flight_rdd.filter(lambda line:line!=header)

#get columnes; ascii will make your text correct without u`
data_rdd=rows_rdd.map(lambda x:x.split(',')).map(lambda x:(x[8].encode('ascii'),x[15].encode('ascii')))

#Data cleaning: nulls
f1_rdd=data_rdd.filter(lambda x:(x[1]!='NA'))

#string to integer
f2_rdd=f1_rdd.map(lambda x: [x[0], int(x[1])])

#dataframe
df=sqlContext.createDataFrame(f2_rdd,['airline','depdelay'])

#groupby in the dataframe
df2=df.groupBy(df.airline).agg({"depdelay":"avg"})

df2.show()
```

```bash
yt_rdd=sc.textFile("youtube.csv")

## header
yt_header=yt_rdd.first()
rows_rdd=yt_rdd.filter(lambda x:x!=yt_header)

## extract columns
data_rdd=rows_rdd.map(lambda x:x.split(",")).map(lambda x:(x[0].encode("ascii"),x[8].encode("ascii"),x[9].encode("ascii")))
f1_rdd=data_rdd.map(lambda x:[x[0],int(x[1]),int(x[2])])

## create dataframe
df1=sqlContext.createDataFrame(f1_rdd,["video_id","likes","dislikes"])

## group by and sum up
df2=df1.groupby(df1.video_id).agg({"likes":"sum","dislikes":"sum"})
df2.show()
## rename the columns
df2=df2.toDF("video_id","total_likes","total_dislikes") ##rename
df2.show()

## calculate pure likes of each video id
df3=df2.withColumn("total_pure_likes",df2.total_likes-df2.total_dislikes)
df3.show()

## sort the pure likes
df4=df3.sort(df3.total_pure_likes.desc())
df4.show(6)
```

#### Word count by pyspark

```python
lines_rdd.flatMap(lambda x: x.split()).map(lambda x: (x,1)).reduceByKey(lambda x,y:x+y).map(lambda x: (x[1],x[0])).sortByKey(False).take(5)
```

