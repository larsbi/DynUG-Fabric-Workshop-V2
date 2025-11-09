Use this PySpark code to load CustomerReiews table from DynUG_Lakehouse_Bronze Lakehoues:
spark_df = spark.read.table("DynUG_Lakehouse_Bronze.CustomerReviews")

To deiplay output, use:
display(spark_df)
