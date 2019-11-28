# Upgrad-ETL-Batch-Processing

Problem Statement
Ingest the India Annual Health Survey (AHS) 2012-13 data hosted on Amazon RDS into Hadoop correctly and process it to generate the following analyses:

 

Analyses

The child mortality rate in Uttar Pradesh
The fertility rate in Bihar
State-wise child mortality rate and state-wise fertility rate and does high fertility correlate with high child mortality?
Find top 2 districts per state with the highest population per household
Find top 2 districts per state with the lowest sex ratios
Such analyses would help in vivid understanding and timely monitoring of different determinants on well-being and health of population particularly Child and Reproductive Health. Based on the analyses, one can also compare India’s position in Global HDI and can suggest ways that can improve it.

 

Guidelines
Ingest data from Amazon RDS to HDFS using Sqoop.

Create an external table in Hive for the ingested data containing all the columns as given in this document. Ingest the data from HDFS to the Hive table. Verify that the ingestion is successfully accomplished.

Columnsfile_download	Download
Sample Data Corresponding To The Columnsfile_download	Download
Create a subset schema in Hive to store the data for the analyses to be done. The schema should be optimized to support ONLY the analyses to be done. You will be graded on your choice of the chosen columns, storage format (Parquet, RC, ORC, CSV), etc.  Benchmark the performance of the storage formats before finalizing the one to be used. 
You are also expected to create and test the performance of Hive-Hbase integrated table. The Hive-Hbase integrated table should be based on the subset schema you created. Benchmark the performance of Hive-Hbase integrated table as well. 
Write queries against each category of analyses. You will be graded on the relevance of your query to the analytical use case and the optimizations used. Generate the corresponding analyses’ charts on Hue. For each analysis, you need to write and run queries for the Hive table(with the storage format you chose) as well as the Hive-Hbase integrated table .

 

Note: To access Amazon RDS, refer to the resources section for more details.

 

Note: The size of the dataset is around 2.5 MB. This is a representative sample and the actual dataset will be of a bigger size. This sample is specifically taken keeping in mind that the engineering process for the data of any size remains the same. Some optimizations might vary as the dataset grows larger. However, while designing the solution, keep optimization in mind and submit a solution that would work even if we increase the size of this dataset. 

 

Tasks
Data Ingestion from the RDS to HDFS using Sqoop

Sqoop import command

Command to see the list of imported data

External table creation in Hive and loading the ingested data into it. Data ingestion verification.

Command to create the external table

Command to load the ingested data into the external table

Queries to verify that the ingestion is correctly accomplished

Query to count the total number of rows along with the screenshots of the data fetched by the query on MySQL Workbench and Hue

Query to select the top 10 rows and first 8 columns along with the screenshots of the data fetched by the query on MySQL Workbench and Hue

Subset schema creation in Hive to support the analyses

Columns used in the subset schema

Storage format used 

[Benchmark the performance before finalizing the storage format to be used. Create one schema using default format and one in any other format such as ORC for the columns to be used. Insert data into both the tables created. Compare the runtimes of the following queries and decide which format to be used.

select count(*) from <Table Name>;
select State_Name, count(*) from <Table Name> group by State_Name;
select * from <Table Name> where State_Name = ‘Uttar Pradesh’;]

You are also expected to benchmark the performance of Hive-Hbase integrated table. Compare the runtimes of the queries in step 2 for the integrated table and the storage format chosen in step 2. 

Create and insert command for the default format

Create and insert command for the formats such as ORC

Create and insert command for the Hive-Hbase integrated table

Screenshot of runtimes against each query, given above in step 2, for the default format,  for the formats such as ORC as well as for the Hive-Hbase integrated table.

Create and insert command for the partition table for analyses 1 & 2. The partition table should be created using the table created above. This step to be done for the Hive only table.

Note: While doing the benchmarking, you might get the run times of formats such as ORC different than expected. These anomalies exist if the dataset is small. The main idea is to let you know that benchmarking is an important step in the end to end engineering process. Generally, you would benchmark the performance against different formats and choose the best. However, here go ahead with the formats such as ORC only. 

 

The result of each analysis along with the query and the corresponding chart generated in Hue for both tables. Keep optimizations in mind

The child mortality rate of Uttar Pradesh

Query

Screenshot of the result

The fertility rate of Bihar

Query

Screenshot of the result

State wise child mortality rate and state wise fertility rate and does high fertility correlate with high child mortality?

Query

Screenshot of the result

Chart

Find top 2 districts per state with the highest population per household

Query

Screenshot of the result

Chart

Find top 2 districts per state with the lowest sex ratios

Query

Screenshot of the result

Chart

Note: For doing the analyses, prefer directly using the relevant columns rather than the computations. Your grading will not be affected if you directly use the relevant columns. Moreover, you will not get extra marks for doing unnecessary computations.

The analyses asked can be done directly using the relevant columns only. Approximations such as using the average function can be used.

The primary purpose is to get you familiar with the end to end engineering process. So the focus is not on the computations.

 

Refer to the sample solution given in Submission segment of the next Submission Guidelines session for getting more clarity on the things to be submitted.
