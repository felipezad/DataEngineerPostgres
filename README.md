# ETL for Music Library

## Sparkify Database Overview

The Sparkfy database project contains data about music, artists and customers.

This project has the purpose of
    Extract, transform and load data (ETL) from Music record Json files with Python and
    demonstrain ETL capability with the language.
    
In this project, you are going to extract data from two database files, log_data and song_data.

The log_data contains all the information about the customers and its music tastes and time played.

The song_data contains all the information about the song and it's artist.


## Database Information

The database contains 5 tables


| Tables        | Description       
| ------------- |-------------|
| songplays     | data about many time a song was played by an user | 
| users         | data about the user profile, gender etc.      |  
| songs         | data about song name, artist id      |  
| artists       | data about artist name       |  
| time          | data about the about the next song was played     |   

## Database Schema

```python

user_table_create = ("""
CREATE TABLE IF NOT EXISTS users(
        user_id int PRIMARY KEY,
        first_name varchar, 
        last_name varchar, 
        gender varchar, 
        level varchar)
;
""")

song_table_create = ("""
CREATE TABLE IF NOT EXISTS songs(
            song_id varchar PRIMARY KEY,
            title varchar, 
            artist_id varchar not null, 
            year int, 
            duration float)
            ;
""")

artist_table_create = ("""
CREATE TABLE IF NOT EXISTS artists(
            artist_id varchar PRIMARY KEY,
            name varchar, 
            location varchar,
            latitude numeric,
            longitude numeric)
            ;
""")

time_table_create = ("""
CREATE TABLE IF NOT EXISTS time(
            time_id serial PRIMARY key,
            start_time bigint not null,
            hour int,
            day int,
            week int, 
            month int,
            year int, 
            weekday int)
            ;
""")

songplay_table_create =  ("""
CREATE TABLE IF NOT EXISTS songplays(
            songplays_id serial primary key,
            start_time bigint NOT NULL , 
            user_id int NOT NULL, 
            level varchar, 
            song_id varchar NOT NULL,
            artist_id varchar NOT NULL,
            session_id int, 
            location varchar,
            user_agent varchar)
            ;
""")


```

## Instructions 

To run any python code use the __following command__ 

> !python {file_name}.py

for example: !python create_tables.py

The project is structured based in 3 files

1. create_tables.py
    -  This is first python code that should be run, it drops existing tables and create the tables.
         When you run this script the console will print out the resulting queries as sucessful program 
    ![result_query](screenshots/pic1.png)
    
2. sql_queries.py
    -     It is not necessary to run this python program, it only creates the queries necessary to create , insert and delete thing inside our project
    
    This files is imported inside the other files.
3. elt.py
    -  This is our ETL code (extract, transform, load), this file is responsible to extract data from the JSON files in the data folder it alsos handle all the SQL cursos statements and code.
         you can check your inserts result in the __etl.ipynb__ file and run the jupyter notebook
