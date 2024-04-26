# Meteorological Data Analysis in R

It can also be termed as weather analysis.

![rain4-1-620x370](https://github.com/AfifRifaie95/R---US-Weather-Pattern-Analysis/assets/159521904/55b6f861-3101-4bb6-bd94-c2d4847f38bf)

### Table of Content

[Project Overview](#Project_Overview)

[Data Import](#Data_Import)

[Data Exploration](#Data_Exploration)

[Data Cleaning](#Data_Cleaning)

[Data Pre-processing](#Data_Pre-processing)

[Question 1 The United States Rain Analysi](#Question_1_The_United_States_Rain_Analysi)

[Question 2 Level of dryness in the United States](#Question_2_Level_of_dryness_in_the_United_States)

[Question 3 Common Breeze in the United States](#Question_3_Common_Breeze_in_the_United_States)

[Question 4 Why no rain take majority in the United States?](#Question_4_Why_no_rain_take_majority_in_the_United_States?)

[Conclusion](#Conclusion)

[References](#References)

### Project Overview

The purpose of this report is to investigate and analyse weather data from the United States. It begins with performing data importing, data exploration, data cleaning and data pre-processing, followed by investigation and visualisation into a visual graph using R Studio.


### Data Source

The dataset is obained from Kaggle [Available Here](https://www.kaggle.com/datasets/zaraavagyan/weathercsv)

### Software

R [Available Here](https://cran.r-project.org/bin/windows/base/)
R Studio [Available Here](https://www.r-project.org/)

### Data Import

The first step of data analysis is to import the given data set. The data was given in csv format.

<img width="431" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/d60c27c4-3af0-4866-8189-aae2b341ef77">

Based on the above snippet, the first thing I did was set the working directory and save it in my personal file. Then I download the necessary packages and install it in my R Studios. To import the data, I used the read.csv() function, which round bracket is the location of the data set on my computer, and I set the given data set as a weather_data variable. I install packages with install.packages() function and the library() function to store the code in the R environment under a directory called library.

### Data Exploration

After importing the Data Set into the R Studio. The next step is data exploration which to understand the data set. This is to do research to understand better of the rain attributes. I did research on each of the columns name in the data. After the research, I get basic information on what are the meaning of each column provided in the data set. After doing research, the next step is to know the basic information of the data such its structure, dimensions, columns names and summary.


<img width="416" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/091c60c8-64f5-4942-9b6f-ac869673e729">


To explore the data, I use str() function to find out the class of each column in data set. Then, I use colnames() function to find out the names of the data. I use the summary() function to get the data's mean, lowest, and highest values. View() function is used to view the data set in table format. The output of the function as below.


<img width="431" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/04ef5a3f-8e1f-4d6e-ac2f-79023c3a2cee">


str() function gives an overview on how many observations and variables are in the data set. This function also provides the information about the type of data, which useful when determining the graph for visualization.


<img width="419" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/979c4fbc-ae47-40a5-87e6-858c88df5b49">

dim() function provides information about how many rows and columns are in the data set. There are 366 rows and 23 columns in the weather_data.

<img width="434" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/05395a59-1f2f-47bf-b595-d36b0a934214">


colnames() function provides the names of each column in the data frame. It is also function to change the names of the columns.

<img width="428" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/e0bcdbee-284a-4e5a-b482-dfa3d670f1bb">

Similarly, names() function gives the name of the object's header in a data frame.

<img width="444" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/aa6e488e-e1c1-47cb-82e8-b93fae17f1f9">


summary() function provides an overview of the variables, including their minimum, first quartile, median, mean, third quantile, and maximum values.

<img width="428" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/ecb77611-7476-4770-b7f6-e537412bd28f">

View() function is used to produce table style data viewer.


### Data Cleaning

Once I explored the data, I proceed with data cleaning. Basically means to make sure that all the columns are set up in a way that is easy for the user to understand and to make sure the columns are set without spacing and inconsistent use of capital and small letter. As the snipped below, I reset the column names with proper spacing using underscore and start the name with capital letter. I state the new columns name into the vector c(“ ”) and set it back to the weather_data.


<img width="428" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/5385b8df-48fc-427d-a4c7-64b3b14572fa">

### Data Pre-processing

After cleaning the data set, the next step is to do the data pre-processing. From the data set, there are no dates given for when each of data attributes happened. As below snipped, I add new Days columns to the data set. With Days column, it would be useful to measure when each of the attribute happened. First, I set new vector of 1:366 because there are 366 rows of data. The assumption I make is each of the row represent a day. Then I used cbind() function to add new Days column in the data set.


<img width="427" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/c86ff047-3c49-4aee-8c89-952802355f65">

### Question 1 The United States Rain Analysis

#### Analysis 1.1: Days with and without rain over the course of a year

<img width="433" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/4c1104ca-2bd6-47f3-8772-e31434ba1593">


In this assignment, pipe function %>% is used to start the code as it takes output of one function, and passes it into the another function as an argument. The stored data variable is weather_data. geom_bar() function under ggplot() package is used to build a bar chart graph. The x-axis shows days it rained or didn't rain, and the y-axis shows how many days it happened. The bar’s colour is set by the fill function in geom_bar(). The theme_bw function is to set theme as grey theme with grey lines on white background. While labs() function is used to change the names of the x axis, y axis and to give title of the graph.


<img width="434" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/5ef83098-daec-47e4-bf8d-27c6f11bfc5d">


The figure above shows that the number of days when it does not rain is more than the number of days when it does rain. Meaning that it does not rain very often in the U.S.

#### Analysis 1.2 Number of rainy and not rainy days for tomorrow

<img width="429" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/529ed185-7414-4b61-b4f3-a099eaeb2341">

The code is used to make a bar chart graph, where x representing will it rain tomorrow and y axis representing how often it will rain. The bar's colour is set by the fill function in geom_bar().


<img width="431" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/2facf118-2040-49ae-ab1d-84984a748437">

Similar to rain today bar chart, rain tomorrow has similar amount of rainy and not rainy days where no rain takes the majority of the days in the United States throughout a year.

#### Analysis 1.3 Total rainfall for raining days

<img width="436" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/3082faac-2a22-4e48-8def-3806be293e23">

This code is used to build a scatter plot with a tabulation line that shows how much rain falls throughout a year, with X axis representing the number of days and Y axis representing the amount of rain. In addition to that, colour = Rain_Today in ggplot() function to differentiate categorical variable for Rain_Today in the plot. Green represent yes for raining days while orange represent not raining days. geom_smooth(method = lm) function to add a straight regression line into the scatter plot.

<img width="431" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/a07dc0e5-1dc1-4dd1-8b45-b8f46365ce0c">

The figure above shows that most of the rain falls between 0 and 20 throughout the year, and only one day has high amount of rain fall.


#### Analysis 1.4 Relation between cloud at 3pm and rain today

<img width="435" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/a88af14d-abfb-4bd0-956a-49142ba69cf6">

The code is used to build a boxplot graph. The x axis representing cloud level, the y axis representing rain today. The colour of the boxplot is set by the fill function in geom_boxplot.


<img width="440" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/9ae88715-d72d-46a6-a1c6-515c7d1cca90">


The line in the middle of the box shows the average value, while the left and right walls show the lowest and highest values. The boxplot above shows that on days when it rains, the clouds are more likely to be in the 2–7 cloud level range than on days when it doesn't rain, when the cloud level can go as low as 1.


### Question 2 Level of dryness in the United States

#### Analysis 2.1 –Average Temperature at 3pm

<img width="425" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/a153b02d-7090-4439-b54e-416a6ec1ebf1">

The code is used to build a boxplot graph. The x axis representing rain today, the y axis representing temperature at 3pm. The colour of the boxplot is set by the fill function in geom_boxplot. The coord_flip() function is used to flip the graph so that it can have better view.

<img width="436" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/5922fcff-9e19-44a6-94de-60b539033313">


The line in the middle of the box shows the average value, while the left and right walls show the lowest and highest values. The boxplot above shows that when it rains, the average temperature is a little lower than when it doesn't. The lowest temperature is 5.10 when raining. On days when it doesn't rain, the temperature can get as high as 34.50.

#### Analysis 2.2 – Compare temperature and sunshine

<img width="429" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/9860c8af-24f2-447f-be89-ddad4e330427">

The code is used to build a scatter plot. The X-axis shows the amount of sunshine, and the y-axis shows the temperature at 3 p.m. For the straight linear line on the graph, the geom_smooth() function with method = lm is used.

<img width="428" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/2a84a81b-ca98-4cd2-af64-d79b95f5b904">

The figure above shows that there is a positive relationship between the amount of sunshine and the temperature. When there is more sunshine, the temperature goes up.

#### Analysis 2.3 – Compare temperature and humidity

<img width="430" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/ef6f4779-f653-4e3b-ae7f-e8570076d840">


The code above is used to build a scatter plot. The x axis representing humidity, the y axis representing temperature at 9am. The geom_smooth() function is used to get the linear line in a graph.

<img width="426" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/87a2deb3-2a0b-4403-9ec7-dd0ac5bba470">

The above figure shows that the humidity has negative relationship against temperature. When humidity is high, the temperature goes down.

#### Analysis 2.4 – Compare temperature and evaporation

<img width="433" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/e760b67c-806f-48db-968b-3dbaf4a11850">

The above code is used to build a scatter plot. The x axis representing temperature at 9am, the y axis representing evaporation. The fill function in geom_boxplot is to set the colour of the point. The geom_smooth(lm) function is to get the linear line in the graph.

<img width="434" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/fb2a521f-3d30-4d6a-8d33-625cf2a1068b">

The above figure shows that the evaporation has positive relations with the temperature. The amount of water that evaporates depends on how high the temperature is.

### Question 3 Common Breeze in the United States

#### Analysis 3.1 –Average Wind Gust Speed

<img width="431" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/b9a5aec7-a8b2-4b22-a508-f8686f4e518f">

The code is used to build a scatter point graph, where the x axis shows the number of days and the y axis shows the speed of the wind gusts. The geom_smooth(lm) function is get the linear line in the graph.

<img width="433" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/88225286-23ab-4b3e-b465-46e22ee514c3">

The figure above shows that the average gust speed in the United States is 39.00 miles per hour. The highest possible value is 98, and the lowest possible value is 13.

### Analysis 3.2 –Major Wind Gust Speed occurrence

<img width="430" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/59b886b7-e519-47f9-b863-14ddaae465fa">

The code is used to build a bar chart graph, with the x axis showing the direction of wind gusts and the y axis showing how often they happen. The fct_infreq function is used to make the number of occurrence of wind gust direction in ascending order. The coord_flip() function is used to turn the graph around so it can be seen better.

<img width="438" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/86ff7d90-fa90-4a7e-be52-87342af7ec1f">

The figure above shows that wind gusts are most likely to come from the NW and least likely to come from the WSW.

### Analysis 3.3 –Highest wind gust speed for each wind gust direction

<img width="431" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/c93fbb79-c3c8-4b77-9ae7-cc492ba12425">

The code is used to build a scatter point graph with line. The x-axis shows the speed of wind gusts, and the y-axis shows the direction of wind gusts. drop_na() fuction is to drop rows that contain missing values. The geom_line() function is used to put a line in between of each point.

<img width="449" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/e762752f-0277-4178-9cd9-9a21a9ca7267">

The figure above shows that the wind gust speed is highest at the NW, at 98.00, and lowest at the W and N, at 13.00.

#### Analysis 3.4 –Average wind speed at 3pm when raining

<img width="432" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/46ab29fd-0763-483b-9dd6-5bef07e1acf7">

The code is used to build a boxplot graph. The x axis representing rainy and not rainy days and y representing how fast the wind speed is at 3pm. The coord_flip() function is used to rotate the graph for better view.

<img width="434" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/13375bee-ac08-4c42-b31f-37a41af73596">

The line in the box shows the average value, and the walls on the left and right show the lowest and highest values. The figure above shows that when it rains, the average wind speed is 20, which is faster than when it doesn't rain. In the same way, both the slowest and the fastest wind speeds are higher when it rains.

#### Analysis 3.5 –Wind gust direction when wind gust speed is over 50km/h while raining and identify the rain volume

<img width="440" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/5d85c9db-33b8-4215-9cca-a050352cf3d6">

This code is used to construct a scatter plot graph. The x-axis shows where wind gusts are coming from, and the y-axis shows how fast they are moving. The filter() function is used to make sure that only days when it rains are shown when the wind gust speed is over 50 km/h. The geom_point() function is used with "aes" of "size" to show how much rain there is. The coord_flip() function rotates the x and y axes to make the graph easier to read.

<img width="447" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/0a92cd5e-a174-4e0c-b8e8-cc3710abdf1b">

The above scatter plot shows that when wind gusts are over 50 km/h, the strongest gusts are in the NW and the most rain falls are in the WMW and NW.

### Question 4 Why no rain take majority in the United States?
#### Analysis 4.1 - Relationship between sunshine and evaporation

<img width="433" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/4b9d2e00-bbaf-46df-a260-5183f99c4fa6">

This code is used to construct a scatter graph to visualise whether or not the amount of sunshine has an impact on the amount of evaporation. The x axis represents the amount of sunshine, and the y axis represents the amount of evaporation.

<img width="428" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/d7b0eb26-9fcc-446f-bf2d-6182f3eb2744">

The figure above shows that the rate of evaporation tends to rise when the sunshine level is close to 10 or higher. After the sun's intensity reaches a higher level, which causes a rise in the rate of evaporation, it is likely that it will begin to rain in the United States.

#### Analysis 4.2 Relationship between sunshine and humidity

<img width="431" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/22fc3841-967e-43a1-94e0-716d6edde18b">

This code is used to construct a point graph that compares whether or not the amount of sunshine throughout the year has an influence on the humidity level. The x-axis of the graph indicate the amount of sunshine, and the y-axis will represent the humidity level at 9 a.m.

<img width="428" alt="image" src="https://github.com/AfifRifaie95/US-Weather-Pattern-Analysis-in-R/assets/159521904/2a84f461-8c57-4fd0-bb8c-54c5b195a967">

The figure above shows that when the sunshine level is close to 10 or higher, the rate of humidity tends to go down.

### Conclusion

In conclusion, I have investigated and analysed the data on the weather in the United States using a variety of methods. I did this by employing the ggplot2 tools in order to generate a visual graph and draw a conclusion. Bar charts, box plots, and scatter graphs with linear lines are representations of graphs that are used in this report. According to the data given, there are a greater number of days in the United States that do not contain rain than there are days that do contain rain. This could be many reasons and one of it is the temperatures, which impact the degree of evaporation and, as a result, cause fewer days with rain.



### References

Wickham, H., Chang, W., & Wickham, M. H. (2016). Package ‘ggplot2’. Create elegant data visualisations using the grammar of graphics. Version, 2(1), 1-189.

Dinea, E. (2021, November 24). PREDICTION OF RAIN TOMORROW IN AUSTRALIA. Jovian. Retrieved December 17, 2022, from https://jovian.ai/edaaydinea/prediction-of-raintomorrow

R Programming 101. (2021, February 2). Ggplot for plots and graphs. An introduction to data visualization using R programming [Video]. YouTube. https://www.youtube.com/watch?v=HPJn1CMvtmI&list=LL&index=6
