# **Case Study: Bellabeat Data Analysis**

#### Analyst: Patrick Kenny

#### Date: August 15, 2022

________________________________________________________________________________________________________________

### This case study follows a six step data analysis process:

1. Ask
2. Prepare
3. Process
4. Analyze
5. Share
6. Act

## Scenario

Bellabeat is a small but successful manufacturer of health focused products for women. The company has had success as a small scale, but its founders believe it has the potential to become a larger player in the global smart device market. Urska Srsen, co-founder and Chief Creative Officer, believes that analyzing smart device data could help unlock new growth opportunities for the company. I am a Junior Data Analyst working on the marketing team at Bellabeat.

## **1. Ask**

**Business Task: The CCO, Urska Srsen, has asked me to analyze smart device usage data in order to gain insight into how consumers use non-Bellabeat smart devices, and then apply my findings to one of Bellabeat’s products.**

Primary Stakeholders: Bellabeat co-founders, Ursa Srsen (CCO) and Sando Mur

Secondary Stakeholders: Bellabeat marketing analytics team

## **2. Prepare**

**Data Source:** The data used for this analysis is FitBit Fitness Tracker Data. This data is CC0: Public Domain, dataset made available through Mobius, via Kaggle. This dataset was generated by respondents to a distributed survey via Amazon Mechanical Turk between 03.12.2016-05.12.2016, in which thirty eligible Fitbit users sonsented to the submission of personal tracker data. https://www.kaggle.com/datasets/arashnic/fitbit

The dataset includes 18 CSV files.

**Does the data align with the ROCCC criteria?**

* **R**eliable: **LOW** - This data was collected from a small sample size (30 users), of which characteristics like gender, age, location is unknown. In addition to this, of the thirty Fitbit users who participated in the survey, only a fraction submitted complete data. 
* **O**riginal: **MEDIUM** - For our analysis, we are not using the original dataset produced via Amazon Mechanical Turk, but there are consistent and accurate citations. We have no reason to believe that the content of the dataset has changed from it's original form. 
* **C**omprehensive: **MEDIUM** - This dataset does not include some information that would be relevant and helpful for our analysis. This includes information such as gender, age, location, device usage, etc. Additionally, only covers a short period of time, (~2 months). This limits our ability to identify trends. 
* **C**urrent: **MEDIUM** - Our data was collected between March and May of 2016, making it a litt more than 6 years old. While this is not an extreme amount of time, there have been substantial societal and social changed during that period. 
* **C**ited: **HIGH** - The source and means of data collection is accurately and clearly cited. 

**Notable Problems with the data:**

* With only 30 users participating in this study, we have a relatively small sample size. 
* The data collected from each participant widely varies, with some participants responding 31 times (max), one participant responding 3 times (min), and multiple participants responding around 20 times. 
* The dataset that contains information on participant weight is very limited, with only 8 users submitting data. 
* Our dataset is limited, only including a two month period during the Spring. (Assuming our users live in the US)

## **3. Process**

**Tools to be used:** For this analysis I chose to use Excel for the entirety of the project. One of the main factors contributing to this decision was the relatively small size of the dataset. 

**Transforming the Data:** As was previously mentioned, the Fitbit data used for this analysis came in the form of 18 seperate CSV files. Many of these files included repeated columns, so I will only need to use 5 of these files. I chose these files because they provide a useful overview of the tracker data, allowing me to find actionable insights and provide useful high-level recommendations. For ease of use, I merged the weightLogInfo_merged data into the dailyActivity_merged data set.  The files I have chose to use are:

  * dailyActivity_merged.csv
  * hourlyCalories_merged.csv
  * hourlyIntensities_merged.csv
  * hourlySteps_merged.csv
  * sleepDay_merged
  * weightLogInfo_merged.csv

After aggregating the daily data, I added additional columns to allow for greater flexibility in my analysis. Some of the changes I made where:

  * Inserted the data into a table format
  * Used the date column to create two seperate columns for the month and day of the week
  * Used Index/Match to import sleep data into the dailyActivity_merged data set
  * Transformed the minutes slept into hours, making it easier to digest for myself and stakeholders
  * Aggregated the totalsteps into 5 "baskets", raning from "very low" to "very high", allowing for for meaningful insights
  * Used Index/Match to import weight data into the dailyActivity_merged data set

**Cleaning the data:**

  * Checked for any duplicates in the data and removed any instances of them
  * Ensured that there weren't any extreme outliers in the data
  * Discovered that the users who submitted data varied among the data sets. The data set had 33 users for daily activity, 24 for daily sleep and only 8 for weight         log. This will likely lead to weight data that is not valuable, as it doesn't reflect the overall sample popoulation. 

## **4. Analyze**

### **Overview:** 

The first step of my analysis was to explore the data and get a feel for what it contained. I found: 

 * Average Daily Steps: 8,319
 * Average Daily Time Sedentary: 956 minutes or ~16 hours
 * Average Calories Burned: 2,361
 * Average Time Slept: 7 hours
 * Average Time in Bed: 7 hours and 38 minutes
 
This provided me with a solid base to start my analysis from, and also provided one particular insight that I would focus on later in my study. That insight was the difference between the time slept and the time in bed. It tells me that the participants are spending an average of 38 minutes in bed, before or after sleeping. 


### **Daily Activity Level Breakdown:**

The data categorized activity level into four seperate groups: Sedentary, Lightly Active, Fairly Active and Very Active. The pie chart shows us the time participants doing each type of activity, broken down by percentage. As we can see, 79% of the time participants are Sedentary, 17% of the time performing light activity, 2% fairly active and 1% very active. 

![image](https://user-images.githubusercontent.com/108141441/184989458-60b00d6f-43b9-4c52-867c-b47c57ba0e1f.png)

According to the Mayo Clinic, as a general goal, adults should aim for at least 30 minutes of moderate physical activity every day. They add that if you want to lose weight, maintain weight or meet specific fitness goals, you may need to exercise more. Additionally, reducing sitting time is also important. They say that the more hours you sit each day, the higher your risk of metabolic problems. According to this data, our participants spend on average about 3% or 43 minutes doing "fairly active" and "very active" activity, indicating that they meet the Mayo Clinics recommendation. At the same time, our participants also spend 79% or 18 hours and 57 minutes in a Sedentary state. This has the potential of leading to metabolic problems. 

### **General Trends:**

This line graph represents the average number of steps of our participants, by the day of week. As we can see, there is a spike on Saturday, as well as early in the week, and a drop at the end of the work week and Sunday. It could be beneficial to gather additional qualitative data via surveys or other means, to discover what contributes to this pattern. One hypothesis could be that people are energized by the work week being over on Saturday and have additional free time, then rest on Sunday to prepare for the week ahead, are energized early in the week by their rest and the opportunities of a new week ahead, and then tired out by Friday. 

![image](https://user-images.githubusercontent.com/108141441/184996885-8d842754-f8a5-49f4-945b-8e3a290836ee.png)

This line graph shows average step count, by time of day. From this graph, we notice a sharp drop in activity around 3pm, possibly following lunch time. We also notice acitivity levels peaking between 5pm and 7pm, around the time when many people are getting off work. From this chart we can possibly infer that individuals are having a post lunch crash, something we may want to address later. 

![image](https://user-images.githubusercontent.com/108141441/184997486-cdeab684-1b70-4fa1-94b7-babfba92c756.png)

In this bar chart, we look at the average calories burned by Sedintary Time. Interestingly, we see that there doesn't seem to be any correlation between lower sedintary time and more calories burned. If anything, we see a higher level of calories burnt when or participants spend more time in the middle three levels. 

![image](https://user-images.githubusercontent.com/108141441/184998032-728a03cb-f8fb-44c7-bbb9-fe0520602543.png)


### **Correlations:**

In this line graph we see a correlation between activity level and sedentary level. This graph provides interesting insight and possibly provides some clarity to what we saw in the previous chart. It appears that participants in the middle three levels of sedentary time also spend the most time in moderate to high levels of intest acivity. 

![image](https://user-images.githubusercontent.com/108141441/184999453-c03c87a8-461b-4e04-99ac-2139d21a49ee.png)

This chart is looking at the correlation between steps and calories burnt. As would be expected, we do see some correlation between step count and calories burned. But, maybe more surprisingly is the larger population of participants who have minimal activity, but still burn between 1500 and 3000 calories. We can understand this a bit better by thinking back to the information from Mayo Clinic, in which they informed us that it takes substantial activity at at least a moderate level to lose weight (burn more calories than you consume). 

![image](https://user-images.githubusercontent.com/108141441/185006046-e8ddd408-9bc7-4fc4-85fb-baee50400123.png)


### **Sleep:**

In this graph we see the average hours of sleep by day of the week. In it, we notice that there is a relatively consistent amount of sleep participants get during the week, with a notable spike on Sunday and a smaller increase in Wednesday. Thinking back to our step count by day of the week chart, we can draw a correlation between sleep and activity level. We see an increase in activity level at the beginning of the week, correlating to a better night sleep Sunday. 

![image](https://user-images.githubusercontent.com/108141441/185006542-e35de601-41a5-47b4-a2e7-ad18af5bd529.png)

This chart shows us the percentage breakdown of how participants spend time in bed. We can see that on average participants spend 91% of their time sleeping and 9% awake, either before or after sleeping. 

![image](https://user-images.githubusercontent.com/108141441/185007495-7acea1a9-ba9c-4c9e-bdd5-d48cd0243cd6.png)

According to an article from the Harvard Medical School, it is reccomended that when possible, we striclty reserve our bed only for sleep. They add that we should avoid answering phone calls, responding to emails, and wathching TV/Video games. 


## **5. Share:**



## **6. Act**

**Summary of Analysis**

 * Almost 80% of each day in a sedentary state by our participants, with only 3% of their time doing a moderate to high level of activity
 * Saturday and the beginning of the week were the most active times for our participants
 * Between 5pm and 7pm was the most active time for our participants and around 3pm we saw a noticable low point when compared to the rest of the waking day
 * We see a moderate correlation between step count and calories burned
 * On average, our particpants got the most sleep on Sunday
 * Patricipants spent 9% of their time in bed, awake

**Recommendations**


