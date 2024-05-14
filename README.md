# Melody_In_Clouds

### Project Overview:
Melody in Cloud is an End-to-End ETL pipeline project leveraging AWS cloud services. Real-time Spotify data is fetched using the Spotify developer API and loaded into a Snowflake database. Using Tableau, interactive dashboards are built to analyze real-time data.

### Business Problem:
A client passionate about the music industry wants to understand the industry better by collecting real-time data to find patterns in trending songs. The client aims to build a recommendation model based on this analysis.

#### Key Performance Indicators (KPIs):
- Song Popularity Trends
- Artist Popularity
- Album Release Performance
- User Engagement
- Conversion Rate
- Playlist Effectiveness

#### Machine Learning Ideas:
- Song Recommendation System
- Artist Similarity Analysis
- Predictive Modeling for Song Popularity
- Churn Prediction
- Genre Classification

#### Business Intelligence Ideas:
- Market Analysis
- Competitor Analysis
- User Segmentation
- Content Licensing Optimization
- Marketing Campaign Effectiveness

#### Objectives:
The client aims to update a playlist throughout the year on a weekly basis to collect real-time data on top global songs on Spotify. The collected data will be used to build insights and data-driven solutions over the course of one year.


### Technologies Used:

- AWS Lambda
- AWS CloudWatch
- AWS S3
- Snowflake
- Tableau

### Technical Architecture of ETL Pipeline:

![Screenshot 2024-05-14 at 02 51 00](https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/820b888f-d31c-4e2f-ae4b-9e2172b9e722)

### Data Extraction:

Utilizing AWS Lambda and the Spotify API, raw data is extracted in JSON format and stored in an AWS S3 Bucket.
Data extraction Lambda functions are automated using AWS CloudWatch on a weekly basis.


<img width="500" alt="Lamda_Data Extraction" src="https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/2f0597ce-ed80-40aa-a295-b7a540607402">



<img width="500" alt="Lambda_DataExtraction_1" src="https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/73589ae0-4b01-4d76-b083-14edd1c43451">


### Data Transformation:

<img width="500" alt="Lambda_DataTransformation" src="https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/ad0f8420-2379-40ed-9fc5-90450b6002ea">


Extracted raw data from the S3 bucket is transformed to make it suitable for analysis.
A Lambda function is triggered to transform the raw data into three separate datasets: Album Data, Song Data, and Artist Data.

<img width="500" alt="Lambda_DataTransformation_1" src="https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/5fd3176b-0550-4d16-b8b9-63b23009e474">



### Data Loading:

Structured data is stored in S3 buckets in three folders: Album Data, Song Data, and Artist Data.
Snowflake stages are used to load data from S3 into Snowflake.

<img width="500" alt="SnowflakeSQL script" src="https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/4c80e9a5-72c0-4615-b3de-22c6cd16d4f0">


**Album_df Data Dictionary**


| Column Name | Description                                | Data Type |
|-------------|--------------------------------------------|-----------|
| album_id    | Unique identifier for the album            | String    |
| album_name  | Name of the album                          | String    |
| release_date| Release date of the album                  | Date      |
| total_tracks| Total number of tracks in the album        | Integer   |
| album_urls  | URL to access the album on Spotify         | String    |

**Song_df Data Dictionary**


| Column Name    | Description                                     | Data Type |
|----------------|-------------------------------------------------|-----------|
| song_id        | Unique identifier for the song                  | String    |
| song_name      | Name of the song                                | String    |
| song_duration  | Duration of the song in milliseconds            | Integer   |
| song_url       | URL to access the song on Spotify               | String    |
| song_popularity| Popularity score of the song                     | Integer   |
| song_added     | Date when the song was added                    | Date      |
| album_id       | Unique identifier for the album                  | String    |
| artist_id      | Unique identifier for the artist                 | String    |



**Artist_df Data Dictionary**


| Column Name  | Description                                  | Data Type |
|--------------|----------------------------------------------|-----------|
| Artist_id    | Unique identifier for the artist             | String    |
| Name         | Name of the artist                           | String    |
| external_url | URL to access the artist on Spotify          | String    |




### Data Analysis:



Tableau is used for further data analysis.
Data is pulled into Tableau using the Snowflake connector.
Song Data acts as the fact table, while Album Data and Artist Data serve as dimension tables.
Merged datasets are used to create insightful dashboards.

<img width="649" alt="Tableau_datamerge" src="https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/3777e3e4-b951-4df1-b920-669f4e85e9b6">


### Credits:
A big thank you to Darshil Parmar for designing this wonderful course.

https://courses.datavidhya.com/cohort/BpfGFSahpQ?module-id=64f82d541e61cc4beeb0119f&lesson-id=64f8327b6133753c810c6143

<img width="700" alt="Screenshot 2024-05-14 at 10 26 36" src="https://github.com/NikhilSalv/Melody_In_Clouds/assets/74225565/2ddf4070-899d-4995-b736-04c60cb80fde">


This structured and detailed documentation provides a clear overview of the project, its objectives, technical architecture, data dictionary, and data analysis process. It also includes placeholders for inserting screenshots of the interactive dashboards in Tableau.






