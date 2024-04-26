# Meteorological Data Analysis in R

It can also be termed as weather analysis.

![rain4-1-620x370](https://github.com/AfifRifaie95/R---US-Weather-Pattern-Analysis/assets/159521904/55b6f861-3101-4bb6-bd94-c2d4847f38bf)

### Project Overview

The purpose of this report is to investigate and analyse weather data from the United States. It begins with performing data importing, data exploration, data cleaning and data pre-processing, followed by investigation and visualisation into a visual graph using R Studio.


### Data Source

The dataset is obained from Kaggle [Available Here](https://www.kaggle.com/datasets/zaraavagyan/weathercsv)

### Software

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










### References

<img width="527" alt="Screenshot 2024-03-21 111639" src="https://github.com/AfifRifaie95/R---US-Weather-Pattern-Analysis/assets/159521904/9cb3634d-08d1-43f3-8dc6-2b58842dddb4">

<img width="448" alt="Screenshot 2024-03-21 111455" src="https://github.com/AfifRifaie95/R---US-Weather-Pattern-Analysis/assets/159521904/1b8ea6fc-d5e9-4a9c-9ccf-8723189c98d3">


I use bar charts, box plots, scatter graphs with linear lines, and other charts as representations of graphs.


<img width="516" alt="Screenshot 2024-03-21 112044" src="https://github.com/AfifRifaie95/R---US-Weather-Pattern-Analysis/assets/159521904/694c4697-f2be-4e9e-8f0f-717d87758ef3">

<img width="526" alt="Screenshot 2024-03-21 112520" src="https://github.com/AfifRifaie95/R---US-Weather-Pattern-Analysis/assets/159521904/784f2e08-8eb5-4373-aa23-847912e45531">



Full PDF report available here,

https://shorturl.at/qsFOR [Shortcut to GitHub file]

