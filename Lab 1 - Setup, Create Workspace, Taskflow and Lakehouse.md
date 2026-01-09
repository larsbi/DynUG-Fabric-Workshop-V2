# Create Workspace
Use the name "DynUG workshop XX" where XX is the number of your user. Make sure workspace is assigned to “FabConUS5-P4 North Central US”:

<img width="733" height="897" alt="image" src="https://github.com/user-attachments/assets/d2b612ef-bb41-4460-9ac8-7a4431f505ef" />

# Setup Task flow

Setup task flow in workspace, select predesigned task flow "Medallion". 

**First delete:**

•	“Further transform”

•	“ML serving”

Create link between “Silver data” and “Gold data”. 

**Next, create new two new tasks:**

•	"Get data" task, name it "Reuse Power Query"

•	"Store data" task, name it "Semantic model"

Create a link between "Reuse Power Query" and "Bronze data".

Modify the link between "Gold data" and "Data visualize" to be a link between from "Gold data" to "Semantic model", and create new link from "Semantic model" to "Data visualize".

**Finally, rename**

• "High-volume data ingest" to "Load from Fabric SQL db" 

• "Low-volume data ingest" to "Load customer reviews"

The Task flow should look like this:

<img width="1524" height="297" alt="image" src="https://github.com/user-attachments/assets/5f30b698-5d91-4bdd-94db-7708fccde857" />

# Create Lakehouse

Create new Lakehouse by creating “New item” from task “Bronze data”:

<img width="495" height="248" alt="image" src="https://github.com/user-attachments/assets/1e7f5f6f-58f5-4b32-9172-33480fc0004d" />

Use the name "DynUG_Lakehouse_Bronze".

Leave Lakehouse open
