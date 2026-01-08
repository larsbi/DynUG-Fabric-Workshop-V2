<a href="https://github.com/microsoft/semantic-link-labs">Semantic Link Labs</a>  can be utilized to upgrade multipe Dataflow Gen1 to Gen2 following these instructions.

# Install Semantic Link Labs in your notebook
```python
%pip install semantic-link-labs
```

# Upgrade all Dataflow Gen1 in a workspace
```python
workspace_name = "<enter workspace name>"
alldataflows = labs.list_dataflows(workspace_name)
gen1dataflows = alldataflows[alldataflows["Generation"].str.lower().eq("gen1")]
gen2dataflows = alldataflows[alldataflows["Generation"].str.lower().eq("gen2 ci/cd")]

for index, row in gen1dataflows.iterrows():
        dataflowid = row["Dataflow Id"]
        dataflowname = row["Dataflow Name"]
        newdataflowname = dataflowname + '-CICD'
        dataflowgen = row["Generation"]
        #print(f"Index: {index}, Id: {dataflowid}, Name: {dataflowname}, Gen: {dataflowgen}")
        checkgen2 = gen2dataflows[gen2dataflows["Dataflow Name"].str.lower().eq(str.lower(newdataflowname))]

        #All dataflows will be upgraded to Dataflow Gen2 and "-CICD" will be added to the original name. If there is already a Dataflow Gen2 with the name, it will not be upgraded
        if checkgen2.empty:
            labs.upgrade_dataflow(dataflowid, workspace_name, dataflowname + '-CICD')
```
