# pyspark exercise>

exercise with pyspark from starting. 

### narrow and wide Transforamtion 
https://www.databricks.com/glossary/what-are-transformations
## Narrow Trasformation
![image](https://github.com/nitish11497/pyspark_from_starting/assets/28913656/c802f3d1-a135-4395-a1b3-7a99d012f112)

 df.select >
 df.filter >
 df.withColumn >
 df.withColumnRenamed >
 df.drop >
## Wide Transformtion
![image](https://github.com/nitish11497/pyspark_from_starting/assets/28913656/9be1a5a1-d739-4617-8e3d-23e8639ccf03)

 df.distinct >
 df.union >
 df.join >
 df.sort or orderby >
# There are multiple ways to rename spark Data Frame Columns or Expressions.
	- We can rname column or expression using alias as part of select
	- We can add or rename column or expression using withColumn on top of DataFrame.
	- We can rename one column at a time using withColumnRenamed or top of DataFrame.
	- We typically use withColumn to perform row level transformations and then to provide a name to the result. If we provide the name as existing column, then the column will be replaced with new one.
	- If we want to just rename the column then it is better to use withColumnRenamed.
	- If we want to apply any transformation, we need to either use select or withColumn.
	- we can rename bunch of columns or change the order of the columns using toDF.
