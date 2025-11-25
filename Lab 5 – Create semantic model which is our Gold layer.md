# Create semantic model and Power BI report

Create a semantic model that will act as our Gold layer. Follow these steps:

1.	Go to Lakehouse “DynUG_Lakehouse_Silver” (makes sure you have all 5 tables, refresh Lakehouse if needed)

2.	In Home ribbon, select New semantic model:
<img width="802" height="131" alt="image" src="https://github.com/user-attachments/assets/e291fb35-d252-4ba5-8ee9-9c999ab98d74" />

3.	Use the name “Sales and sentiment model” and select all 5 tables (if not visible, cancel “New semantic model” dialog and go back to refresh Lakehouse)

    Click Confirm

4.	The web model view will appear after a few seconds. Here, you must create the following relationships:

    dimcustomer.CustomerID -> factsales.CustomerID
    
    dimdate.DateID -> factsales.DateID
    
    dimproduct.ProductID -> factsales.ProductID 
    
    customerreview.CustomerID -> factsales.CustomerID

5.	Validate the relationships and cardinality – it should be "Many to one" where Fact is on the Many-side. This can be validated by seeing * on the Fact and 1 on Dimensionts:
<img width="940" height="686" alt="image" src="https://github.com/user-attachments/assets/ca2f314a-7a1b-4f07-b052-a26b4526bab9" />

If needed double-click a relationship and modify cardinality, and column mapping:

<img width="863" height="1016" alt="image" src="https://github.com/user-attachments/assets/22aa75a6-7f3d-4cfe-87f9-8b4b3c973bec" />

Now you created a basic semantic model in Direct Lake mode. In real life, you will also define measures, hide columns and configure data categories & summarize by for relevant columns and more.

Next, go back to the workspace and attach the semantic model to the task “Golden data”.

# Create Power BI report

Final step is to create a Power BI report, do it by adding an item from the task “Data visualize”, select Report and select semantic model “Sales and sentiment model”, remember to select “Create a blank report” and not “Auto-create report”:

<img width="586" height="291" alt="image" src="https://github.com/user-attachments/assets/0f297356-9ef6-443f-968e-9151830a234f" />

Create a visual showing Total sales by sentiment. Use Sentiment from customerreview table and TotalSales from factsales. You can also try to make Copilot create your report.

Save the report with the name “Sales by sentiment”:

<img width="948" height="635" alt="image" src="https://github.com/user-attachments/assets/d4fa212b-646f-442c-9ed0-58c168f6b08a" />

# Final result

Go back to the workspace and you have now created your small Fabric project, and the content of the workspace should look like this:

<img width="940" height="504" alt="image" src="https://github.com/user-attachments/assets/5b26a54a-ad87-4052-94bd-5ff0e5924d1f" />
