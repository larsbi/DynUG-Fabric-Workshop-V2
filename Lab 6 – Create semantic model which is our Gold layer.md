# Create semantic model and Power BI report

Create a semantic model based on Gold layer in Warehouse. Follow these steps:

1.	Go to Warehouse “DynUG_Warehouse_Gold”, make sure you have all 5 views:

    <img width="437" height="605" alt="image" src="https://github.com/user-attachments/assets/02252061-7546-4004-894c-2a72b1fbbbd6" />

3.	In Home ribbon, select New semantic model:

    <img width="649" height="113" alt="image" src="https://github.com/user-attachments/assets/003fa4fc-8298-492c-bdde-7d49afbc25cd" />

5.	Use the name “Sales and sentiment model” and select all 6 views

    <img width="598" height="732" alt="image" src="https://github.com/user-attachments/assets/ec944b86-1206-406c-9b98-a582bb1207e9" />

    Click Confirm

7.	The web model view will appear after a few seconds. Here, you must create the following relationships:

    FactSales.CustomerID -> DimCustomer.CustomerID
    
    FactSales.DateID -> DimDate.DateID
    
    FactSales.ProductID -> DimProduct.ProductID

  	DimProduct.StoreID -> DimStore.StoreID
    
    customerreview.CustomerID -> FactSales.CustomerID

9.	Validate the relationships and cardinality – it should be "Many to one" where Fact is on the Many-side. This can be validated by seeing * on the Fact and 1 on Dimensionts:
<img width="940" height="686" alt="image" src="https://github.com/user-attachments/assets/ca2f314a-7a1b-4f07-b052-a26b4526bab9" />

If needed double-click a relationship and modify cardinality, and column mapping:

<img width="863" height="1016" alt="image" src="https://github.com/user-attachments/assets/22aa75a6-7f3d-4cfe-87f9-8b4b3c973bec" />

Now you created a basic semantic model in Direct Lake mode. In real life, you will also define measures, hide columns and configure data categories & summarize by for relevant columns and more.

Next, go back to the workspace and attach the semantic model to the task “Semantic model”.

# Create Power BI report

Final step is to create a Power BI report, do it by adding an item from the task “Data visualize”, select Report and select semantic model “Sales and sentiment model”, remember to select “Create a blank report” and not “Auto-create report”:

<img width="586" height="291" alt="image" src="https://github.com/user-attachments/assets/0f297356-9ef6-443f-968e-9151830a234f" />

Create a visual showing Total sales by sentiment. Use Sentiment from customerreview table and TotalSales from factsales. You can also try to make Copilot create your report.

Save the report with the name “Sales by sentiment”:

<img width="948" height="635" alt="image" src="https://github.com/user-attachments/assets/d4fa212b-646f-442c-9ed0-58c168f6b08a" />

# Final result

Go back to the workspace and you have now created your small Fabric project, and the content of the workspace should look like this:

<img width="940" height="504" alt="image" src="https://github.com/user-attachments/assets/5b26a54a-ad87-4052-94bd-5ff0e5924d1f" />
