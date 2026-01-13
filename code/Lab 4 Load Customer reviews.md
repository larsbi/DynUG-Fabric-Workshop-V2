Use this PySpark code to load CustomerReiews table from DynUG_Lakehouse_Bronze Lakehoues:

```python
spark_df = spark.read.table("DynUG_Lakehouse_Bronze.dbo.CustomerReviews")
```
To deiplay output, use:
```python
display(spark_df)
```
