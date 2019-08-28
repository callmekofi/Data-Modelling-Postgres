INTRODUCTION:
The goal of this project is to create a database using PostgreSql to analise songs and user activity data collected by Sparkify. This makes use of models to design and create tables to optimise queries on datasets made available by Sparkify as log data and song data in JSON formats. At the end of this project, the Sparkify analysis team is able to retrieve results based on queries on what songs its users are listening to. 

STEPS:
Files made available to execute this project are: 
- create_tables.py: This file makes a connection to the dB, executes create and drop table queries and should be executed prior to running other scripts.
- sql_queries.py: This file is made up of "create" and "insert into" facts and dim table queries to the dB. 
- etl.py: This file contains all processes for an ETL procedure for all fact and dim tables considered.
- test.ipynb: This file contains sample queries for testing on our dB.

IMPORTANT PROCESSES:
- Create tables in sql_queries.py
- Build ETL processes and Pipelines in etl.py
- Test queries on dB.

NOTE:
ETL pipeline consists of retrieving data from files and transforming them into tables in a dB. This process starts by extracting files using python file-handling methods and pandas to read the individual files. Functions are created to iterate over the individual files in the dir and extract information from the files. The files are processed based on content and inserted into the individual tables created using sql_queries and create_table python scripts, respectively.

TABLES CREATED:
- Facts: Songplays = Made up of songplay events for the datasets given to inform business decision.
- Dim: users = Made up of users registered to the Sparkify app.
       songs = Made up of all available songs in the Sparkify music dB
     artists = Made up of all artists of the songs in the Sparkify music dB
        time = Made up of the timestamps of song plays by users of the Sparkify app.
        
NOTE:
We avoid duplication in the  songplays "FACT" table by creating "DIM" tables. As evident in the lod data files, there are several instances where data duplication occurs, as such we achieve 2NF in songs and artist tables which are JOINED based on selected fields in the "song_select" query used to insert values in songplays.
        
QUERIES:
All select, join, aggregation and known available postgres queries can be applied on the dB.
