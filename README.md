# spark-setup
Spark-Installation SpeedRun:

1. Install Python3 (Default)

2. Install Java21 (Eg. C:\Java)
https://download.oracle.com/java/21/latest/jdk-21_windows-x64_bin.exe

3. Extract Hadoop-3.0.0 (Eg. C:\Hadoop)
https://github.com/steveloughran/winutils

5. Extract Spark (Eg. C:\spark)
https://dlcdn.apache.org/spark/spark-3.5.3/spark-3.5.3-bin-hadoop3.tgz

6. Set Environment Variables as:
	JAVA_HOME - C:\Java
	HADOOP_HOME - C:\Hadoop
	SPARK_HOME - C:\Spark
	PYSPARK_HOME - C:\Users\<>\AppData\Local\Programs\Python\Python\python.exe

7. Set Path Varibles as:
	%JAVA_HOME%\bin
	%SPARK_HOME%\bin
	%HADOOP_HOME%\bin

8. Run PythonShell:

from pyspark.sql import SparkSession
spark = SparkSession.builder.master("local").appName("PySpark Installation Test").getOrCreate()
df = spark.createDataFrame([(1, "Hello"), (2, "World")], ["id", "message"])
df.show()
