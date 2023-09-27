Author:
This database contains information about what songs users are listening to. The startup Sparkify will be able to use this database to respond to analyzes such as: "which user is the most active?", "what are the top 10 most played songs?". Such questions can guide business decisions towards more profitable paths for the company.
 \
The database schema was transformed from music table + event table to a star schema. The users, artirts and time tables were distributed with the 'all' method because they are small, so their replication in all nodes will reduce shuffling and therefore increase performance. The songplays table was distributed with the user_id column to try to distribute the same number of users in each node.

# Project Instructions

## Schema for Song Play Analysis
Using the song and event datasets, you'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.

# Fact Table
1. songplays - records in event data associated with song plays i.e. records with page NextSong: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

# Dimension Tables
2. users - users in the app: user_id, first_name, last_name, gender, level
3. songs - songs in music database: song_id, title, artist_id, year, duration
4. artists - artists in music database: artist_id, name, location, lattitude, longitude
5. time - timestamps of records in songplays broken down into specific units: start_time, hour, day, week, month, year, weekday

# Project Template
To get started with the project, go to the workspace on the next page, where you'll find the project template. You can work on your project and submit your work through this workspace. Alternatively, you can download the template files in the Resources tab in the classroom and work on this project on your local computer. \
 \
The project template includes four files:
1. create_table.py is where you'll create your fact and dimension tables for the star schema in Redshift.
2. etl.py is where you'll load data from S3 into staging tables on Redshift and then process that data into your analytics tables on Redshift.
3. sql_queries.py is where you'll define you SQL statements, which will be imported into the two other files above.
4. README.md is where you'll provide discussion on your process and decisions for this ETL pipeline.
