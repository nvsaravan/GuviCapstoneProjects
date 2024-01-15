Guvi YouTube Data Harvesting and Warehousing

Overview : This project is designed to collect data from YouTube channels using the YouTube API, store the data in both MongoDB and MySQL databases, and provide a user interface for data visualization and interaction using Streamlit.

Prerequisites : 
- Python 3.x
- MongoDB
- MySQL

Importing necessary libraries
  import pandas as pd
  from datetime import datetime
  import mysql.connector
  import pymongo as pm
  import streamlit as st
  from googleapiclient.discovery import build
  from pymongo import MongoClient
  from datetime import datetime

  Connect to YouTube AP- API Key Connection
  
The provided code defines a function named Api_connect() that connects to the YouTube Data API v3

Api_connect() Function:This function is designed to establish a connection to the YouTube Data API v3. It uses the build function from the googleapiclient.discovery module to create a resource for interacting with the API. 
The api_service_name is set to "youtube," and the api_version is set to "v3," indicating the version of the YouTube Data API.The developerKey parameter is set to the API key (Api_Id) for authentication.

API Key (Api_Id):The Api_Id variable contains the API key, which is required for authentication when making requests to the YouTube Data API. In a real-world scenario, 
it's crucial to keep API keys secure and not expose them in public code repositories.
Youtube Object:The youtube variable is assigned the result of calling the Api_connect() function, representing a connection to the YouTube Data API v3.

Function to get channel information, videos IDs, video informations,playlist informations and Comment informations
Functionality:-
    Api_connect: Connects to the YouTube API using the API key.
    get_channel_info: Retrieves channel information.
    get_videos_ids: Retrieves video IDs from a channel.
    get_video_info: Retrieves detailed information about videos.
    get_comment_info: Retrieves comments on videos.
    get_playlist_details: Retrieves details about playlists.
    channel_details: Inserts data into MongoDB based on channel ID.
    tables: Sets up MySQL tables for channels, playlists, videos, and comments.
    show_channels_table: Displays the channel details table using Streamlit.
    show_playlist_table: Displays the playlist details table using Streamlit.
    show_video_table: Displays the video details table using Streamlit.
    show_comment_table: Displays the comment details table using Streamlit.

Connect to MongoDB and sql
connect_mongodb:- This function is designed to establish a connection to a MongoDB database. It uses the pymongo library (pm is used as an alias) to connect to the MongoDB server running on localhost at port 27017. 
The connection string "mongodb://localhost:27017/" specifies the server address and port.

connect_mysql:- This function is designed to establish a connection to a MySQL database. It uses the mysql.connector library to connect to the MySQL server. 
The parameters for the connection include the host (server address), user (username), password, and database (the specific database to connect to, in this case, "Guvi_Youtube_data").

Store data in a MongoDB and, Migrate data to a SQL data warehouse

Table creation for channels, playlists, videos, comments

SQL Queries: The script includes SQL queries to answer specific questions about the data stored in MySQL. Questions include:
    Names of all videos and their corresponding channels.
    Channels with the most number of videos and the count of videos.
    Top 10 most viewed videos and their respective channels.
    Number of comments on each video and their corresponding video names.
    Videos with the highest number of likes and their corresponding channel names.
    Total number of likes and dislikes for each video and their corresponding video names.
    Total number of views for each channel and their corresponding channel names.
    Names of channels that have published videos in the year 2022.
    Average duration of all videos in each channel.
    Videos with the highest number of comments and their corresponding channel names.

Display data in the Streamlit app - Streamlit page creation - Access the Streamlit dashboard by visiting the provided URL in the terminal after running the script.

Overall, above approach involves building a simple UI with Streamlit, retrieving data from the YouTube API, storing it in a MongoDB data lake, migrating it to a SQL data warehouse, 
querying the data warehouse with SQL, and displaying the data in the Streamlit app.

Author : Saravanan Varadharajan
