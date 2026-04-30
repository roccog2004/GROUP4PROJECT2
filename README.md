# GROUP4PROJECT2

# Team Name 
21479 Group 4

## Team Members 
 1. Raines Harvard [@RainesHarvard237](https://github.com/RainesHarvard237)
 2. Grace Klatt [@gracecklatt](https://github.com/gracecklatt)
 3. Rocco Garcia [@roccog2024](https://github.com/roccog2004)
 4. Kory Cote [@Korycote](https://github.com)

## Data Set
Where was it obtained, what are the dimensions of it (rows and columns), what are the various
columns, data types, etc. Describe it in sufficient detail so that an uninformed reader would
understand the dataset.  (Reduce what we have rn into bullet points of all the rows and columns) 

The dataset we selected is based on 2025 NYPD shooting incident records. We chose this dataset because of the wide range of insights that can be extracted from it. It provides valuable information not only for public safety officials looking to identify patterns and improve response strategies, but also for everyday individuals who want to better understand high-risk areas within New York City. In terms of data types, the dataset includes several dimensions that describe the incidents, such as borough, victim age group, victim race, and victim sex. These categorical variables help us categorize and better understand the context of each incident. On the other hand, the dataset also contains measures, such as latitude and longitude, which allow us to quantitatively map and analyze where incidents are occurring. While there are many discrete categories we could have explored, we chose to focus on visualizing patterns related to time of day, as well as grouping variables like age and victim demographics. This approach allows us to better identify trends and potential correlations within the data.

## Questions 
What are the questions, and why each question is important. Importance can be evaluated and
conveyed in a variety of ways including, social, economic, cultural and other factors. Also
indicate how they are tied to the data set or sets being used. (Add the why) 

Q1 How do youth shooting victimization patterns differ from adult patterns across time of day, day of week, and school calendar period?  

This question is important as it provides valuable information pertaining to the social impact shootings can unfortunately have on society. During certain times of the day youths are at greater risk than adults, and vice versa. Assesing this question can also help link when youths are put in potential danger during the school year and summer. 

Q2 How does shooting lethality vary by location type, borough, and time and where do high volume, high-fatality hotspots overlap?

Why This Matters: It is important to understand when and where shootings are most deadly and when they have direct implications on public safety resource allocation, emergency medical response positioning, and targeted intervention programs.A shooting occurring in one are can have many different survival odds than those in other areas. Some factors that are important to consider are witness presence, EMS response time, and concealment. Being able to identify hotspots where shooting volume and fatality rates overlap allow for police and policymakers to enforce more laws and resoruces to reduce fatality. 

## Manipulations 
- Replaced null values across all perpetrator and victim variables with "UNKNOWN" by changing the alias of the "NULL" variable 
- Filtered out records without location data by using the fiter tab
- Changed Borough to geographic role for mapping
## Calculated Fields

### YOUTH
  
This classifies each victim into an age group. If the victim's age group is <18 or 18–24, it returns "Youth (Under 25)"; otherwise, it returns "Adult (25+)." Helped to narrow the age group variable further. 

<img width="529" height="309" alt="Screenshot 2026-04-29 at 9 57 41 PM" src="https://github.com/user-attachments/assets/799ccd9c-4cf6-4236-8526-3f609f54bcfc" />


### Fatality Rate F (Filtered)
  
Only displays Fatality Rate when incident count ≥ 5, returning NULL otherwise to filter out unreliable small sample results.

<img width="491" height="305" alt="Screenshot 2026-04-29 at 9 58 57 PM" src="https://github.com/user-attachments/assets/61c05816-3472-4905-8448-c9d0dd00eb1f" />


### Season
  
Uses the month of the occurrence date to label records as "Summer" (June–July) or "School Year."

<img width="531" height="307" alt="Screenshot 2026-04-29 at 9 53 27 PM" src="https://github.com/user-attachments/assets/d789672b-377a-4268-97e5-617a31c29429" />


### Weekend 
  
Checks the day of week to classify records as "Weekend" or "Weekday."

<img width="491" height="309" alt="Screenshot 2026-04-29 at 9 59 29 PM" src="https://github.com/user-attachments/assets/50423f0a-9268-4a3f-9b88-99be64b580ae" />

### Fatality Rate
Proportion of incidents flagged as statistical murders out of total incidents.
<img width="543" height="325" alt="Screenshot 2026-04-29 at 10 00 05 PM" src="https://github.com/user-attachments/assets/6df7c0ec-6525-475b-88fa-1c69f1aa589d" />


### Adult Pct
Calculate each adult incident's share of total adult incidents at a given dimension level.
<img width="546" height="326" alt="Screenshot 2026-04-29 at 10 02 09 PM" src="https://github.com/user-attachments/assets/e57ad996-f339-4c6a-8ff4-ad317f423ddd" />


### Youth Pct
Calculate each youth incident's share of the total number of youth incidents at a given dimension level.
<img width="542" height="326" alt="Screenshot 2026-04-29 at 10 02 51 PM" src="https://github.com/user-attachments/assets/edbb103d-62c0-465a-a756-ac90c0b0e635" />


### Risk Gap
Difference between Youth Pct and Adult Pct in which positive values indicate disproportionate youth risk.
<img width="543" height="327" alt="Screenshot 2026-04-29 at 10 03 31 PM" src="https://github.com/user-attachments/assets/33048fd5-7fd7-467f-bf72-decef6dc3e2e" />

## Analysis and Results 

### Q1 How do youth shooting victimization patterns differ from adult patterns across time of day, day of week, and school calendar period?  

### Time of Day
The Risk Gap chart reveals that youth are underrepresented in overnight and early-morning shootings. The gap dips to −4.57% at 1 AM and stays negative till 11 AM. Starting around noon, the pattern flips, and youth become overrepresented, peaking at +3.97% around 4 PM. There's a secondary spike near 10 PM (+2.91%).
<img width="1479" height="674" alt="Screenshot 2026-04-29 at 10 04 57 PM" src="https://github.com/user-attachments/assets/7b1f28d4-3a92-4ebf-8e33-b4b03797ebad" />

The implication is that youth victims are disproportionately shot during afternoon and early-evening hours, times that align with school dismissal, after-school idle time, and outdoor activity; rather than the late-night hours that dominate adult victimization.

### Day of Week
The weekday vs. weekend dumbbell chart shows that weekend youth shootings cluster more heavily in the late-night and early morning hours. The brown dots for weekdays tend to sit lower than the blue weekend dots at hours like 12 AM–3 AM, while afternoon hours are more evenly split. Weekend nights appear to carry elevated youth risk in the 10 PM–12 AM window, with some hours reaching above 5%.
<img width="1480" height="675" alt="Screenshot 2026-04-29 at 10 05 54 PM" src="https://github.com/user-attachments/assets/b654f5a0-3d7a-47e7-9f8c-a5b750a44614" />

### School Calender Period 
During the school year on weekdays, youth shootings stay near zero during school hours (8 AM–2 PM) before a spike in shootings in the afternoon/evening, peaking around 10 PM (11.40%). While on the weekends, we still see this afternoon spike of around 9.52%, but shootings carry on throughout the night, spiking at 13.85% around 3 am. 

In summer, the overnight spike shifts earlier, peaking around 9 PM at 14.17%, and the weekday night shootings are higher, reflecting the absence of curfews usually in place during the school year.
<img width="1502" height="921" alt="Screenshot 2026-04-27 at 2 04 16 PM" src="https://github.com/user-attachments/assets/55f4fd70-de73-417a-a03a-fbef6eead58f" />

### Q2 How does shooting lethality vary by location type, borough, and time and where do high volume, high-fatality hotspots overlap?

### Borough Fatality Rates

The Bronx stands out with the highest fatality rate of 23 and the highest volume with 298 shootings. Queens follows at roughly 21% with 86 shootings. Brooklyn has a high volume of 266 but a somewhat lower fatality rate of 20%. Manhattan is still near the rest of the pack with 111 shootings and 20% fatality rate. Lastly, Staten Island sits way below average with only 13% fatality rate and only 8 shootings.

The Bronx is the clearest high-volume, high-fatality hotspot as it has both the most shootings and the deadliest outcomes, but Queens is interesting as it only has 86 shootings, making it second to last in incident amount, but also the second most deadly. 

<img width="1499" height="906" alt="Screenshot 2026-04-27 at 2 02 58 PM" src="https://github.com/user-attachments/assets/58530991-e871-429f-81f6-3e912877a431" />

### Location Type
The quadrant chart breaks locations into four main profiles:

- Common and deadly (upper-right quadrant): Street-level shootings for the 25–44 age group dominate here: high count, high fatality. This is the single most dangerous combination in the dataset.
- Common but survivable (lower-right): Street shootings for 18–24 victims and 25-44 are the highlights of this quadrant, likely from the publicity of the location.
- Rare but deadly (upper-left): Playground and dwelling shootings involving minors (<18) show up here, with low volume but alarmingly high fatality rates (50–60% for dwelling shootings of youth). These are low-frequency events, but when they happen to children, the outcomes are disproportionately lethal.
- Rare and survivable (lower-left): A mix of age ranges and locations all fall into this quadrant. 
<img width="1495" height="915" alt="Screenshot 2026-04-27 at 2 01 57 PM" src="https://github.com/user-attachments/assets/858d9aef-47c8-4b30-811e-fff7fccea03e" />

### Lethality by Hour and Day
The heatmap shows that weekend early-morning hours 3 AM weekend: 37 fatality count) and late evening 7 PM weekend: 25 are the most lethal time slots. Weekday afternoons 2 PM: 36, 4 PM: 42) carry high volume but comparatively moderate lethality per incident.

<img width="1501" height="911" alt="Screenshot 2026-04-27 at 2 01 13 PM" src="https://github.com/user-attachments/assets/f34e4373-7536-4b50-92f8-d8dbdf0b3d90" />

