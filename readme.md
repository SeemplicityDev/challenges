# Data Engineering Challenge: UK Property Price Analysis Microservice (Python or Java)

This challenge assesses your skills in building and deploying data processing pipelines with a focus on performance optimization. The task involves creating two microservices written in Python or Java to analyze UK property price data.

## Data Source
*   We will be using the UK Property Price dataset ([https://www.gov.uk/government/collections/uk-house-price-index-reports](https://www.gov.uk/government/collections/uk-house-price-index-reports)), specifically the 2023 data available for download at: [http://prod.publicdata.landregistry.gov.uk.s3-website-eu-west-1.amazonaws.com/pp-2023.csv](http://prod.publicdata.landregistry.gov.uk.s3-website-eu-west-1.amazonaws.com/pp-2023.csv)
*   A description of the column headers in this dataset can be found here: [https://www.gov.uk/guidance/about-the-price-paid-data](https://www.gov.uk/guidance/about-the-price-paid-data)
    
## Microservice 1: Data Ingestion
This microservice will be responsible for downloading, processing, and storing property data.
### Functionality
1. Accepts a file URL as input (similar to the provided 2023 data URL). Note that the data received can be for any year, not limited to 2023.  
1. Downloads the data from the provided URL.
1. **Pre-processes the data:** You can implement data cleaning or transformation steps as needed to ensure data quality before storage.  
1. **Stores the data:**
    *   Choose a durable storage solution like a relational database, columnar database or a document store based on your design decisions.    
    *   Consider techniques like data partitioning or indexing for optimized querying in Microservice 2.

## Microservice 2: Property Price Analysis
This microservice will analyze the ingested property data based on user-provided filters.
### Functionality
1. Accepts a set of optional filters as input:   
    *   starting\_year (integer)   
    *   ending\_year (integer) 
    *   county (string) 
    *   town (string)         
    *   street (string)           
1. Calculate and return the average property price and the total number of properties matching the filters.      
### Evaluation
The performance of this service will be measured based on two key factors:   
*   Latency: How quickly the service can respond to a query with the requested analysis results.      
*   Freshness: The time it takes for newly ingested data (through Microservice 1) to be reflected in the analysis results returned by Microservice 2. 

## Submission
*   Explain your design choices.
*   Provide code for both microservices in your chosen language (Python or Java) showcasing your functionalities and data storage/access approach.
*   If your solution involves additional files or scripts (e.g., configuration files, shell scripts, Dockerfiles), please include them in your submission.

## License
The dataset contains HM Land Registry data © Crown copyright and database right 2021. This data is licensed under the Open Government Licence v3.0.
