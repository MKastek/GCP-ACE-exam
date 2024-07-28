## BigQuery  
- BigQuery is a managed, petabyte scale data warehouse, which uses SQL, but it is not transactional database.  

### Bigquery dry run
BigQuery provides various methods to estimate cost:  
- Use the query dry run option to estimate costs before running a query using the on-demand pricing model.  
- Calculate the number of bytes processed by various types of query.  
- Get the monthly cost based on projected usage by using the Google Cloud Pricing Calculator.

A dry run in BigQuery provides the following information:  
- estimate of charges in on-demand mode  
- validation of your query  
- approximate size and complexity of your query in capacity mode

### How to use dry run - you want to find out how much it will cost to run the query  
Use the command line to run a dry run query to estimate the number of bytes read. Then convert that bytes estimate to dollars using the Pricing Calculator. 
