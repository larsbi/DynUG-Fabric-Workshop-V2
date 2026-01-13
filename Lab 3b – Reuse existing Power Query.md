# Reuse existing Power Query or M script

If you have some existing Power Query - either from Power BI Desktop or Dataflow Gen1 - you want to reuse, that can be done easily using Dataflow Gen2 in Fabric.

In the <a href="https://github.com/larsbi/DynUG-Fabric-Workshop-V2/tree/main/code">code folder</a>, you find 3 files you can use to test reusing Power Query:
1. Lab 3b Power Query for DFGen2.pbix
  
   This is a Power BI Desktop file containing two queries. To complete the labs, you should use the query DimStore and load data to "DynUG_Lakehouse_Bronze"
2. Lab 3b Power Query for DFGen2.txt

   This is a _raw_ M script for the query DimStore. Load data to "DynUG_Lakehouse_Bronze"
3. Lab 3b Dataflow Gen1 sample.json

   This is an export of a Dataflow Gen1 you can use. To complete the labs using this Dataflow Gen1, create a new Dataflow Gen1 and import this json file:

    <img width="817" height="352" alt="image" src="https://github.com/user-attachments/assets/31fa7b6b-2292-4b98-ae58-263a578c2b54" />

   You will need to configure the connection by editing the query and use Anonymous as Authentication kind.

   Load data to "DynUG_Lakehouse_Bronze"
   

You decide which option you want to use and instructions are found below.

The important part is that you load data to "DynUG_Lakehouse_Bronze" to a table called DimStore.

If you choose to create a new Dataflow Gen2, you should add a new "Get data" task and link it to "Bronze data"

# Reuse from Power BI Desktop or M scripts

There is not an automated way to migrate Power Query from Power BI Desktop or a basic M script to Dataflow Gen2. In this case manual copy/paste is required.

If you start in **Power BI Desktop**, go to Power Query by selecting "Transform data" in Home ribbon:

<img width="804" height="166" alt="image" src="https://github.com/user-attachments/assets/bd793184-a550-4ddc-b387-e946bc06ac53" />

In the Power Query window, navigate to the query or queries you want to use in Dataflow Gen2. E.g. DimStore in this example:

<img width="300" height="244" alt="image" src="https://github.com/user-attachments/assets/7ba76228-1326-4023-bd19-8a73f11bb1b4" />

There are a few ways to get the M script from the query, preferred way is to copy queries in the Queries list (right-click the query and select "Copy" or simply use CTRL+C), alternatively select "Advanced Editor" in Home or View ribbon and copy the M script. Using _copy query_, you can select multiple queries, using "Advanced Editor" you can only copy one query at a time.

Next, you must open an exiting Dataflow Gen2 item or create a new Dataflow Gen2. Depending on the way M script has been copied, you need to perform differenct actions:

**Using copied queries**
In this case, you can simply paste the M script without manually creating anything first.
When creating a new Dataflow Gen2, you can just do paste using CTRL+V. 
Using an existing Dataflow Gen2, first click in the Queries list and then paste. 

Once query has been copied, you may need to configure connectivity details.

**Using Advanced Editor**
In this case, you only copy the _raw_ M script without any details about the query. Therefore, you must create Blank query and paste M script in the source for the Blank query, replace the default content in Blank query with the copied M script:
<img width="551" height="243" alt="image" src="https://github.com/user-attachments/assets/a1b8dd3d-c522-4c0c-8b51-f408673e6c28" />

Once query has been copied and new query created, you may need to configure connectivity details.

# Reuse from Dataflow Gen1

If you already have one or more Dataflow Gen1, there is built-in feature to migrate to Dataflow Gen2. This is all documented <a href="https://learn.microsoft.com/en-us/fabric/data-factory/migrate-to-dataflow-gen2-using-save-as">here</a>
