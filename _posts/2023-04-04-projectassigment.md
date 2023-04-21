---
title: National Highway Traffic Safety Administration (NHTSA) Analysis
layout: post
post-image: "/assets/images/pa1/pa1cover.png"
description: This is a group project assignment at Refocus Digital Academy.
tags:
- Data Analyst
- informative
- NHTSA
- SQL
---
### **Background**<br>
Imagine yourself as a data analyst for PT Refocus Consultant. Refocus Consultant is a consultancy firm that handles various data analyses, such as business, environmental, health, and government data. Refocus Consultant is also often asked to provide opinions to assist the government in making policies. Refocus Consultant helps many clients obtain important information from the data provided by the clients.

### **Job Description**<br>
You and your team in the data analytics department have a great opportunity to help the National Highway Traffic Safety Administration (NHTSA). NHTSA is one of the government departments in the United States that focuses on reducing the number of traffic accidents on highways.

Currently, NHTSA is working on new regulations that will be implemented next year. Refocus Consultant is one of the companies asked to analyze the data collected during 2021. This data is complete data on accidents that occurred during 2021.<br>

### **Data Analysis Objectives**<br>
The main objective of your study is to provide a number of recommendations on how to reduce the number of accidents on highways. To do this, you first need to identify the following data:

1. Conditions that increase the risk of accidents
2. Top 10 states where accidents occur the most
3. Average number of accident occurrences per day based on the time of day the accident occurred
4. Percentage of accidents caused by drunk drivers
5. Percentage of accidents in rural and urban areas
6. Number of accidents by day.<br>

### **ROCCC Analysis:**<br>
Reliable — The data has been made available by Refocus specifically for this project

Original — Subject to the terms and conditions of the Data License Agreement by NHTSA.

Comprehensive — Data dictionary has been provided through this [link](https://docs.google.com/spreadsheets/d/1QCyKawlHnxEQ3-kzZ_6mSHsx1_KEHLeCo8L3Iss-Y6I/edit?usp=sharing).

Current — The latest data is 2022.

Cited — All the data needed for this project can be accessed through this [link](https://drive.google.com/file/d/1wiFf1VpFRXXUz9XpHjb--6vFDoNiCVDK/view).

### **Cleaning Data**<br>
The program that we used for data cleaning is pgAdmin 4 using PostgreSQL.<br>
"Elimination & validation of data to other.<br>
This statement means that certain values in specific columns of a dataset will be eliminated or validated as "other". The specific columns and values are:

* city_name: 'NOT APPLICABLE', 'Not Reported', 'Unknown'
* land_use_name: 'Not Reported', 'Trafficway Not in State Inventory', 'Unknown'
* functional_system_name: 'Not Reported', 'Unknown', 'Trafficway Not in State Inventory'
* manner_of_collision_name: 'Reported as Unknown', 'Not Reported'
* type_of_intersection_name: 'Not Reported', 'Reported as Unknown'
* light_condition_name: 'Reported as Unknown', 'Not Reported'
* atmospheric_conditions_1_name: 'Not Reported', 'Reported as Unknown'

Any rows with these values in the specified columns will either be eliminated from the dataset or validated as "other". This is done to ensure the accuracy and reliability of the data analysis.<br>
![cover](\assets\images\pa1\eliminasi.png){:width="60%"}<br>

Convert the abbreviation "USA" to "Central Standard Time"<br>
CST stands for Central Standard Time, which is a time zone used in some parts of the United States, Canada, and Mexico. The reason for changing the time zone to CST may be to ensure consistency and accuracy in reporting the time of the crash across different states and jurisdictions.

When dealing with data from multiple states or regions, it is important to have a consistent time zone for reporting and analysis. This is especially true when dealing with time-sensitive data, such as traffic accidents, where the precise timing of events can be critical in understanding the cause and severity of the crash. Therefore, by converting the timestamps to CST, all the data will be standardized and easier to compare and analyze.<br>
![cover](\assets\images\pa1\timezone.png){:width="60%"}<br>

### **ISSUE**<br>
There were high numbers of accidents in the United States in 2021, with 35,414 accidents involving 85,311 people. This proves that the regulations or traffic signs that have been established are still inefficient or not adjusted to the factors of accidents that occur. Therefore, an analysis of accident data from the previous year is needed to create more appropriate regulations.

### **OBJECTIVE**<br>
To analyze accident data in 2021, so that from the results of the analysis, new regulations can be created that have the potential to reduce the number of accidents in the future.

### **FINDING**<br>
The analysis conducted is to identify the factors that cause high accident rates. The first variable we analyzed is atmospheric conditions and light conditions. From this, it was found that in atmospheric conditions that are 'Clear', the number of accidents is high. The figure is also significantly different from other conditions such as 'Cloudy', 'Rain', 'Fog', 'Snow', and others. Contrary to what we expected, from the above data, we can conclude that some countries may have longer periods of sunlight, which is why the data above has a higher number of accidents in clear conditions. If we also connect the average accident time and day, the accidents occur during the day, where people tend to be more relaxed but in a hurry (not worried), resulting in a very high number of single accidents compared to others. In terms of light conditions, it was found that 'Daylight' actually has a high number of accidents, followed by 'Dark-lighted'. Contrary to what we assumed, the highest number of accidents from the above data occurred during the day. What we can assume here is that more people tend to drive during the day/daylight, resulting in more frequent accidents.<br>
![cover](\assets\images\pa1\kodisi-cahaya.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents based on lighting conditions.</p>

![cover](\assets\images\pa1\atmosfer.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents based on atmospheric conditions.</p>

Next, we analyzed the variables of intersection type or road type and manner of collisions. After data processing, it can be seen that straight roads or 'Not an intersection' have higher accident rates compared to other road types with a significant difference. Straight roads are the biggest cause of accidents because drivers can get bored and lose focus while driving, causing the vehicle to lose control and potentially lead to accidents. Then, from the manner of collisions, we found that the most common type of accident is a single-vehicle accident. 

![cover](\assets\images\pa1\jenis-jalan.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents based on road type.</p>

![cover](\assets\images\pa1\collisions.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents based on collision type.</p>

Furthermore, we also looked for states with the highest accident rates. Based on the graph we created, the top three states with the most frequent accidents are Texas, California, and Florida. Each of these states had around 3000 accident cases, while other states only had around 1000 cases. These three states have the highest population in the USA, with California being the most populous, followed by Texas and Florida. However, Texas has the highest accident rate ranking due to a large number of its residents not paying attention to the speed limit set.

![cover](\assets\images\pa1\negara-kecelakaan.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Top states with the highest accident rates.</p>

The next finding is based on the time of the accidents. On average, accidents occur between 10 am to 4 pm. During these hours, various activities are taking place such as working, going to school, traveling, and others, and this is also during the daytime where the hot weather can cause fatigue. The second highest average occurrence of accidents is between 7 am to 9 am and 5 pm to 6 pm.

![cover](\assets\images\pa1\hour-crash.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents based on the time of the accidents.</p>

In addition, we also analyzed the number of accidents that may have been caused by drunk driving. However, we found that only 25% of all accidents that occurred in 2021 were caused by drunk drivers.

![cover](\assets\images\pa1\drunkdriver.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Percentage of accidents based on drunk and undrunk drivers.</p>

We also found that accidents occur more frequently in urban areas, which accounted for 38.8%, compared to rural areas, which accounted for 6.1%. This proves that urban areas have more activities such as schools, work, cafes, malls, and others.

![cover](\assets\images\pa1\kota-desa.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Percentage of accidents in urban and rural areas.</p>

Lastly, we also analyzed the occurrence of accidents based on the time of the accidents, including variables such as day, date, and month. For the day variable, we found that accidents occur more frequently on Mondays with 6,111 accidents, followed by Sundays with 5,862 accidents. Monday is the day when various activities and routines such as school, work, grocery shopping, and others start, followed by a weekend break. Meanwhile, Sunday is the day of preparation for starting usual activities and routines on Monday, for example, many people return to their workplace. Sunday is also a day when most people do not have to work on the weekend, so the number of people traveling by car will increase, resulting in a higher likelihood of accidents and traffic. Based on the date, the highest number of accidents occurred on the 19th and also at the beginning of the month, while at the end of the month, the number of accidents was relatively small. Furthermore, based on the month, it can be seen that accidents occur more frequently around the summer season.

![cover](\assets\images\pa1\dayofweek.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents by day of the week.</p>

![cover](\assets\images\pa1\dateofcrash.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents by date of occurrence.</p>

![cover](\assets\images\pa1\monthofcrash.jpg){:style="display:block; margin-left:auto; margin-right:auto"}{:width="60%"}<br>
<p style="color:gray; font-size:80%;" align="center">Number of accidents by month of occurrence.</p>

### **Recommendations**<br> 

**The NHTSA should pay more attention to traffic conditions during peak hours when driver activity is high**<br> 
1. Enforce speed limits through warning signs
2. Impose strict penalties for violators
3. Install or add CCTV cameras to monitor straight roads, especially during peak hours
4. Install speed bumps to slow down drivers
5. Implement rules such as only vehicles with 2-3 passengers to reduce road congestion

**Encourage drivers to be more cautious**<br> 
1. Create/increase signage prohibiting cellphone use while driving
2. Advise drivers to use sunglasses to anticipate excessive sunlight

**The NHTSA should also conduct further research on the findings we have obtained. Due to limited data, the findings we have generated are also limited. If more detailed findings are desired, we suggest including data such as:**
1. Average driver speed
2. Whether or not a driver has a valid driver's license
3. Police or local government traffic regulations.

**Presentation Project Assignment 1 group 8**<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/TVDkauvS33E" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>