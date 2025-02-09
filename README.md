# Azure_Data_Engineer
quiz -2 :

1.You're starting a project for a client in Paris. To minimize latency, which Azure region might you choose?

West US

Australia East

North Europe

Brazil South
Explanation:

2.For the project in Paris, North Europe is a sensible choice due to geographical proximity, potentially offering lower latency than more distant regions.

Your team is working on two separate projects: "AppDev" and "DataAnalytics". How would you best organize your Azure resources?

Create one resource group for both projects

Create separate resource groups for each project

Use tags within a single resource group

Merge both projects into a single application
Explanation:

Organizing Azure resources for "AppDev" and "DataAnalytics" projects separately enhances management and clarity, making "Create separate resource groups for each project" the best practice.

3.You have accidently deleted the a very crucial file from storage account. How can we recover?

Recreate the blob manually

Use the Soft Delete feature

Contact Azure Support

Restore from a backup
Explanation:

Soft Delete for Azure Blob Storage allows you to recover blobs that were mistakenly deleted. When enabled, blobs are retained for a specified period after deletion, giving you the opportunity to restore them.

4.Your application requires frequent read and write operations. Which redundancy option ensures the highest availability in a single region?

Locally-redundant storage (LRS)

Zone-redundant storage (ZRS)

Geo-redundant storage (GRS)

Read-access geo-redundant storage (RA-GRS)
Explanation:

Zone-redundant storage (ZRS) offers high availability within a single region by replicating data across multiple data centers, making it the optimal choice for applications requiring frequent read/write operations

5.A healthcare app stores sensitive patient data in Azure. Is the data encrypted in azure storage?

True

False
Explanation:

Yes

------------------------x=========================



Quiz no-3:

1.What is the main purpose of the Lookup activity in Azure Data Factory?

To copy data from a source to a destination.

To create a data flow.

To fetch a dataset and make it available for other activities in the pipeline.

To execute a SQL query against a database.

2.You have a pipeline 'Pipe1' that you want to execute from another pipeline 'Pipe2'. How would you do that?

By using a ForEach activity in 'Pipe2'.

By using an If Condition activity in 'Pipe2'.

By using an Execute Pipeline activity in 'Pipe2'.

By using a Lookup activity in 'Pipe2'.

3.If you want to execute an activity only when a certain condition is met, which activity should you use?

Lookup activity.

Until activity.

If Condition activity.

Web activity.

4.Consider the following code snippet in ADF: "activities": [ { "name": "LookupActivity", "type": "Lookup", "typeProperties": { "source": { "type": "SqlSource", "sqlReaderQuery": { "value": "@dataset().sqlQuery", "type": "Expression" }}}}] What does this code do?

It executes a SQL query stored in a dataset parameter named 'sqlQuery'.

It copies data from a source to a destination.

It fetches a dataset and makes it available for other activities in the pipeline.

It triggers another pipeline.

5.You are using the Lookup activity to fetch a dataset from a source. Can this dataset be used in subsequent activities in the same pipeline?

Yes, but only in the activity that follows the Lookup activity.

Yes, it can be used in any activity within the same pipeline.

No, it cannot be used in any other activity.

Yes, but only in a Copy activity.

6.You are fetching a dataset using a Lookup activity. You want to use this dataset in a Copy activity. Where would you provide the dataset's name in the Copy activity?

In the 'Source' tab of the activity.

In the 'Sink' tab of the activity.

In the 'General' tab of the activity.

In the 'Settings' tab of the activity.

7.Assume you are working as a Data Engineer for azurelib.com. You are tasked to develop a pipeline that should execute a child pipeline but only when a certain condition is met. Which Azure Data Factory activities would you need to use to accomplish this?

If Condition and Execute Pipeline activities.

Lookup and Until activities.

Web and Execute Pipeline activities.

Switch and ForEach activities.

8.Assume you are working as a Data Engineer for azurelib.com. Your team uses a Data Factory pipeline which fetches a dataset from a database using a SQL query. This query should be configurable so that it can be easily adjusted in the future. How would you implement this functionality in the pipeline?

By creating a parameter in the dataset that the SQL query uses and storing the SQL query in this parameter.

By creating a variable in the pipeline and storing the SQL query in this variable.

By storing the SQL query in the linked service that the dataset uses.

By storing the SQL query in the source of the Copy activity.

9.Is nested if else allowed in ADF pipeline

TRUE

FALSE

10.Is nexted For each acitvity allowed in ADF

TRUE

FALSE




-=---=-=---=-=---==-=-=-=--=


QUIZ 4:

1.Your pipeline is set up to load data incrementally using the highwater mark. The pipeline fails mid-load. What happens when you restart it?

It starts loading from the beginning.

It continues loading from where it failed.

It loads only the failed files.

It does nothing until manual intervention.

2.You've just run a pipeline and forgot to update the highwater mark. What's the impact?

The next pipeline run will reload all data.

The next pipeline run will not load any data.

The next pipeline run will only load new data.

The next pipeline run will fail.

3.In your ADF pipeline, you've incorporated metadata activity to read file properties. Which of these properties is not available from metadata activity?

Child Items

Structure

Content

Item Name

4.Your pipeline processes files stored in Azure Blob Storage. How can you use metadata activity to only process the most recently added files?

Sort by LastModified property.

Sort by ContentSize property.

Filter by ContentMD5 property.

Filter by Type property.

5.What is the correct syntax to retrieve child item names from Metadata Activity output?

@activity('MetadataActivity').output.childitems

@activity('MetadataActivity').output.childitems.name

@activity('MetadataActivity').output.name

@activity('MetadataActivity').output.item.name

6.How do you specify in a Lookup activity that it should get the maximum value from a specific column?

Use the max(columnName) in the select statement.

Use @max(columnName) in the select statement.

Use @max.activity('columnName') in the select statement.

Use @activity('max').output.columnName in the select statement.

7.You've been tasked with migrating a legacy ETL process to ADF. The existing process loads data incrementally using a highwater mark stored in a SQL Server table. You've decided to continue using this highwater mark in ADF. What's the most appropriate activity to use to retrieve the highwater mark at the start of each pipeline run?

Web activity

Copy activity

Lookup activity

Get Metadata activity

8.Your ADF pipeline processes sales data from a multinational organization with multiple departments. Each department's data is stored in a separate folder in Azure Blob Storage. For cost optimization, the organization wants to process data only from departments where the number of files has increased since the last run. How would you achieve this using ADF activities?

Use the Get Metadata activity for each department folder and compare the childItemsCount with the count from the previous run.

Use the Lookup activity for each department folder and compare the childItemsCount with the count from the previous run.

Use a ForEach activity to loop through each file in each department and manually increment a counter.

Use a Copy activity with the binary copy option enabled.

9.Your team is handling a complex ADF pipeline which processes hundreds of files. It's difficult to keep track of which files have been processed during each run. How could you use ADF to maintain a record of the filenames processed?

Use a Get Metadata activity to get the filenames and a Lookup activity to store them in a SQL database.

Use a Copy activity to copy the filenames to a text file in Blob Storage.

Use a ForEach activity to loop through each file and a Web activity to post the filenames to a web service.

Use a Delete activity to remove processed files from Blob Storage.

10.You have an ADF pipeline that loads data into a data lake. Due to some network issues, your last run partially loaded data. Your pipeline uses the highwater mark for incremental loads. What steps would you take to ensure the next run captures all the required data?

Manually change the highwater mark to the timestamp of the last successful file load.

Run the pipeline again as it will automatically load from where it left off.

Delete the data loaded during the last run and run the pipeline again.

Change the highwater mark to the start time of the last run and execute the pipeline.
