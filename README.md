# Case study: How does a bike-share navigate speedy success?
Google Data Analytics Capstone

This Python script performs data preprocessing on Cyclistic's bike-sharing data, preparing it for analysis in Tableau to answer the question: **How do annual members and casual riders use Cyclistic bikes differently?**

The script focuses on cleaning and transforming the raw data into a format suitable for analysis in Tableau. The steps involved are as follows:

1. **Import Libraries:** Imports necessary libraries such as pandas, os, and glob for data manipulation.
2. **Load Data:** Loads all CSV files from the Cyclistic dataset, located in a specified directory, and combines them into a single pandas DataFrame.
3. **Remove Duplicates:** Removes duplicate rows from the DataFrame based on the ride ID (ride_id) to ensure data integrity.
4. **Convert Data Types:** Converts the 'started_at' and 'ended_at' columns to datetime data type to enable time-based calculations for ride duration and analysis.
5. **Calculate Ride Length:** Calculates the duration of each ride by subtracting the start time from the end time and stores it in a new column 'ride_length', a key metric for comparing usage patterns.
6. **Filter Data:** Removes rides with a duration of less than 60 seconds, filtering out potentially erroneous or irrelevant data points.
7. **Create Day of Week:** Adds a new column 'day_of_week' that contains the day of the week of the ride, enabling analysis of usage patterns by day.
8. **Clean DataFrame:** Removes unnecessary columns such as 'new_started_at', 'new_ended_at', and 'ride_length' to streamline the dataset for Tableau.
9. **Save Data:** Saves the resulting DataFrame to a new CSV file named 'full_data.csv', ready for import and analysis in Tableau.


**Objective:**

The objective of this script is to prepare the Cyclistic data for analysis in Tableau to understand how annual members and casual riders use Cyclistic bikes differently. This involves cleaning, transforming, and organizing the data to facilitate exploration and visualization in Tableau. The resulting file, 'full_data.csv', will contain clean and structured data ready for import into Tableau to answer the key analysis question.


## Graphs and analyses
### Graphs
1. **Total Trips (Member vs. Casual)**:
   - **Members:** 63.70% (5,798,318 trips)
   - **Casual Users:** 36.30% (3,299,409 trips)
   - *Members take more trips than casual users.*
   
     ![image](https://github.com/user-attachments/assets/b0c1df96-69d7-4f5e-8918-c447987a3858)


2. **Total Hours (Member vs. Casual)**:
   - **Members:** 8,024,844 hours
   - **Casual Users:** 9,082,883 hours
   - *Despite taking fewer trips, casual users spend more total time on the service.*
  
     ![image](https://github.com/user-attachments/assets/6748fde9-a1e9-4933-b94a-89b669de947b)

      Casual users likely use the service for leisure or tourism, leading to longer rides. Members seem to use it for shorter, more frequent trips, such as daily commutes.



3. **Average Ride Time**:
   - **Casual Users:** Approximately 25 minutes
   - **Members:** Approximately 15 minutes
   - *Casual users have a longer average ride time compared to members.*
   
     ![image](https://github.com/user-attachments/assets/d419a802-97cb-40e7-8637-4c4f7285acbf)

     Casual users may use the service for relaxed, exploratory rides, while members prioritize quick and practical trips.



4. **Types of Bikes**:
   - **Electric Bikes:** Approximately 2,800,000 (members) and 2,600,000 (casual users)
   - **Classic Bikes:** Approximately 2,600,000 (members) and 2,400,000 (casual users)
   - **Electric Scooters:** Very little use by both groups
   - *Both groups use electric bikes more than classic bikes, with members slightly preferring them.*
   
     ![image](https://github.com/user-attachments/assets/8ea16913-8873-48bd-a50f-5e27c809c0cd)


5. **Heat Map by Hour and Day of the Week (Member)**:
   - Peak usage during weekdays, especially between 7 AM to 9 AM and 4 PM to 6 PM.
   - Reduced usage on weekends.
   
     ![image](https://github.com/user-attachments/assets/d543b106-1ae7-462e-b8d5-ef124c24ddc1)


6. **Heat Map by Hour and Day of the Week (Casual)**:
   - Peak usage during weekends, especially between 11 AM to 5 PM.
   - Reduced usage during weekdays.
   
     ![image](https://github.com/user-attachments/assets/4a6c95b1-ab73-4d5d-b9d5-50bdaf3ae375)

     Members typically use the service for work-related travel, while casual users focus on leisure or sightseeing during off-peak times.

7. **Total Rides (Monthly)**:
   - **Members:** Steady increase from February to August 2024, peaking in August.
   - **Casual Users:** Steeper increase from February to August 2024, peaking in August.
   
     ![image](https://github.com/user-attachments/assets/a1389938-e2ca-4a69-868f-9251f173b45d)


8. **Total Hours (Monthly)**:
   - **Members:** Steady increase from February to August 2024, peaking in August.
   - **Casual Users:** Steeper increase from February to August 2024, peaking in August.
   
     ![image](https://github.com/user-attachments/assets/13e5d547-8e1c-4e35-8032-70c4bcb2e9d5)

     Favorable weather during summer makes the service more appealing for outdoor activities, especially for casual users.

9. **Average Trip Duration (Minutes by Month)**:
   - **Members:** Relatively constant average ride time, with a slight dip in August.
   - **Casual Users:** Average ride time increases from February to August, peaking in August.
   
     ![image](https://github.com/user-attachments/assets/34ebb2b2-f7c7-49a4-bb09-5418be5dc1b2)

     Members have regular, goal-oriented travel patterns, while casual users’ behavior is more influenced by seasonal and weather conditions.


### Analyses
1. **Member Usage Patterns**:
   - **Frequent Short Trips**: Members might use the bike service for their daily commutes or short trips, such as going to work, running errands, or visiting nearby locations. This could explain why they take more trips but spend less time on each trip.
   - **Routine and Convenience**: Members likely have an established routine and find the service convenient for regular use, leading to consistent usage patterns during weekdays, especially during peak commute hours.

2. **Casual User Usage Patterns**:
   - **Recreational Use**: Casual users might use the service more for leisure or recreational activities rather than commuting. This could explain the longer average ride times and higher usage during weekends.
   - **Tourist Activities**: Casual users could include tourists who use the bike service to explore the city. They might spend more time on each trip to visit various attractions.

3. **Preference for Electric Bikes**:
   - **Ease and Speed**: Both members and casual users might prefer electric bikes for their ease of use and faster travel speeds, making them a popular choice for both commuting and recreational activities.

4. **Monthly Usage Trends**:
   - **Seasonal Variations**: The increase in usage from February to August could be attributed to better weather and longer daylight hours during the summer months, encouraging more people to use the bike service.
   - **Vacation Periods**: The peak in August might be due to summer vacations, when both locals and tourists are more likely to engage in outdoor activities, including using the bike service.


## Data Source:

The data used in this analysis is publicly available and sourced from Motivate International Inc. under this [license](https://ride.divvybikes.com/data-license-agreement). The data can be accessed from the following link:  https://divvy-tripdata.s3.amazonaws.com/index.html.


## Tableau complete viz:

The dashboard with all graphs is can be accessed using the link: https://public.tableau.com/views/CyclisticBikeShareAnalysis_17322844572600/CyclisticBikeShare
