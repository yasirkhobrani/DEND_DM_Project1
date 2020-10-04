# Sparkify database and ETL pipeline
## About Sparkify
Sparkify is a music startup, they store songs data and their logs in separate JSON files, analyzing those data becomes diffcult, in order to handle those large data, they need to process and extract data using ETL pipelines, then store it in the destination database.

## Database Schema
Sparkify destination database will have the following tables:
* Songplay (The fact table)
* Songs (Dimensional table from song_data json files)
* Artists (Dimensional table from song_data json files)
* Users (Dimensional table from log_data json files)
* Time (Dimensional table from Timestamp (ts) Column)

## ETL Pipline
Extract Transform and Load data:
* Extracting data from json files (source data)
* Store song data separately into 2 tables: Songs, Artists
* Store log data separately into 2 tables: Users, Time

## Results:
### results of Songs table:
![Songs](https://imgur.com/iB2WHoT.png)
### results of Artists table:
![Artists](https://imgur.com/RF25pVY.png)
### results of Users table:
![Users](https://imgur.com/jFwhwua.png)
### results of Time table:
![Time](https://imgur.com/I2DXBBu.png)
### results of SongPlays table:
![songPlays](https://imgur.com/Mvc6nLI.png)
## How to run:
1. Run the terminal.
2. Execute create_tables.py
3. Execute etl.py
4. Once etl.py processing is completed run test.ipynb to make sure all data added successfully.

### Other ways I used
1. To run create_tables.py without using terminal I created run_main.ipynb -> it imports create_tables and runs main function.
2. To run etl.py without using terminal I included that at the end of etl.ipynb file
