## Data Engineer Nanodegree 
# Project: Data Modeling with Postgres
*Author: Katarzyna Pranke 
[Linkedin](https://www.linkedin.com/in/kpranke/) [GitHub](https://github.com/kpranke) 

This is the first project of the Data Engineer Nanodegree at Udacity.

The aim of this task is to put into practise knowledge on data modeling with Postgres and building an ETL pipeline using Python.

## Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

## Project Description
In this project, you'll apply what you've learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project, you will need to define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

## Datasets
There are two datasets provided for the project: **Song Dataset** and **Log Dataset**

## Database Schema
For the database a star schema is being used, with one fact table (*songplays*) and four dimension tables (*users*, *artists*, *songs* and *time*). The primary keys of dimension tables are foreign keys in the fact table.

### Start Schema 

### Data Description
#### Fact table:
**songplays**
- songplay_id **PK** (ID of a song play)
- start_time **FK** (timestamp indicating start of the activity)
- user_id **FK** (user's ID)
- level (user's level: free, paid)
- song_id **FK** (played song's ID) 
- artist_id **FK** (played song's author's ID)
- session_id **FK** (session's ID)
- location (user's location)
- user_agent (agent, e.g. a browser, used by a user to access Sparkify)

#### Dimension tables:
**users**

 - user_id **PK** (user's ID)
 - first_name (user's first name)
 - last_name (user's last name)
 - gender (user's gender: 'F' or 'M')
 - level (user's level: 'paid' or 'free' )
 
**artists**
 - artist_id **PK** (artist's ID)
 - name (artist's name)
 - location (artist's location: city and state)
 - latitude (latitude of artist's location)
 - longitude (longitude of artist's location) 

**songs**

 - song_id **PK** (song's ID)
 - title (song's title)
 - artist_id (ID of the artist performing the song)
 - year (year of release)
 - duration (song duration in ms)

**time**

 - start_time **PK** (timestamp)
 - hour (hour subtracted from timestamp)
 - day (day subtracted from timestamp)
 - week (week subtracted from timestamp)
 - month (month subtracted from timestamp)
 - year (year subtracted from timestamp)
 - weekday (weekday subtracted from timestamp)

## Project's folder and files structure

The project folder contains the following items:
- *data* folder in which *log_data* and *song_data* folders can be found. This is where all the data in JSON format resides. 
- *README.md* - the currently open file;  includes a summary of the project, how to run the Python scripts, and an explanation of the files in the repository
- *sql_queries.py* - contains SQL queries
- *create_tables.py* - connects to the Sparkify database, drops any tables if they exist, and creates the tables; used before running the ETL code
- *test.ipynb* - allows to test if the tables were correctly created
- *etl.ipynb* - the script connects to the Sparkify database, extracts and processes one file from each: the log_data and song_data, and loads data into the five tables
- *etl.py* - the script connects to the Sparkify database, extracts and processes the log_data and song_data, and loads data into the five tables

## Step by step instructions

