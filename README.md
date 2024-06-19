## Review unstructured JSON data and diagram a new structured relational data model
###	Json to ER diagram
To convert unstructured JSON data into a structured relational data model, I first analyze the JSON structure to identify key entities and their attributes. For instance, in the provided example, I recognize Receipts and Items as main entities. Then, I define a relational schema by creating corresponding tables for these entities, such as a Receipts table with fields like _id, userId, totalSpent, and purchaseDate, and a ReceiptItems table with fields like receipt_id (foreign key referencing Receipts._id), name, and price. This schema ensures data normalization, normalized to 3NF and maintains relationships between tables.

# Data Analysis Findings and Concerns

Dear All,

This is Abhinav. I hope you all are having a good day! I've spent some time analyzing the Fetch rewards datasets for the past couple of days and wanted to apprise everyone of my findings and concerns with the data. I would appreciate your inputs/feedback on these points. Some points are addressed to specific teams but feel free to share your inputs nonetheless.

## 1. Data Quality Issues:

### NLP Team:
Do we have a more comprehensive list of items extracted from the scanned receipts like item number, item price, and its description? There are a significant number of null values in the current dataset, resulting in missing information about item purchases from the receipts. Understanding how we can improve the extraction process or fill in these gaps would be beneficial.

### BA Team:
There are quite a few missing values for brand codes. This might lead to data inconsistencies in the event of any future changes in the brand category. Addressing this will also massively help optimize our database. Can we ensure all entries have valid brand codes to maintain data integrity?

## 2. Anomalies and Data Capture Concerns:
I have observed some extreme values regarding reward points earned (some exceeding 4000 points) and the amount spent on approved cases (some more than $500 on a single receipt). Are these anomalies or incorrect data capture? I believe it is worth double-checking some of these cases to ensure data accuracy.

## 3. Barcode Relationships:
I am having trouble understanding the relationship between the barcodes of items and the barcodes of brands. Is there some logic that connects the two? Clarifying this relationship will help in better data categorization and analysis.

## 4. Performance and Scaling Concerns:
As we are growing, I anticipate a significant increase in user interaction via APIs. Therefore, we must start working on incremental backup and recovery to avoid huge downtimes. Also, since we are dealing with JSON files for each entry, what are your views on using a database like MongoDB (NoSQL) instead of RDBMS? This could potentially enhance performance and scalability.

## 5. Questions and Next Steps:

### Questions about the Data:
- Are there standardized procedures for capturing and validating data from receipts?
- How frequently are the datasets updated, and are there any processes to audit and correct anomalies?

### Discovering Data Quality Issues:
I discovered these issues through exploratory data analysis, focusing on null values, outliers, and the relationships between different data points.

### Resolving Data Quality Issues:
To resolve these issues, I need to understand the existing data extraction and validation processes. Access to more detailed documentation or direct communication with the teams involved in data capture would be helpful.

### Additional Information Needed:
- Detailed documentation of the data capture and extraction processes.
- Insights into any existing data cleaning and validation mechanisms.
- Information on how brand codes are assigned and maintained.

### Performance and Scaling Concerns:
- Anticipating increased API interactions, we should consider implementing incremental backups and recovery processes.
- Evaluating the potential shift from RDBMS to NoSQL databases like MongoDB for better handling of JSON data and scalability.
- I would really appreciate your inputs and thoughts on the above points. Feel free to connect with me if you feel a quick chat is necessary to resolve some of these issues.

Best Regards,

Abhinav
