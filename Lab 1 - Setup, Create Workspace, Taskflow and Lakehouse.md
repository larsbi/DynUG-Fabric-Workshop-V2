# Create Workspace
Use the name "DynUG workshop XX" where XX is the number of your user. Make sure workspace is assigned to “FabConUS5-P4 North Central US”:

<img width="733" height="897" alt="image" src="https://github.com/user-attachments/assets/d2b612ef-bb41-4460-9ac8-7a4431f505ef" />

# Setup Task flow

Setup task flow in workspace, select predesigned task flow "Medallion". 

**First delete:**

•	“Further transform”

•	“ML serving”

Create link between “Silver data” and “Gold data”. 

**Next, create new one new tasks:**

•	"Store data" task, name it "Semantic model"

Modify the link between "Gold data" and "Data visualize" to be a link between from "Gold data" to "Semantic model", and create new link from "Semantic model" to "Data visualize".

**Finally, rename**

• "High-volume data ingest" to "Load from Fabric SQL db" 

• "Low-volume data ingest" to "Load customer reviews"

The Task flow should look like this:

<img width="1586" height="267" alt="image" src="https://github.com/user-attachments/assets/ededfedf-1f58-440f-bf91-3fa91c8c5c01" />

# Create Lakehouse

Create new Lakehouse by creating “New item” from task “Bronze data”:

<img width="495" height="248" alt="image" src="https://github.com/user-attachments/assets/1e7f5f6f-58f5-4b32-9172-33480fc0004d" />

Use the name "DynUG_Lakehouse_Bronze", keep default selection of "Bronze data" and "Lakehouse schemas":

<img width="717" height="481" alt="image" src="https://github.com/user-attachments/assets/bcbc3ee4-8037-41ce-a8ce-c719675ffee0" />


Leave Lakehouse open
