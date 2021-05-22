-   [Introduction](#introduction)
-   [Data Organization](#data-organization)
    -   [US Accidents Data](#us-accidents-data)
    -   [Applications of Dataset](#Applications-of-Dataset)
-   [Exploratory Data Analysis](#exploratory-data-analysis)
    -   [Accidents Map](#accidents-map)
    -   [Top 10 States by Number of Accidents](#top-10-states-by-number-of-accidents)
    -   [Accident Rate and Severity by Day of the Week](#accident-rate-and-severity-by-day-of-the-week)
    -   [Accident Severity by Time of the Day](#accident-severity-by-time-of-the-day)
-   [Conclusions](#conclusions)
    -   [Main Observations](#main-observations)
    -   [Future Directions](#future-directions)
-   [Run Notebook in Google Colab](#run-notebook-in-google-colab)
-   [Youtube Video Link](#youtube-video-link)
-   [Inquiries](#inquiries)
-   [Data Sources](#data-sources)
-   [Applications of Dataset](#application)

# Introduction
Car accidents considering from one of the most problems that occurred in the recent years starting from that time that first car was made. This kind of problem has a lot of problems in different aspects such as economic, Psychological, and human souls. The economic damages that caused by the accidents are big like the damages that occurred on the cars from car metal's damages, re fix the body to re the car to its real shape; which is cause a lot of money costing on the car owner in order to fix it. The main problem of the car accidents caused is human deaths, many numbers of humans died in car accidents over the years which cause by a lot of losses on human souls and money. 
Knowing the reasons that causes the accidents have an efficient factor in order to avoid and solve car accidents reasons, and provide big and sufficient awareness of people in order to deal with the accidents and how to avoid the reasons that may cause the accidents like the vast speed, focus on the phone and social media while driving, and think about certain things other than driving.
Knowing the places that accidents occurred helps the government to provide safe facilities in these ways to help the citizens take care of them self while driving then avoiding the accidents as much as they can.
The main challenge in this kind of research is the huge amount of data used. The reason for the huge amount of data is the vast car accidents that occur every day, every hour, and every second.
Python programming language used in the paper to read, analyze, and visualize the data in an easy, understandable way using python libraries like Pandas, NumPy, Matplotlib, and Seaborn.
-	Pandas is a python library for data manipulation and analysis. It provides a data structure and operations for manipulating numerical tables [1].
-	NumPy is a python library that used in mathematical and logical operations on data [2].
-	Matplotlib is python package used for data visualization, it is a library for making 2D plots from data [3].
-	Seaborn is python library provides high level API for visualizing the data [4].

The paper asked some questions to be answered through the work, these questions represented as follows; displaying the state that has the highest number of accidents, the time that accidents usually do in the United States (US), and visualize the whole data set in one figure.
The dataset that used in the paper is a countrywide car accident dataset, which covers 49 states of the USA [5]. The accident data are collected from February 2016 to Dec 2020, using multiple APIs that provide streaming traffic incident (or event) data. These APIs broadcast traffic data captured by a variety of entities, such as the US and state departments of transportation, law enforcement agencies, traffic cameras, and traffic sensors within the road networks. Currently, there are about 3 million accident records in this dataset [6].
The remain paper workflow are as follow; Section II demonstrates the related work, Section III introduce the methodology, Section IV present the experimental results, and Section V conclude the whole study.

# Data Organization
This is a countrywide traffic accident dataset, which covers 49 states of the United States. The data is continuously being collected from February 2016, using several data providers, including multiple APIs that provide streaming traffic event data. These APIs broadcast traffic events captured by a variety of entities, such as the US and state departments of transportation, law enforcement agencies, traffic cameras, and traffic sensors within the road-networks. Currently, there are about 3 million accident records in this dataset. Check the below descriptions for more detailed information.

After filtering the data by removing the irrelevant attributes to our analysis, we ended up with the following attributes:

## US Accidents Data:
<div class="datatable-begin"></div>

| # | Attribute | Description |Nullable|
| - | --- | --- |--- |
|1|	ID|	This is a unique identifier of the accident record.|	No|
|2|	Severity|	Shows the severity of the accident, a number between 1 and 4, where 1 indicates the least impact on traffic (i.e., short delay as a result of the accident) and 4 indicates a significant impact on traffic (i.e., long delay).|	No|
|3|	Start Time	|Shows start time of the accident in local time zone.|	No|
|4	|End_Time	|Shows end time of the accident in local time zone. End time here refers to when the impact of accident on traffic flow was dismissed.	|No|
|5|	Start_Lat|	Shows latitude in GPS coordinate of the start point.	|No|
|6	|Start_Lng	|Shows longitude in GPS coordinate of the start point.	|No|
|7|	End_Lat|	Shows latitude in GPS coordinate of the end point.	|Yes|
|8|	End_Lng	|Shows longitude in GPS coordinate of the end point.	|Yes|
|9|	Distance(mi)	|The length of the road extent affected by the accident.	|No|
|10|	Description	|Shows natural language description of the accident.	|No|
|11|	Number	|Shows the street number in address field.	|Yes|
|12|	Street	|Shows the street name in address field.	|Yes|
|13|	Side	|Shows the relative side of the street (Right/Left) in address field.	|Yes|
|14|	City	|Shows the city in address field.	|Yes|
|15|	County	|Shows the county in address field.	|Yes|
|16|	State	|Shows the state in address field.	|Yes|
|17|	Zipcode	|Shows the zipcode in address field.	|Yes|
|18|	Country	|Shows the country in address field.	|Yes|
|19|	Timezone	|Shows timezone based on the location of the accident (eastern, central, etc.).	|Yes|
|20|	Airport_Code|	Denotes an airport-based weather station which is the closest one to location of the accident.	|Yes|
|21|	Weather_Timestamp|	Shows the time-stamp of weather observation record (in local time).	|Yes|
|22|	Temperature(F)|	Shows the temperature (in Fahrenheit).	|Yes|
|23|	Wind_Chill(F)|	Shows the wind chill (in Fahrenheit).	|Yes|
|24|	Humidity(%)	|Shows the humidity (in percentage).	|Yes|
|25|	Pressure(in)	|Shows the air pressure (in inches).	|Yes|
|26|	Visibility(mi)|	Shows visibility (in miles).	|Yes|
|27|	Wind_Direction	|Shows wind direction.	|Yes|
|28|	Wind_Speed(mph|)	Shows wind speed (in miles per hour).	|Yes|
|29|	Precipitation(in)|	Shows precipitation amount in inches, if there is any.	|Yes|
|30|	Weather_Condition|	Shows the weather condition (rain, snow, thunderstorm, fog, etc.)	|Yes|
|31|	Amenity|	A POI annotation which indicates presence of amenity in a nearby location.|No|
|32|	Bump|	A POI annotation which indicates presence of speed bump or hump in a nearby location.	|Yes|
|33|	Crossing|	A POI annotation which indicates presence of crossing in a nearby location.|No|
|34|	Give_Way|	A POI annotation which indicates presence of give_way in a nearby location.|No|
|35|	Junction|	A POI annotation which indicates presence of junction in a nearby location.|No|
|36|	No_Exit|	A POI annotation which indicates presence of no_exit in a nearby location.|No|
|37|	Railway|	A POI annotation which indicates presence of railway in a nearby location.|No|
|38|	Roundabout|	A POI annotation which indicates presence of roundabout in a nearby location.|No|
|39|	Station|	A POI annotation which indicates presence of station in a nearby location.|No|
|40|	Stop|	A POI annotation which indicates presence of stop in a nearby location.|No|
|41|	Traffic_Calming	|A POI annotation which indicates presence of traffic_calming in a nearby location.|No|
|42|	Traffic_Signal|	A POI annotation which indicates presence of traffic_signal in a nearby loction.|No|
|43|	Turning_Loop|	A POI annotation which indicates presence of turning_loop in a nearby location.|No|
|44|	Sunrise_Sunset|	Shows the period of day (i.e. day or night) based on sunrise/sunset.	|Yes|
|45|	Civil_Twilight	|Shows the period of day (i.e. day or night) based on civil twilight.|Yes|
|46|	Nautical_Twilight|	Shows the period of day (i.e. day or night) based on nautical twilight.|Yes|
|47|	Astronomical_Twilight|	Shows the period of day (i.e. day or night) based on astronomical twilight.|Yes|
<div class="datatable-end"></div>

# Applications of Dataset
# Exploratory Data Analysis
Here we explore some of the most interesting trends in our data. Please refer to [our notebook](https://github.com/pard187/pard187.github.io/blob/master/Final_Project_Gormley_Giffin_Johnston_Saleh.ipynb) to explore more profound Data Analysis findings and relatively successful Machine Learning models.

## Accidents Map
The following plot displays a scatterplot of accidents in the United States based on Latitude and Longitude. Note that the points are colored by Severity of the accident with red corresponding the Level 4 Severity (the most severe). Below the plot is a map of the major highways and interstates in the United States.
From these plots, we make a few observations. First, we observe that the accidents, and the Level 4 accidents in particular, seem to follow along the paths of the major highways and interstates in the United States. We have inserted a figure below to illustrate this point. Second, we observe the highest concentration of Level 4 accidents in the most densely populated areas near large cities such as Chicago, Portland, Colombus, and Jacksonville. The Southeast and Midwest regions show particularly high concentrations of severe accidents.

<p align="center">
    <img src = "Images/Accidents_Throughout_the_US.png" alt = "Scatter Plot of Accidents throughout the US Map">
    <img src = "Images/Highway_Network_in_the_US.png" alt = "Map of the Highway Network in the US">
</p>

## Top 10 States by Number of Accidents
After standardizing our data based on the population size, we were able to generate this plot which shows the number of accidents per 1000 residents for the top 10 states.

<p align="center">
    <img src="Images/Top_10_States_by_Number_of_Accidents_per_1000_Residents.png" alt="Bar Plot of the Top 10 States by Number of Accidents per 1000 Residents">
</p>

## Accident Rate and Severity by Day of the Week
The following two plots explore the relationship between accidents and days of the week. The first plot compares the number of accidents happening on each day of the week. We note that the number of accidents is fairly consistent Monday-Friday, however, the number of accidents drops significantly, to about a third of the original number, on the weekends. We hypothesize that this could be due to the work commute which happens Monday-Friday, but not on Saturday or Sunday. This is reasonable but something interesting shows up in the second graph, which compares the accident severity on each day of the week. It is noticeable that while there are fewer accidents occuring on the weekends, the severity of the accidents increases. During the weekdays, the percentage of accidents classified as Level 4 is constantly at under 5% of the total number of accidents. However, on Saturday and Sunday, this percentage nearly doubles.

<p align="center">
    <img src="Images/Number_of_Accidents_by_Day_of_the_Week.png" alt="Bar Plot of the Number of Accidents by Day of the Week">
    <img src="Images/Severity_of_Accident_by_Day_of_the_Week.png" alt="Bar Plot of the Severity of Accidents by Day of the Week">
</p>

## Accident Severity by Time of the Day
This plot aims to compare the severity of accidents happening in the daytime versus those happening at night. We note that as the severity of the motor vehicle accident increases, the percentage of accidents that occur after sunset increases from less than 20% (Severity Level 1) to nearly 40% (Severity Level 4). We hypothesize that this difference could be due to driving conditions, specifically the lack of light during those hours of the day, as the sun has completely set. This could also be due to human conditions such as fatigue, or intoxication, which we hypothesize may be more prevalent during those late hours.

<p align="center">
    <img src="Images/Severity_of_Accidents_and_Light_Condition.png" alt="Bar Plot of the Severity of Accidents during Day and Night">
</p>

# Conclusions
The goal of our analysis was to explore factors that lead to higher accident rates and higher rates of severe accidents. We explored data containing different road and weather conditions at the sight of accidents across the United States. Based on our analysis we make the following conclusions:

## Main Observations

First we observe some trends in accident rates among states. South Carolina and Oregon in particular display high rates of accidents per 1000 residents. Furthermore, the Southeast and Midwest regions appear to have higher rates of accidents. We observe also that communities with higher rates of public transport and lower rates of driving commutes record fewer accidents.

General Conditions: The highest rates of accidents occur during weekdays during the morning and evening commuting hours. However, accidents tend to be more severe accidents occur on weekends and during the middle of the night.

Road Conditions: Road conditions that decrease the rate of accidents are most notably the presence of Stops and Bumps. Traffic Signals and Crossings decrease the severity of accidents that occur in nearby locations. On the other hand, Junctions seem to increase the severity of nearby accidents.

Weather Conditions: Weak relationships between Temperature, Humidity and Severity were observed. As Humidity increases, accident severity increases, and as temperature decreases, accident severity increases. Somewhat suprisingly no weather conditions displayed strong correlation to accidents or accident severity. This is most likely due to limitations in how the data was collected. Also, we believe weather to be most significant at causing accidents in extreme forms, however, for a nationwide dataset such as the one we used, extreme weather occurrences are rare and therefore their significance is not clear in the data.

Our machine learning model was able to relatively successfully predict accident severity using the most significant factors discussed above. This performance supports our conclusion that there is a relationship to note between the variables.

## Future Directions

Based on our insights above we can make the following recommendations to clients interested in preventing accidents and decreasing accident severity.

Accident prevention measures should focus on late night driving on weekends. This could potentially include driving under the influence and driving fatigued education initiatives.
Stops, Speed Bumps, and Roundabouts could be implemented in areas of frequent accidents in order to decrease the rate.
More Traffic Lights and Crossings in areas of frequent accidents can reduce accident severity.
Regions with high rainfall, high humidity, or low temperatures should further investigate the effect of weather on accident rates and should explore preventative measures to counteract the increased risk.
In regards to where to begin, we would reach out to the states with the highest accident rates per 1000 residents in order to encourage a pointed approach to reducing this statistic. In addition, more specific recommendations can be provided based on a specific County or State, as displayed by the performance of the Machine Learning model on Greenville County, SC.

# Run Notebook in Google Colab

Click the link below to run [our notebook](https://github.com/pard187/pard187.github.io/blob/master/Final_Project_Gormley_Giffin_Johnston_Saleh.ipynb) directly in Google Collab. No coding is required to run this notebook, you just need to run every code cell in order or simply click Runtime -> Run all and wait for all cells to run. 
Click the link below to run [our notebook](https://github.com/pard187/pard187.github.io/blob/master/Final_Project_Gormley_Giffin_Johnston_Saleh.ipynb) directly in Google Collab. No coding is required to run this notebook, you just need to run every code cell in order or simply click Runtime -> Run all and wait for all cells to run.

*Please note that since the US-Accident dataset we are using is too big, it was not convienient to download and import it to Google Drive or Github. Therefore, our notebook is pulling the data directly from Kaggle. A potential drawback to this method is that any changes to the dataset on Kaggle will affect the ability of the analysis in this notebook to be replicated. At the time of analysis, the US-Accidents dataset was last updated July 9, 2020. Were the dataset to be altered at a later date, then the conclusions drawn as a part of this analysis might change. We have however, stored a version of the US Accidents data in this GitHub repository for access at a later date.*

<table align="left">
  <td>
    <a target="_blank" href="https://colab.research.google.com/github/pard187/pard187.github.io/blob/master/Final_Project_Gormley_Giffin_Johnston_Saleh.ipynb"><img src="https://www.tensorflow.org/images/colab_logo_32px.png" />Run in Google Colab</a>
  </td>
</table>
<br> <br> <br>

# Youtube Video Link
Check out our walkthrough video [here](https://youtube.com/watch?v=IXMQVvu-zYY)!

# Inquiries
For inquiries about this project, please contact Kaelyn Gormley at <a href="mailto:gormleyk@lafayette.edu">gormleyk@lafayette.edu</a>, James Giffin at <a href="mailto:giffinj@lafayette.edu">giffinj@lafayette.edu</a>, Kate Johnston at <a href="mailto:johnstkr@lafayette.edu">johnstkr@lafayette.edu</a>, or Marwa Saleh at <a href="mailto:salehm@lafayette.edu">salehm@lafayette.edu</a>.

# Data Sources
- [US-Accidents Dataset](https://www.kaggle.com/sobhanmoosavi/us-accidents)


- Moosavi, S. [*US Accidents (3.5 million records)*](https://www.kaggle.com/sobhanmoosavi/us-accidents), Version 6. 2020 
- Moosavi, S. [*US Accidents (3.5 million records)*](https://www.kaggle.com/sobhanmoosavi/us-accidents), Version 6. 2020

- Moosavi, Sobhan, Mohammad Hossein Samavatian, Srinivasan Parthasarathy, and Rajiv Ramnath. [*A Countrywide Traffic Accident Dataset.*](https://arxiv.org/abs/1906.05409), 2019.

- Moosavi, Sobhan, Mohammad Hossein Samavatian, Srinivasan Parthasarathy, Radu Teodorescu, and Rajiv Ramnath. [*Accident Risk Prediction based on Heterogeneous Sparse Data: New Dataset and Insights.*](https://arxiv.org/abs/1909.09638), 2019.

- Muon, Neutrino. [*US Census Dempgraphic Data*](https://www.kaggle.com/muonneutrino/us-census-demographic-data), Version 3. 2018

- National Highway Traffic Safety Administration (NHTSA), [*2019 Fatality Data Show Continued Annual Decline in Traffic Deaths*](https://www.nhtsa.gov/press-releases/2019-fatality-data-traffic-deaths-2020-q2-projections), October 2020
