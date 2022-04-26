# Analysis_Services_AW_Internet_Sales
Analysis Services Course from Microssoft 

Adventure Works Internet Sales tutorial (1500)
---------------------------------------------------------------------------------------------------------------------------------------------------------
•	How to create a new tabular model project at the 1500 compatibility level in Visual Studio.
•	How to import data from a relational database into a tabular model project workspace database.
•	How to create and manage relationships between tables in the model.
•	How to create calculated columns, measures, and Key Performance Indicators that help users analyze critical business metrics.
•	How to create and manage perspectives and hierarchies that help users more easily browse model data by providing business and application-specific viewpoints.
•	How to create partitions that divide table data into smaller logical parts that can be processed independent from other partitions.
•	How to secure model objects and data by creating roles with user members.
•	How to deploy a tabular model by using Visual Studio.

Scenario
---------------------------------------------------------------------------------------------------------------------------------------------------------

This  is based on Adventure Works Cycles, a fictitious company. Adventure Works is a large, multinational manufacturing company that produces and distributes bicycles, parts, and accessories for commercial markets in North America, Europe, and Asia. The company employs 500 workers. Additionally, Adventure Works employs several regional sales teams throughout its market base. Your project is to create a tabular model for sales and marketing users to analyze Internet sales data in the AdventureWorksDW database. The purpose is learning how to work with a basic tabular model by using many of the features included in Visual Studio with Analysis Services projects.


---------------------------------------------------------------------------------------------------------------------------------------------------------

First, let's create a tubular model project in visual studio, remembering that for this example it needs to be in version 2019, for reasons of compatibility with SQL 2019.

![image](https://user-images.githubusercontent.com/81394440/163251139-29e9b6a7-3398-45fb-bafa-9b4ed1809a14.png)

![image](https://user-images.githubusercontent.com/81394440/163251208-eac4ecfa-9d0d-476c-94ea-42b6483f8dac.png)

Now in our Azure environment, let's create our sample database. Azure provides an example database that we are going to work, called Adventure Works DW. So let's create our SQL Pool passing the Sample Database parameter shown below.

![image](https://user-images.githubusercontent.com/81394440/163252277-b13568a6-4567-49e8-8e80-71122a3096fc.png)

![image](https://user-images.githubusercontent.com/81394440/163252297-d1485825-22ca-43f9-a5ea-a48e02e1f197.png)

![image](https://user-images.githubusercontent.com/81394440/163252325-8e688dd8-f054-4eda-b0c5-e1490fa87b11.png)

With our sample database in hand, we are now going to create a connection from this database to our tubular project in visual studio
A detail that we cannot forget is to define the firewall and connection permissions so that it can be carried out without major problems.

In Tabular Model Explorer, right-click Data Sources > Import from Data Source.
This launches Get Data, which guides you through connecting to a data source. If you don't see Tabular Model Explorer, in Solution Explorer, double-click Model.bim to open the model in the designer.
![image](https://user-images.githubusercontent.com/81394440/163253307-84441755-6679-4953-bc27-9aabe7b92c35.png)

So we just pass our credentials and access the data.
![image](https://user-images.githubusercontent.com/81394440/163253404-6010c9d2-712d-4e50-8c25-20763fd90fc6.png)

![image](https://user-images.githubusercontent.com/81394440/163253418-6dc12743-9f8d-4de6-af86-285601b1ae14.png)

Get Data
---------------------------------------------------------------------------------------------------------------------------------------------------------

Now that we have access to the tables, we can, for example, select only the tables we want to work with and perform any necessary transformation that can later be loaded into our Analisys Services, so we have our complete ETL.
![image](https://user-images.githubusercontent.com/81394440/163254787-1c623278-a549-402c-b389-066b124870ca.png)

![image](https://user-images.githubusercontent.com/81394440/163254282-f8e080ae-9e6f-4e2e-b5cb-8be9efdd43a5.png)

We can apply specific metrics and various other features such as calculated columns based on other columns for example.

![image](https://user-images.githubusercontent.com/81394440/163254571-797d45b0-41d1-4d2f-ac11-6b4104fbb917.png)

Other features:
We can perform many data transformations in our tabular project, such as creating calculated tables, managing or creating relationships between tables, and many things before we deploy the project to Analysis Services.

In Diagram view for example we can see the relationship and edit then:
![image](https://user-images.githubusercontent.com/81394440/165366656-9e4dd612-4866-4f8f-a15d-a50424a91b22.png)

Creating a calculated colunm:
![image](https://user-images.githubusercontent.com/81394440/165367140-39b075e6-2a77-4e7b-9958-84ff06721631.png)
Using the column MonthNumberOfYear and EnglishMonthName we created the MonthCalendar Column for example.
=RIGHT(" " & FORMAT([MonthNumberOfYear],"#0"), 2) & " - " & [EnglishMonthName]

Partitions
---------------------------------------------------------------------------------------------------------------------------------------------------------

Partitions divide portions of data you need to process (refresh) frequently from data that can be processed less frequently. For example, a fact table may include certain row sets that contain data that rarely changes, but other row sets have data that changes often. There's no need to process all of the data when only a portion of it needs to be processed.

Partitions work by dividing a table into logical partition objects. Individual partitions, each containing a unique segment of data, can then be incrementally processed either sequentially or in parallel independent of other partitions, or excluded from processing operations altogether.

![image](https://user-images.githubusercontent.com/81394440/165368814-d738058c-2a11-42fd-9957-26d030da4511.png)

In this project we will create partitions based on sales from the year 2001 to 2005:

![image](https://user-images.githubusercontent.com/81394440/165369564-6667b770-12b5-4c76-9e78-7d70338ac15d.png)

![image](https://user-images.githubusercontent.com/81394440/165369607-be9eb418-cfb2-4975-b2ff-4bed4961a43e.png)


Deploy
---------------------------------------------------------------------------------------------------------------------------------------------------------
In this project we are going to Deploy to Azure Analysis Services, for this you will need some admin permissions on the server.
If you are going to replicate in the same way, don't forget to configure this step.

Deploy the Model.

In Solution Explorer, right-click the AW Internet Sales project, and then click Properties.

![image](https://user-images.githubusercontent.com/81394440/165370352-76d33ec4-4e63-420e-b86b-6d1a98d31c55.png)

In the AW Internet Sales Property Pages dialog box, under Deployment Server, in the Server property, enter the full server name.

- If deploying to Azure Analysis Services, server name is a URL. In the portal, copy the Azure Analysis Services server name URL from the server's Overview page.
- If deploying to a Power BI Premium workspace, server name is a Workspace Connection URL. In the Power BI service, copy from workspace Settings > Premium > Workspace Connection.

![image](https://user-images.githubusercontent.com/81394440/165370938-0482d766-ac15-4f45-8490-e080be5fda7f.png)

In the Database property, type Adventure Works Internet Sales.

In the Model Name property, type Adventure Works Internet Sales Model.

Verify your selections and then click OK.

![image](https://user-images.githubusercontent.com/81394440/165371122-ef0bb5d4-b5f9-4a19-87f4-359bf1f5bc80.png)

In Solution Explorer, right-click the AW Internet Sales project > Build.

Right-click the AW Internet Sales project > Deploy.

![image](https://user-images.githubusercontent.com/81394440/165371381-4ab59ad5-cf98-423b-b784-bfeaef633e7e.png)

![image](https://user-images.githubusercontent.com/81394440/165371688-de2d9563-4e9c-4d60-921e-a6e7f7466fd9.png)

We can now see in our azure environment in our Analysis Services if Deploy actually worked.

![image](https://user-images.githubusercontent.com/81394440/165372353-7aa8e4e0-4b87-45ce-85bb-34efd7e1cfb8.png)

As we can see the deployment worked, we can now create, for example, a connection with Power BI and create dashboards based on our Analysis Services data.

Below is a small example of a dashboard created with the data from our connection to Analysys Services:
![image](https://user-images.githubusercontent.com/81394440/165372871-d4457215-c0bc-4b68-9e2b-6db04893a18f.png)


