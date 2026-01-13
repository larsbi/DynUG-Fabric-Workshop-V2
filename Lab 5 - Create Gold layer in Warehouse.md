# Create Warehouse

The gold layer will be a Warehouse in Fabric.

In task "Gold data", create a Warehouse item and name it "DynUG_Warehouse_Gold":

<img width="407" height="205" alt="image" src="https://github.com/user-attachments/assets/39f2b117-a389-4e56-adcb-1b1ba60dc371" />

Navigate back to workspace and confirm that Warehouse is assigned to task "Gold data". If not, assign the newly created Warehouse to "Gold data"

# Get data from Silver Lakehouse to Warehouse

There are several ways to get data from Silver Lakehouse into Gold Warehouse. In this lab we will create tables using T-SQL.

In Warehouse, create a New SQL query:

<img width="400" height="124" alt="image" src="https://github.com/user-attachments/assets/ac9f4920-eed7-4f78-b011-446f3eb9522e" />


Use this SQL to create the 6 views:

```sql
DROP TABLE IF EXISTS [dbo].[FactSales];
GO
CREATE TABLE [dbo].[FactSales] AS
SELECT *
FROM [DynUG_Lakehouse_Silver].[dbo].[FactSales];
GO

DROP TABLE IF EXISTS [dbo].[customerreviews];
GO
CREATE TABLE [dbo].[customerreviews] AS
SELECT *
FROM [DynUG_Lakehouse_Silver].[dbo].[customerreviews];
GO

DROP TABLE IF EXISTS [dbo].[DimCustomer];
GO
CREATE TABLE [dbo].[DimCustomer] AS
SELECT *
FROM [DynUG_Lakehouse_Silver].[dbo].[DimCustomer];
GO

DROP TABLE IF EXISTS [dbo].[DimDate];
GO
CREATE TABLE [dbo].[DimDate] AS
SELECT *
FROM [DynUG_Lakehouse_Silver].[dbo].[DimDate];
GO

DROP TABLE IF EXISTS [dbo].[DimProduct];
GO
CREATE TABLE [dbo].[DimProduct] AS
SELECT *
FROM [DynUG_Lakehouse_Silver].[dbo].[DimProduct];
GO

DROP TABLE IF EXISTS [dbo].[DimStore];
GO
CREATE TABLE [dbo].[DimStore] AS
SELECT *
FROM [DynUG_Lakehouse_Silver].[dbo].[DimStore];
GO
```
