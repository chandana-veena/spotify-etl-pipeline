# Spotify ETL Pipeline
In this project, I have built an ETL (Extract, Transform, Load) pipeline using Spotify API on AWS. This pipeline will retrieve data from Spotify API, transform this data to desired format and then load this data into AWS datastore.
## Dataset/API:
Here I have worked on Spotify's Top 50 Global Songs Playlist.
API of Playlist : [Top Global Songs](https://open.spotify.com/playlist/37i9dQZEVXbNG2KDcFcKOF?si=1333723a6eff4b7f)

Spotipy Python library : [Spotipy](https://spotipy.readthedocs.io/en/latest/)

## Services Used:
-**S3 (Simple Storage Service)**: Used to store the retrieved data from the API.

-**AWS LAMBDA**: Used to write functions to retrive data from API and to transform the data.

-**Cloud Watch**: Created a trigger using this AWS service to load the data into S3 every hour.

-**Glue Crawler**: Extracted the Schema for tables from the dataframes created using AWS lambda.

-**Amazon Athena**: Used to perform various SQL queries to analyze the data present in Glue Data Catalog and S3 buckets.

## Execution Flow:
Extract data from Spotify API -> Lambda Trigger (Every 1 hours) -> Run extract code -> Store raw data in S3 bucket -> Trigger Transform Function -> Run code of tranforing data and load it in S3 bucket -> Extract the schema and tables using Crawler -> Query the data using Athena
