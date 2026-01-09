# Create Warehouse

The gold layer will be a Warehouse in Fabric.

In task "Gold data", create a Warehouse item and name it "DynUG_Warehouse_Gold":

<img width="407" height="205" alt="image" src="https://github.com/user-attachments/assets/39f2b117-a389-4e56-adcb-1b1ba60dc371" />

Navigate back to workspace and confirm that Warehouse is assigned to task "Gold data". If not, assign the newly created Warehouse to "Gold data"

# Get data from Silver Lakehouse to Warehouse

The easiest way to make data available in the Warehouse, is to create views based on tables in Silver Lakehouse utilizing SQL Analytics Endpoint.

In Warehouse, create a New SQL query:

<img width="400" height="124" alt="image" src="https://github.com/user-attachments/assets/ac9f4920-eed7-4f78-b011-446f3eb9522e" />

Use this SQL to create the 6 views:

```sql
CREATE OR ALTER VIEW FactSales AS
SELECT *
FROM DynUG_Lakehouse_Silver.[dbo].[FactSales];
GO

CREATE OR ALTER VIEW customerreviews AS
SELECT *
FROM DynUG_Lakehouse_Silver.[dbo].[customerreviews];
GO

CREATE OR ALTER VIEW DimCustomer AS
SELECT *
FROM DynUG_Lakehouse_Silver.[dbo].[DimCustomer];
GO

CREATE OR ALTER VIEW DimDate AS
SELECT *
FROM DynUG_Lakehouse_Silver.[dbo].[DimDate];
GO

CREATE OR ALTER VIEW DimProduct AS
SELECT *
FROM DynUG_Lakehouse_Silver.[dbo].[DimProduct];
GO

CREATE OR ALTER VIEW DimStore AS
SELECT *
FROM DynUG_Lakehouse_Silver.[dbo].[DimStore];
GO
```
