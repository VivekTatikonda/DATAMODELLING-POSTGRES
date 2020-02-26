### Purpose
The purpose is this database helps in keeping the keeping the files in a systematic manner and managing large ampunt of info in small time. From this the Analytics team can run reports and perform analysis for growth of the company.

### Datasets
1. Song Dataset - Complete details and metadata about the song.
2. Log Dataset - User activity log.

### Database Schema 
we are using Star Schema to model dividing them into one fact table (songplays) and dimensions(users, songs, artists etc) so that it is structured.

### Fact Table:
songplays table which contains the metadata of the complete information about each user activity. Dimension table are connected to this fact table.

### Dimension Tables:
users,songs,artists,time are dimension tables. These tables will be having detailed info of fact table data.

### ETL Pipleline
Build an ETL pipeline that collects data from json log files and then inserts data into respective tables. etl.py file consists of entire pipeline.

#### Explaination about each Files

### songplay_table_create
Used for creating songplay table. This is the fact table. songplay_id is assigned as the primary key to uniquely identify the row. All the other columns are pulled from  will have duplicate values which voialtes primary key constarint.
### user_table_create
Used for creating user table. This is a dimension table. first_name, last_name cannot be a primary has two people can have same first or last name. So, user_id is assigned as the primary key.
### song_table_create
Used for creating song table. This is a dimension table. Multiple artist_id can be present has an artist can have several songs. song_id is assigned as the primary key.
### artist_table_create
Used for creating artist table. This is a dimension table. latitude and longitude can have NONE values which voailtes primary key.So, artist_id is assigned as the primary key.
### time_table_create
Used for creating time table. This is a dimension table. start_time is assigned as the primary key as all the other columns can have repeatitive data.

### songplay_table_drop
For dropping Songplay table.
### user_table_drop
For dropping user table.
### song_table_drop 
For dropping song table.
### artist_table_drop 
For dropping artist table.
### time_table_drop
For dropping time table.

### songplay_table_insert
A query is written which pulls the arists and user id's from user and artist tables by matching the title, name, duration from log files and other column data are pulled from log_data and inserted by executing the insert statement.
### user_table_insert
Data is extracted from log data files and inserted by executing the insert statement 
### song_table_insert
Data is extracted from song data files and inserted by executing the insert statement
### artist_table_insert
Data is extracted from song data files and inserted by executing the insert statement
### time_table_insert
Data is extracted from log data files and inserted by executing the insert statement

There are 7 files:

data: This folder contains log_data and song_data subfloders which intern has individual datasets.
etl.ipynb: jupyter notebook which I used to create the skeleton for the pipeline. It is kind of a workbook. It contains detailed instructions on the ETL process for each of the tables.
test.ipynb: This jupyter notebook tests whether the tables are created and data is inserted.
create_tables.py: A python program contains postgresql queries for creating or dropping(if already exists) the database and tables.
etl.py: This script contains the complete ETL pipeline for the project.
Readme.md: Details about the project.
sql_queries.py: This python script contains the create and insert contains for the database.

### Steps to run the project
Start running the sql_queries.py file and then create_tables for creating or dropping( if table already exists) tables. 
Then Run etl.py script to run the etl pipeline and extract data from the log and song datasets and insert them into the facts and dimension table.