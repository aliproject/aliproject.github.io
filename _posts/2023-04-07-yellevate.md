---
title: Elevating Yellevate
layout: post
post-image: "/assets/images/yellevate/yellevatecover.png"
description: This is a group project assignment at Refocus Digital Academy.
tags:
- Data Analyst
- Refocus
- Excel
- SQL
---
### **INTRODUCTION**<br>
For the past few years, Yellevate has been struggling with client disputes. Yellevate defines disputes as clients expressing dissatisfaction with the company’s services and refusing to pay for them. The team will be following Google’s five phases of data analysis: ask, prepare, process, analyze and share.

### **Data Analysis Objectives**<br>
Statistically, approximately 20% of the Yellevate conflicts resulted in a payment opt-out. This has resulted in a 5% annual revenue loss (in USD). Management has now asked the data analyst team to assist in resolving the problem. The team must identify the reasons for these issues using data gathered by the company and devise practical methods to resolve them.

Executives at the company decided that the following information should be obtained to identify the circumstances around the dispute problem:

1. The processing time in which invoices are settled (average # of days rounded to a whole number).
2. The processing time for the company to settle disputes (average # of days rounded to a whole number).
3. Percentage of disputes received by the company that was lost (within two decimal places).
4. Percentage of revenue lost from disputes (within two decimal places)
5. The country where the company reached the highest losses from lost disputes (in USD).<br>

### **PREPARE**<br>

### **ROCCC Analysis:**<br>
Reliable — The data has been made available by Refocus specifically for this project

Original — Subject to the terms and conditions of the Data License Agreement by NHTSA.

Comprehensive — Data dictionary has been provided through this [link](https://docs.google.com/spreadsheets/d/1o2nk0hGXDWviSegJp1RHtzzQN0e4gmP91mTdp-Dj-X4/edit?usp=sharing).

Current — The latest data is 2022.

Cited — All the data needed for this project can be accessed through this [link](https://drive.google.com/file/d/1b7Q5pRBB0cov_m0zRNPS_HyhVv8tHXL_/view?usp=sharing).

### **PROCESS**<br>
The program that we used for data cleaning is pgAdmin 4 using PostgreSQL. The first thing to do was to create a new database and create a new table. To create a new table, the code is the ff:<br>
![cover](\assets\images\yellevate\yallecelaning.png)<br>

Next is to import the dataset in pgAdmin. On the left side panel, right-click on the table that was created earlier, and then select Import/Export Data…<br>
![cover](\assets\images\yellevate\yellecelan8.jpg)<br>

Click on the folder icon to locate the file that needs to be imported. The format should be CSV and the encoding is UTF8. Hit OK to import the CSV file.

![cover](\assets\images\yellevate\yelleimport.jpg)<br>

### **CLEAN DATA**<br>
According to the data dictionary, the disputed field has a 0 or 1 value. “1” signifies the customer disputed the invoice; “0” means they did not. When this table is provided to clients, they must understand what the numbers 0 and 1 signify. The team has added a new column that will display Disputed or Not Disputed.

![cover](\assets\images\yellevate\yellecelan6.jpg)<br>

The same goes with the dispute_lost column, “1” means Yellevate lost the dispute and the dispute was resolved in favor of the customer, and the customer does not have to pay the invoice; “0” means the customer did not win the dispute, and they are legally required to pay the full invoice amount, it either means that Yellevate won the dispute, or there was no dispute in the first place.

![cover](\assets\images\yellevate\yelleclean2.png)<br>

Lastly, a new column named settlement has been added to distinguish disputes that have been settled on time or settled late.

![cover](\assets\images\yellevate\yellecelan3.jpg)<br>

The country column is the one that can be checked for inconsistencies. We can see all of the countries listed by using the DISTINCT function. There are just five distinct countries after running the code.

![cover](\assets\images\yellevate\yellecelan4.jpg)<br>

### **FINDING**<br>
Russia has the longest average processing time of 29 days, which is 22.81% longer than China, which has the shortest data of 23 days. Furthermore, the average processing time for the entire dataset is 26 days.
<br>
![cover](\assets\images\yellevate\yelleaverage.jpg){:style="display:block; margin-left:auto; margin-right:auto"}<br>
Russia has the highest average processing time of 5 days, which is 2.5 times faster than China, which has an average processing time of 2 days. Furthermore, the average processing time for the five countries is three days.<br>

![cover](\assets\images\yellevate\yelleaverage2.jpg){:style="display:block; margin-left:auto; margin-right:auto"}<br>

France has the highest percentage of lost disputes at 34.23% which is 9 times higher than the United States which only has 3.75% lost disputes.<br>

![cover](\assets\images\yellevate\yelletop5.jpg){:style="display:block; margin-left:auto; margin-right:auto"}

France has the highest percentage of revenue lost from disputes at 13.35% which is 15 times higher than the United States which only has 0.84% lost disputes.

![cover](\assets\images\yellevate\yellecelan7.jpg){:style="display:block; margin-left:auto; margin-right:auto"}

Because France has the highest rate of lost disputes, the country with the biggest losses from lost disputes should be France.

![cover](\assets\images\yellevate\invoicea-amount.jpg){:style="display:block; margin-left:auto; margin-right:auto"}<br>

Customers file a dispute with Yellevate because they expected a pandemic exception in their contract but were not given one. As a result, they decided not to pay their invoices or file a dispute. They believe that because of natural disasters, every company should make an exception for their customers.

Consider that the invoice dates occurred during the pandemic, which meant that employees were adjusting to their workforce. Furthermore, the lack of documentation from both parties, and the lack of communication caused the dispute to arise.

Aside from the invoices being settled late, there is no visibility into why they were late and why the invoices were being disputed. It is suggested that we include more information in the dataset, such as the cause for the delay and why it is disputed.

With it, we can get a better understanding of the issue at hand and take the required steps to resolve it. For the time being, since the only ground for a dispute is “Late Settlement,” we can ask the client how the settlement is progressing.

### **RECOMMENDATIONS**<br>
Yellevate and its customers must have open communication with each other especially if one party wanted to change the contract.

Have a discussion with the customers and offer them freebies such as discounts on future service requests in exchange for not opting out of their payment in order to reduce revenue loss.

Here’s an overview of the insights and visualizations we made:

![cover](\assets\images\yellevate\yellemore.jpg){:style="display:block; margin-left:auto; margin-right:auto"}<br>