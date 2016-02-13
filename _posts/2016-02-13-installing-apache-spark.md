---
layout: post
title: "Installing Apache Spark"
modified:
categories: blog
excerpt:
tags: [apache spark, installation]
image:
  feature:
date: 2016-02-13
---

<!-- ## Sample Heading -->
<!-- ### Sample Heading 2 -->

### Prerequisite

* You must have java installed on your system
* `JAVA_HOME` must be set in your system path
* To confirm the installation open terminal / command prompt and type `java -version` you should see the output as below

{% highlight ruby %}
$ java -version
java version "1.8.0_25"
Java(TM) SE Runtime Environment (build 1.8.0_25-b17)
Java HotSpot(TM) 64-Bit Server VM (build 25.25-b02, mixed mode)
{% endhighlight %}

If Java is not installed on your system download the latest version of JDK <a href="http://www.oracle.com/technetwork/java/javase/downloads/index.html" target="_blank">`http://www.oracle.com/technetwork/java/javase/downloads/index.html`</a> and install, add path to your `<path>/jdk/bin` to .bashrc

* You must have Python installed on the system check the installation using `python --version` you should see the version of python installed on your system

{% highlight ruby %}
$ python --version
Python 2.7.10
{% endhighlight %}

If Python is not installed on your system download the latest version <a href="https://www.python.org/downloads/" target="_blank">https://www.python.org/downloads/</a> and install, check the version after installation

* To run scala jobs in spark we would need scala installed on the system as well
* To install scala download the latest release build and extract the archieve
* Add the path to scala bin to your system path `<path>\scala\bin`
* Also set the `SCALA_HOME=<path>\scala` on your system
* To verify the installation open terminal and run command `scala -version` you should see the output as below

{% highlight ruby %}
$ scala -version
Scala code runner version 2.11.6 -- Copyright 2002-2013, LAMP/EPFL
{% endhighlight %}

### Installation

* To install the Spark download the latest binary from `http://spark.apache.org/downloads.html`
* Unzip the file and save it at desired location
* Add path to spark bin `<path>/spark-1.3.0-bin-hadoop2.4/bin` to your system path

After this you should be ready to use Apache Spark standalone cluster on your local

### Checking Installation

To verify the installation run the command `./ spark-shell` this should start Apache Spark shell in standalone single node cluster. You should see the output as below.

{% highlight ruby %}
 $ ./ spark-shell
Spark assembly has been built with Hive, including Datanucleus jars on classpath
16/02/13 01:04:11 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /___/ .__/\_,_/_/ /_/\_\   version 1.3.0
      /_/

Using Scala version 2.10.4 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_25)
Type in expressions to have them evaluated.
Type :help for more information.
Spark context available as sc.
SQL context available as sqlContext.

scala>
{% endhighlight %}

Once the installation is done you are ready to write your first spark job

Apache Spark logs print lot of information by default which is very low level and not of much use. We can reduce it by changing the configuration properties for spark.

To do the configurations
* Go to conf folder in Apache Spark installation `<path>\spark\conf`
* Rename the file `log4j.properties.template` to `log4j.properties`
* Change the property value for `log4j.rootCategory` from `INFO` to `WARN` as shown below

{% highlight ruby %}
# Set everything to be logged to the console
log4j.rootCategory=WARN, console
log4j.appender.console=org.apache.log4j.ConsoleAppender
log4j.appender.console.target=System.err
log4j.appender.console.layout=org.apache.log4j.PatternLayout
log4j.appender.console.layout.ConversionPattern=%d{yy/MM/dd HH:mm:ss} %p %c{1}: %m%n

# Settings to quiet third-party logs that are too verbose
log4j.logger.org.spark-project.jetty=WARN
log4j.logger.org.spark-project.jetty.util.component.AbstractLifeCycle=ERROR
log4j.logger.org.apache.spark.repl.SparkIMain$exprTyper=INFO
log4j.logger.org.apache.spark.repl.SparkILoop$SparkILoopInterpreter=INFO
{% endhighlight %}

* Restart the spark-shell after the changes and you should be ready to write your first spark job yay :)

References: <a href="http://spark.apache.org" target="_blank">Apache Spark</a>