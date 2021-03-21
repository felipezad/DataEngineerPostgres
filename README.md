# ETL for Music Library

## Sparkify Database

<p>
    Extract, transform and load data from Music record Json files
</p>

## Instructions 

To run any python code use the __following command__ 

> !python {file_name}.py

for example: !python create_tables.py

The project is structured based in 3 files

1. create_tables.py
    -  This is first python code that should be run, it drops existing tables and create the tables.
    <p> When you run this script the console will print out the resulting queries as sucessful program </p>
    ![result_query](screenshots/pic1.png)
    
2. sql_queries.py
    -     It is not necessary to run this python program, it only creates the queries necessary to create , insert and delete thing inside our project
    
    This files is imported inside the other files.
3. elt.py
    -  This is our ETL code (extract, transform, load), this file is responsible to extract data from the JSON files in the data folder it alsos handle all the SQL cursos statements and code.
    <p> you can check your inserts result in the __etl.ipynb__ file and run the jupyter notebook <P>
