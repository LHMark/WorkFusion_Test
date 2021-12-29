## Creating, testing, and running bots in WorkFusion
### Description
This article discusses how to use WorkFusion tools to create, test, and run bots. These bots perform the steps in your business process that are more suited for automation than human labor. 
### Terminology
**Bot Tasks** contain the work that WorkFusion’s bots will do. Examples include:
- Parsing addresses.
- Determining image dimensions.
- Interacting with your API or repository.
- Filtering specified content.

Bot Tasks can exist only as a Business Processes step.

**Bot Configs** are your bots’ XML configuration files. 
- WorkFusion executes bot configs separately for each record. 
- Bot configs are written using the Web-Harvest library.
- You can use the predetermined Web-Harvest XML elements described here or WorkFusion plugins to write Web-Harvest XML bot configs.

**Bot Config Bundles** are bundled Java libraries that contain:
- A bot config.
- A Java code reference for use within the bot config.
### Procedure
You create bots with WorkFusion Studio (our Eclipse-based IDE). 
1. In WorkFusion, create a **Bot Use Case.** As a best practice, select the **ETL** use case type, as it is the most flexible and reusable use case type.
2. Create a **Business Process (BP)** and include a **Bot Step** based on the Bot Use Case you defined in step 1. Alternatively, you can import a Bot Config Bundle by using a WorkFusion Repository.
3. Using a small input batch, test the bot config in your BP: Ensure that the **column name**, **output column name**, **use proxy**, and **datastore connection** values are correct.
4. Update the Bot Use Case with any changes you made during testing. Then, use it in your production BP.

You can also create a bot from scratch in your BP by using the **Design Process** tab and pasting your code, but this approach can cause multiple issues.

### Execution details
WorkFusion will execute the Bot Config file for each submission. If your input CSV file contains 40 records, the system will run the XML configuration 40 times, once for each record. If an error occurs, the system will run the Bot Config 5 times. 
### Results
WorkFusion defines Bot Task results in the `<export>` plugin settings. You can use all columns the Bot Task creates in further BP steps (both manual and automated). 

### Example
This sample XML performs the following steps:
1. Get an HTTP response from URLs listed in the input data file’s url_to_check column.
2. Store the HTTP response in the http_response variable. 
3. Export all original column.
4. Add a new column, labeled **http**, containing the **http_response** variable value. 
``` 
<?xml version="1.0" encoding="UTF-8"?>
<config>
<!--defining variable-->
<var-def name="http_response">
<!--passing the appropriate value from url_to_check column in input data file
as a parameter for http plugin-->
<http url="${url_to_check}"></http> </var-def>

<!--exporting all original input columns-->
<export include-original-data="true">
<!--adding a new column with the http plugin result to the export file-->
<single-column name="http" value="${http_response}"/> </export>

</config>
```


