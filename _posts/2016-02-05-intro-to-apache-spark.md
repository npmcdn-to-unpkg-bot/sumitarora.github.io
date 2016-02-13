---
layout: post
title: "Introduction to Apache Spark"
modified:
categories: blog
excerpt:
tags: [apache spark, introduction]
image:
  feature:
date: 2016-02-05
---

<!-- ## Sample Heading -->


<!-- ### Sample Heading 2 -->


#### What is Apache Spark?

Apache Spark is a cluster computing platform designed to be fast and general purpose engine for large-scale data processing.

#### Why Spark?

* Spark supports wide range of diverse workflows including Map Reduce, Machine Learning, Graph processing etc.
* Apache Spark makes use of RDD (Resilient Distributed Dataset) the basic abstraction in Spark.
* RDDs are immutable, partitioned collection of elements that can be operated on in parallel
* Consists of Rich Standard Library
* Spark consists of API in many programming languages supported - Scala, Java, Python, R consists of Unified development and deployment environment for all
* Regardless of which programming language you are good at, be it Scala, Java, Python or R, you can use the same single clustered runtime environment for prototyping


#### Features

* **Generality**: Combine SQL, streaming, and complex analytics. Spark powers a stack of libraries including SQL and DataFrames, MLlib for machine learning, GraphX, and Spark Streaming. You can combine these libraries seamlessly in the same application.

* **Easy to Use**: Write applications quickly in Java, Scala, Python, R. Spark offers over 80 high-level operators that make it easy to build parallel apps. And you can use it interactively from the Scala, Python and R shells.

![Easy to Use]({{ site.url }}/images/2.png)

* **Run Everywhere**: Spark runs on Hadoop, Mesos, standalone, or in the cloud. It can access diverse data sources including HDFS, Cassandra, HBase, and S3. You can run Spark using its standalone cluster mode, on EC2, on Hadoop YARN, or on Apache Mesos. Access data in HDFS, Cassandra, HBase, Hive, Tachyon, and any Hadoop data source.

![Run Everywhere]({{ site.url }}/images/3.png)

* **Speed**: Run programs up to 100x faster than Hadoop MapReduce in memory, or 10x faster on disk. Spark has an advanced DAG execution engine that supports cyclic data flow and in-memory computing.

![Speed]({{ site.url }}/images/1.png)


#### Spark stack


* **Spark Core**: At the core it consist of basic functionality, including components for task scheduling, memory management, fault recovery, interacting with storage systems, and more. Resilient distributed data‐ sets (RDDs) which provide main programming abstraction for spark is also part of Spark Core. RDDs are immutable, partitioned collection of elements that can be operated on in parallel.

* **Spark SQL**: Spark SQL is module for working with structured data in Spark. Using Spark SQL we mix SQL queries with Spark programs. Like Spark it can also be connected to any data source. Spark SQL includes a cost-based optimizer, columnar storage and code generation to make queries fast. At the same time, it scales to thousands of nodes and multi hour queries using the Spark engine, which provides full mid-query fault tolerance.

* **Spark Streaming**: Spark Streaming is the component which enables Real Time Processing of data streams. It's easy to build scalable fault-tolerant streaming applications using it. Spark Streaming can read data from various sources and also from custom data sources.

* **MLlib**: MLlib is Apache Spark's scalable machine learning library. It consists of multiple types of machine learning algorithms, includ‐ ing classification, regression, clustering, and collaborative filtering.

* **GraphX**: GraphX is Apache Spark's API for graphs and graph-parallel computation. It allow us to create a directed graph with properties attached to each vertex and edge, Various operators for manipulating graphs and a library of common graph algorithms.


References: <a href="http://spark.apache.org" target="_blank">Apache Spark</a>