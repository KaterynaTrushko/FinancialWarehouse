# FinencialWarehouse

FinancialWarehouse is a project I worked on to help a business manage and consolidate customer purchase data. They had transaction data stored in SQL Server, customer contact info in another table, and currency exchange rates in Excel files. To make things even more flexible, I also added an option to fetch exchange rates through an API. The goal was to bring all this scattered data together into one SQL Server database.

The main part of the project was setting up an ETL process using SSIS. I created workflows to extract data from the various sources, transform it where needed (like converting currencies or cleaning up duplicates), and load it into the SQL Server warehouse. Along the way, I handled common issues like data type mismatches, missing values, and lookup errors. Debugging was a big part of the process—especially when working with different file formats like CSVs and Excel.

For currency conversion, I used exchange rates stored in an Excel file and also built a script to call an API for real-time updates. The SSIS package included derived columns to calculate converted amounts and lookups to match the correct exchange rates. I also had to deal with situations where there were no matches, using multi-cast and split techniques to handle those gracefully.

Once the ETL was ready, I deployed the package to SQL Server and set up the SSISDB catalog for managing it. I also scheduled jobs using SQL Server Agent so the ETL runs automatically on a schedule. To make the deployment more flexible, I added environment parameters for connection strings and other settings.

This project brought together financial transactions, customer details, and supplier data, making it all accessible in one place. It was a mix of data engineering and problem-solving, with a lot of time spent refining workflows and handling edge cases. Overall, it was a great learning experience in working with ETL processes, SQL Server, and integrating different data sources.
