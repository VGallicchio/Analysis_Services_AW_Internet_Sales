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

ETL
---------------------------------------------------------------------------------------------------------------------------------------------------------

Now that we have access to the tables, we can, for example, select only the tables we want to work with and perform any necessary transformation that can later be loaded into our Analisys Services, so we have our complete ETL.
![image](https://user-images.githubusercontent.com/81394440/163254787-1c623278-a549-402c-b389-066b124870ca.png)

![image](https://user-images.githubusercontent.com/81394440/163254282-f8e080ae-9e6f-4e2e-b5cb-8be9efdd43a5.png)

We can apply specific metrics and various other features such as calculated columns based on other columns for example.

![image](https://user-images.githubusercontent.com/81394440/163254571-797d45b0-41d1-4d2f-ac11-6b4104fbb917.png)





