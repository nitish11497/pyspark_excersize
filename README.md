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
 
# Read CSV with array datatype 
	- You can not write DataFrames with array columns to csv file.
 	- It's not a limitiation of spark It's a limitation of the csv file.
  	- csv files can't handle complex column types like arrays.
   	- Parquet files are able to handle complex columns.
# How Iterate over rows and columns in pyspark DataFrame.
	# using collect
 		- Syntax = 
   			for iterator in dataframe.collect:
      				print(iterator['column'])
	# Using toLocalIterator()
 		- Syntax-
   			for itr in dataframe.rdd.toLocalIterator():
                    		print(itr["column_name"])
	# Using Using iterrows()
 		- Syntax
   			for index,row in dataframe.toPandas().iterrows():
      				print(row[0],row[1],row[2])
	# Using select
 		- Syntax
   			for rows in dataframe.select("ID", "Name").collect():
       
    				print(rows[0], rows[1])
	# Using List Comprehension
 			for i in [j["NAME"] for j in dataframe.rdd.collect()]:
    				print(i)
	# Using MAP
 		rdd=dataframe.rdd.map(lambda loop: (
      		loop["column1"],...,loop["columnn"]) )
 		rdd.toDF(["column1",.......,"columnn"]).collect()
