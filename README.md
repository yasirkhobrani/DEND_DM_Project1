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
song_id	title	artist_id	year	duration
SOMZWCG12A8C13C480	I Didn't Mean To	ARD7TVE1187B99BFB1	0	218.93179
SOUDSGM12AC9618304	Insatiable (Instrumental Version)	ARNTLGG11E2835DDB9	0	266.39628
SOIAZJW12AB01853F1	Pink World	AR8ZCNI1187B9A069B	1984	269.81832
SOHKNRJ12A6701D1F8	Drop of Rain	AR10USD1187B99F3F1	0	189.57016
SOCIWDW12A8C13D406	Soul Deep	ARMJAGH1187FB546F3	1969	148.03546

### results of Artists table:
artist_id	name	location	latitude	longitude
ARD7TVE1187B99BFB1	Casual	California - LA	nan	nan
ARNTLGG11E2835DDB9	Clp		nan	nan
AR8ZCNI1187B9A069B	Planet P Project		nan	nan
AR10USD1187B99F3F1	Tweeterfriendly Music	Burlington, Ontario, Canada	nan	nan
ARMJAGH1187FB546F3	The Box Tops	Memphis, TN	35.14968	-90.04892
### results of Users table:
user_id	first_name	last_name	gender	level
57	Katherine	Gay	F	free
30	Avery	Watkins	F	paid
73	Jacob	Klein	M	paid
86	Aiden	Hess	M	free
24	Layla	Griffin	F	paid
### results of Time table:
start_time	hour	day	week	month	year	weekday
1543537327796	0	30	48	11	2018	4
1543540121796	1	30	48	11	2018	4
1543540368796	1	30	48	11	2018	4
1543540625796	1	30	48	11	2018	4
1543540856796	1	30	48	11	2018	4

### results of SongPlays table:
songplay_id	start_time	user_id	level	song_id	artist_id	session_id	location	user_agent
1	1543537327796	91	free	None	None	829	Dallas-Fort Worth-Arlington, TX	Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; WOW64; Trident/6.0)
2	1543540121796	73	paid	None	None	1049	Tampa-St. Petersburg-Clearwater, FL	"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit/537.78.2 (KHTML, like Gecko) Version/7.0.6 Safari/537.78.2"
3	1543540368796	73	paid	None	None	1049	Tampa-St. Petersburg-Clearwater, FL	"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit/537.78.2 (KHTML, like Gecko) Version/7.0.6 Safari/537.78.2"
4	1543540625796	73	paid	None	None	1049	Tampa-St. Petersburg-Clearwater, FL	"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit/537.78.2 (KHTML, like Gecko) Version/7.0.6 Safari/537.78.2"
5	1543540856796	73	paid	None	None	1049	Tampa-St. Petersburg-Clearwater, FL	"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit/537.78.2 (KHTML, like Gecko) Version/7.0.6 Safari/537.78.2"

## How to run:
1. Run the terminal.
2. Execute create_tables.py
3. Execute etl.py
4. Once etl.py processing is completed run test.ipynb to make sure all data added successfully.

### Other ways I used
1. To run create_tables.py without using terminal I created run_main.ipynb -> it imports create_tables and runs main function.
2. To run etl.py without using terminal I included that at the end of etl.ipynb file
