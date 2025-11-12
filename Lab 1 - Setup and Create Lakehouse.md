# Create Workspace
Use the name "DynUG workshop XX" where XX is the number of your user. Make sure workspace is assigned to “FabConUS5-P4 North Central US”:

<img width="733" height="897" alt="image" src="https://github.com/user-attachments/assets/d2b612ef-bb41-4460-9ac8-7a4431f505ef" />

# Setup Task flow

Setup task flow in workspace Select predesigned task flow "Medallion" Delete:

•	“Further transform”

•	“ML serving”

Create link between “Silver data” and “Gold data”. 

Rename

• "High-volume data ingest" to "Load from Fabric SQL db" 

• "Low-volume data ingest" to "Load customer reviews"

The Task flow should look like this:

<img width="1612" height="278" alt="image" src="https://github.com/user-attachments/assets/6a2094b2-cc45-4982-b05c-dd1cd609869b" />

# Create Lakehouse

Create new Lakehouse by creating “New item” from task “Bronze data”:

<img width="495" height="248" alt="image" src="https://github.com/user-attachments/assets/1e7f5f6f-58f5-4b32-9172-33480fc0004d" />

Use the name "DynUG_Lakehouse_Bronze".

Leave Lakehouse open
