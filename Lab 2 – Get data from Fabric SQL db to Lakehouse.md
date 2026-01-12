# Create Shortcuts to tables in Fabric SQL database

In Lakehouse select “New shortcut”:

<img width="940" height="268" alt="image" src="https://github.com/user-attachments/assets/91590001-0b9d-48c0-8e4a-a8c1db09a0f3" />

Select Microsoft OneLake as the source.

Find the item “DynUG database” which is a Fabric SQL database.

Expand Tables section and SalesLT schema, select:

•	DimCustomer

•	DimDate

Validate that the two tables are part of Lakehouse:

<img width="503" height="458" alt="image" src="https://github.com/user-attachments/assets/f415e559-3a40-4e41-941d-f66f361e92cd" />


# Load data from views in Fabric SQL database

In Lakehouse select “New pipeline”:

<img width="420" height="420" alt="image" src="https://github.com/user-attachments/assets/f3165907-463d-40e2-8aac-d28a6b8aa7d8" />


Name the pipeline “DynUG pipeline”

Use “DynUG database” as source. If not available on landing page, select OneLake catalog and find the item there.

In “Connect to data source” section, make sure “Tables” are selected. Then select:

•	SalesLT.DimProduct

•	SalesLT.FactSales

Click Next

In “Connect to data destination” section. Make sure:

•	SalesLT.DimProduct and SalesLT.FactSales is loading to Tables 

•	"Load to new table" is selected

•	Replace schema name “SalesLT” with "dbo" in for table name:

<img width="1151" height="442" alt="image" src="https://github.com/user-attachments/assets/7a2fe34d-3043-4f16-a9bf-321d0ce42ff7" />

Then click Next

Validate that the destination is the Lakehouse you created, also check that “Start data transfer immediately” is selected:

<img width="1395" height="768" alt="image" src="https://github.com/user-attachments/assets/41f815cf-4e40-4cc2-a375-d2c9c2b2ad70" />


Click Save + Run

In Pipeline run pane, select OK (the parameter “cw_items_gbb” will be called something else in your Pipeline):

<img width="940" height="536" alt="image" src="https://github.com/user-attachments/assets/374070a0-1dc6-4667-a2f1-fc67750dc780" />

Now the pipeline will start load data from Fabric SQL database to the Lakehouse you created (“ForEach_gbb” & “Copy_gbb” will be called something else in your Pipeline):

<img width="940" height="334" alt="image" src="https://github.com/user-attachments/assets/92296952-f80d-449a-95f5-ba4424320879" />

Navigate back to Lakehouse and validate that two new tables are created. If you don’t see the new tables immediately, refresh the Lakehouse;

<img width="234" height="167" alt="image" src="https://github.com/user-attachments/assets/0b8a9a04-433d-4c7f-b96b-d0ffe0f0dfc6" />

You may see table called Unidentified, if that happens, refresh again. It can take a few minutes to show up:

<img width="508" height="589" alt="image" src="https://github.com/user-attachments/assets/cf22062a-18bc-4eab-9a39-fad0e1307dc4" />

Go to workspace and add “DynUG pipeline” to “Load from Fabric SQL db” task. 

Select “Load from Fabric SQL db” and Attach item:'

<img width="408" height="220" alt="image" src="https://github.com/user-attachments/assets/8e79f288-04d5-479c-956a-c2366a324e6a" />
