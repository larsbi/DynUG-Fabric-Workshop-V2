# Load data using Dataflow Gen2

Create new Dataflow Gen2 by creating “New item” from task “Load customer reviews”:
<img width="538" height="291" alt="image" src="https://github.com/user-attachments/assets/382963d0-a4bb-460d-af4c-f1307c8696d0" />

Use the name “DynUG Dataflow Gen2”

The source file “Customer reviews.xls” is stored in the Lakehouse called “DynUG_source_Lakehouse”. Choose “Get data from another source”:

<img width="940" height="368" alt="image" src="https://github.com/user-attachments/assets/74fa427a-b2f3-445d-a74a-f371024fc81c" />

If you cannot locate “DynUG_source_Lakehouse” on the landing page, select OneLake catalog in the left navigation to locate the Lakehouse. Expand Files folder and select “Customer reviews.xls”, followed by clicking Create.

Click on [Table] in the row where name is “CustomerReviews”, this will expand the Excel-table called “CustomerReviews”. Rename the query to “CustomerReviews”:

<img width="940" height="400" alt="image" src="https://github.com/user-attachments/assets/9b700ae7-c750-4515-a2d6-84d12a08d177" />

No further transformations are needed. However, the Data destination should be the Lakehouse you created. Select + next to Data destination in the lower right-hand corner:

<img width="477" height="223" alt="image" src="https://github.com/user-attachments/assets/69ce70de-9d55-4212-9788-a2e9946b5f8e" />

Then select Lakehouse and navigate to the Lakehouse “DynUG_Lakehouse_Bronze” you have created (do not use the Lakehouse “DynUG_workshop_source”). Click Next.

Keep default destination settings and click Save settings.

Select “Save, run & close” in the Home ribbon:

<img width="314" height="389" alt="image" src="https://github.com/user-attachments/assets/1a8a15ea-ffaa-4c3e-a75e-3daf8d091273" />

Now the Dateflow Gen2 will load data from the Excel file to your Lakehouse.

It can take a few minutes to run. While you are waiting, you can take a look your Fabric activities by selecting “Monitor” in the left navigation. Initially, you will likely see that your Dataflow Gen2 is in progress:

<img width="940" height="411" alt="image" src="https://github.com/user-attachments/assets/864ddb07-9124-4157-bec2-86b2b483b7bd" />

When it has finished running, go to your Lakehouse and validate that you have a table called “Customer reviews” (remember, you may need to refresh Lakehouse):

<img width="492" height="642" alt="image" src="https://github.com/user-attachments/assets/f8f50a34-7794-46ee-b997-0c765f5da198" />

