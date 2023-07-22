# Google-Capstone-Project: Case Study_1
Course: [Google Data Analytics Certification](https://www.coursera.org/learn/google-data-analytics-capstone)
## Introduction:
To complete the Google Data Analytics Course and to acheive my Professionial Certificate, I have completed a Capstone Project highlighting the technical skills (SQL & Tableau) that I felt comfortable. The case study I selectef for my Capstone Project is the 'Cyclistic Case Study'. In order to answer the key business questions, I have followed the steps of the data analysis process: Ask, Prepare, Process, Analyze, Share, and Act.
### Quick Links: 
Data Source: [divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html)

SQL Queries:  
[01. Data Combining](https://github.com/Avi6584/Google-Capstone-Project/blob/main/01.%20Data%20Combining.sql)  
[02. Data Exploration](https://github.com/Avi6584/Google-Capstone-Project/blob/main/02.%20Data%20Exploration.sql)  
[03. Data Cleaning](https://github.com/Avi6584/Google-Capstone-Project/blob/main/03.%20Data%20Cleaning.sql)  
[04. Data Analysis](https://github.com/Avi6584/Google-Capstone-Project/blob/main/04.%20Data%20Analysis.sql)  

Data Visualizations: [Tableau](https://public.tableau.com/app/profile/avinash.matla/viz/Cyclist-Data_Casestudy/TripsatStartStations?publish=yes)
## Background
### Cyclistic
A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use them to commute to work each day.   
  
Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.  
  
Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno (the director of marketing and my manager) believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a very good chance to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.  

Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the marketing analyst team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.  
## Ask
### Business Task
Devise marketing strategies to convert casual riders to members.
### Analysis Questions
Three questions will guide the future marketing program:  
1. How do annual members and casual riders use Cyclistic bikes differently?  
2. Why would casual riders buy Cyclistic annual memberships?  
3. How can Cyclistic use digital media to influence casual riders to become members?  

Moreno has assigned me the first question to answer: How do annual members and casual riders use Cyclistic bikes differently?
## Prepare
### Data Source
I have used cyclistic historical trip data to analyze and identify trends from Jan 2022 to Dec 2022 which can be downloaded from [divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html). The data has been made available by Motivate International Inc. under this [license](https://www.divvybikes.com/data-license-agreement).  
This is public data that can be used to explore how different customer types are using Cyclistic bikes. But note that data-privacy issues prohibit from using riders’ personally identifiable information. This means that we won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.
### Data Organization
There are 12 files with naming convention of YYYYMM-divvy-tripdata and each file includes information for one month, such as the ride id, bike type, start time, end time, start station, end station, start location, end location, and whether the rider is a member or not. The corresponding column names are ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng, end_lat, end_lng and member_casual.
## Process
BigQuery is used to combine the multiple tables into one dataset and also to clean raw data.

Reason:  
A worksheet can only have 1,048,576 rows in Microsoft Excel because of its inability to manage large amounts of data. Because the Cyclistic dataset has more than 5.6 million rows, it is essential to use a platform like BigQuery that supports huge volumes of data.
### Combining the Data
SQL Query: [Data Combining](https://github.com/Avi6584/Google-Capstone-Project/blob/main/01.%20Data%20Combining.sql)  
12 csv files are uploaded as tables in the dataset '2022_tripdata'. Another table named "combined_data" is created, containing 5,667,717 rows of data for the year 2022.
### Data Exploration
SQL Query: [Data Exploration](https://github.com/Avi6584/Google-Capstone-Project/blob/main/02.%20Data%20Exploration.sql)  
Before cleaning the data, I familiarised myself with the data to find the inconsistencies.
### Data Cleaning
SQL Query: [Data Cleaning](https://github.com/Avi6584/Google-Capstone-Project/blob/main/03.%20Data%20Cleaning.sql)  
1. Rows with missing values are deleted.  
2. 3 more columns such as, ride_length for duration of the trip, day_of_week and month are added.  
3. Trips with duration less than a minute and longer than a day are deleted.
4. Total 1,375,912 rows are removed in this step.
## Analyze and Share
SQL Query: [Data Analysis](https://github.com/Avi6584/Google-Capstone-Project/blob/main/04.%20Data%20Analysis.sql)  
Data Visualization: [Tableau](https://public.tableau.com/app/profile/avinash.matla/viz/Cyclist-Data_Casestudy/TripsatStartStations?publish=yes)

The data is stored appropriately and is now prepared for analysis. I have run queries on multiple relevant tables for the analysis and visualized them in Tableau.  
The analysis question is: How do annual members and casual riders use Cyclistic bikes differently?

First of all, member and casual riders are compared by the type of bikes they are using.

![Screenshot 2023-07-22 194412](https://github.com/Avi6584/Google-Capstone-Project/assets/89294923/03098121-6182-43d5-a0b1-72e00743e597)

The members make 59.7% of the total while remaining 40.3% constitutes casual riders. Each bike type chart shows percentage from the total. Most used bike is classic bike followed by the electric bike. Docked bikes are used the least by only casual riders.
  
Next the number of trips distributed by the months, days of the week and hours of the day are examined.

![Screenshot 2023-07-22 201954](https://github.com/Avi6584/Google-Capstone-Project/assets/89294923/c3d18800-3106-4b7c-b44b-6a3730868d1b)

__Months:__ When it comes to monthly trips, both casual and members exhibit comparable behavior, with more trips in the spring and summer and fewer in the winter. The gap between casuals and members is closest in the month of july in summmer.   
__Days of Week:__ When the days of the week are compared, it is discovered that casual riders make more journeys on the weekends while members show a decline over the weekend in contrast to the other days of the week.  
__Hours of the Day:__ The members shows 2 peaks throughout the day in terms of number of trips. One is early in the morning at around 6 am to 8 am and other is in the evening at around 4 pm to 8 pm while number of trips for casual riders increase consistently over the day till evening and then decrease afterwards.  
  
We can infer from the previous observations that member may be using bikes for commuting to and from the work in the week days while casual riders are using bikes throughout the day, more frequently over the weekends for leisure purposes. Both are most active in summer and spring.  
  
Ride duration of the trips are compared to find the differences in the behavior of casual and member riders.

![Screenshot 2023-07-22 194809](https://github.com/Avi6584/Google-Capstone-Project/assets/89294923/25f8a20f-961e-47b2-a8b5-a5798cf09910)

Take note that casual riders tend to cycle longer than members do on average. The length of the average journey for members doesn't change throughout the year, week, or day. However, there are variations in how long casual riders cycle. In the spring and summer, on weekends, and from 10 am to 2 pm during the day, they travel greater distances. Between five and eight in the morning, they have brief trips.
  
These findings lead to the conclusion that casual commuters travel longer (approximately 2x more) but less frequently than members. They make longer journeys on weekends and during the day outside of commuting hours and in spring and summer season, so they might be doing so for recreation purposes.   
  
To further understand the differences in casual and member riders, locations of starting and ending stations can be analysed. Stations with the most trips are considered using filters to draw out the following conclusions.

![Screenshot 2023-07-22 194906](https://github.com/Avi6584/Google-Capstone-Project/assets/89294923/148dc674-7093-429b-b067-035dfbdb615e)

Casual riders have frequently started their trips from the stations in vicinity of museums, parks, beach, harbor points and aquarium while members have begun their journeys from stations close to universities, residential areas, restaurants, hospitals, grocery stores, theatre, schools, banks, factories, train stations, parks and plazas.

