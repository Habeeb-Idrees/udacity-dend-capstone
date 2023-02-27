# Capstone Project for Udacity Data Engineering Nanodegree
## Project Summary
As a capstone project for the Udacity Data Engineering Nanodegree, I chose to go with the Udacity provided project as the final project. The purpose of the project was to take multiple different datasets, clean, and process them for analysis. In other words, process multiple data sources and create a dataset suitable for analytics through an ETL pipeline.

The project uses the Udacity-provided I94 immigration data, enriches the data using other suggested sources and creats a suitable data warehouse for analytics. in fact, the project utlises I94 immigration, global land temperatures and US city demographics datasets to create an analytical data lake that can be used to analyse immigration events to the US. For instance,  What cities has what demographic immigrates to the most and do climate effect these percentages and at what time of year. Questions of that sort can be extracted from the main immigration fact table using the datasets.

The project is divided into three phases:

1. The immigration SAS data is partitioned by year, month, and day and stored as Parquet files in an Amazon S3 data bucket.
2. The partitioned data is loaded into a Redshift wherehouse staging tables.
3. The staging data is combined with other staged data sources to produce the final fact and dimension records in a Redshift warehouse.

The final data set can be used to explore several questions, such as:

- How many immigrants enter each country from a given port city?
- What are the port city demographics, and is there any relationship to the country of origin?
- Is there any connection between the average temperature of the country of origin and the average temperature of the port city of entry?
- What is the busiest time of year or month for immigration in certain areas?

## **Data Source Analysis**

### I94 Immigration Data

The data for this project is sourced from the U.S. National Tourism and Trade Office, and a data dictionary is available in the workspace. The data is stored as SAS7BDAT files, which are binary encoded datasets used for advanced analytics, data management, and more. The immigration data is partitioned into monthly SAS files, each around 300 to 700 MB in size, representing 12 months of data for the year 2016. The project includes a data dictionary for the immigration data, which provides descriptions of the various fields and lists the port and country codes used in table format. The port and country codes were extracted into separate CSV files to be used as a lookup when extracting the immigration data. The SAS format can be easily read with pandas in Python or Apache Spark.
