# Working in Notebook

Create another Lakehouse by creating New item from task “Silver data”.

Use the name “DynUG_Lakehouse_Silver”, verify that “Assigned to task” is “Silver data” if not change it:

<img width="520" height="347" alt="image" src="https://github.com/user-attachments/assets/386dbfe2-882c-41cb-8fcc-1a6f47248ff6" />

Navigate back to workspace and create new Notebook by creating New item from task “Initial process”.

Use the name “DynUG customer sentiment and load to Silver”, remember to verity that “Assigned to task” is “Initial process”. If being asked to about seeing new capabilities, select “Skip tour”.

In the Notebook attach Lakehouse “DynUG_Lakehouse_Bronze” and “DynUG_Lakehouse_Silver” by selecting Add data items > Existing data sources:

<img width="381" height="283" alt="image" src="https://github.com/user-attachments/assets/c4f041df-eea0-4da5-b8a2-2f7f926323a6" />

In the first code cell that says “# Welcome to your new notebook”, delete the prepopulated content and add import required libraries to use AI functions for PySpark. You can find the answer in documentation at https://learn.microsoft.com/en-us/fabric/data-science/ai-functions/overview (remember to look for PySpark and not pandas) 

You can also find the answer at DynUG-Fabric-Workshop/code/Lab 4 AI functions library.md at main · larsbi/DynUG-Fabric-Workshop

Run the code cell.

Create a new code cell, move mouse to blank space under first code cell:

<img width="753" height="266" alt="image" src="https://github.com/user-attachments/assets/1b25e31f-cd1f-4f24-a8ef-93647fb3a070" />

Or navigate to Edit ribbon and select “+ Add code cell below”:

<img width="940" height="152" alt="image" src="https://github.com/user-attachments/assets/77bcd3c1-fe15-418a-b896-857379d41c83" />

Start by loading data from “Customer reviews” table in DynUG_Lakehouse_Bronze into a dataframe. If you need help you can ask Copilot about “Load data from table CustomerReviews in DynUG_Lakehouse_Bronze into a dataframe” – you want everything from the table, so delete code that limits the output if Copilot suggests limiting output.

Because we have two Lakehouses attached to our Notebook, you should prefix the table name with the Lakehouse name, e.g. “DynUG_Lakehouse_Bronze.<table_name>”. There is always a default Lakehouse and it will be used if no prefixes are used.

You can also find the answer at DynUG-Fabric-Workshop/code/Lab 4 Load Customer reviews at main · larsbi/DynUG-Fabric-Workshop

If you want to see the output, use “display(<dataframe_name>) to see the result, e.g. replace <dataframe_name> with spark_df.

The name of the column with customer reviews is called “CustomerReview”. The syntax to use built-in AI function ai.analyze_sentiment is using this syntax:
```python
df.ai.analyze_sentiment(input_col="input", output_col="Sentiment")
```
In our example dataframe is called “spark_df” and not “df” as syntax above, input_col is “CustomerReview” and we can keep output_col as “Sentiment”, we want to load this to a new dataframe and can use this syntax to load to dataframe called dfscore:
```python
dfscore = spark_df.ai.analyze_sentiment(input_col="CustomerReview", output_col="Sentiment") 
*** remember to replace spark_df with the name of the first dataframe you created ***
```
Again, add “display(dfscore)” to view the output.

Next step is to write the output of sentiment analysis to a new table in Lakehouse DynUG_Lakehouse_Silver. If you ask Copilot it will give you an answer like 
```python
dfscore.write.format("delta").saveAsTable("<table_name>")
```
Where dfscore is the name of the dataframe we created when doing the sentiment analysis. Again, you must remember to prefix the table name with the Lakehouse name. Use the following syntax:
```python
dfscore.write.format("delta").saveAsTable("DynUG_Lakehouse_Silver.CustomerReviews")
```
Validate that DynUG_Lakehouse_Silver has table “customerreviews”:

<img width="478" height="277" alt="image" src="https://github.com/user-attachments/assets/2215f3a1-3170-47bf-a878-7ddfc5e24ec4" />

Next, we must make copies of the other four tables from DynUG_Lakehouse_Bronze to DynUG_Lakehouse_Silver.

In this lab, we don’t need to perform further transformations, but we must get the other four tables from "DynUG_Lakehouse_Bronze" to "DynUG_Lakehouse_Silver". The easy way to achieve this is to create shortcuts Lakehouse "DynUG_Lakehouse_Silver". 

Navigate to "DynUG_Lakehouse_Silver" and select "Get data" > "New shortcut" in Home ribbon. Select Microsoft OneLake followed by "DynUG_Lakehouse_Bronze", under Tables select:

• DimCustomer

• DimDate

• DimProduct

• FactSales

<img width="306" height="391" alt="image" src="https://github.com/user-attachments/assets/4973a3fa-f2bf-40d2-9555-06870d975882" />


<img width="306" height="391" alt="image" src="https://github.com/user-attachments/assets/58b1572e-369f-4f74-871d-5a8137ee9a6a" />

Validate that you now have 5 tables in DynUG_Lakehouse_Silver:

<img width="315" height="405" alt="image" src="https://github.com/user-attachments/assets/0015c409-6839-4924-ad3d-30c1aca56c80" />

