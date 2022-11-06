# Use of Web-Scraping Techniques to Capture Mars News and Weather Data

## Overview
Web-scraping, in general, is the process of extracting information from websites for the purposes of conducting analysis.  Using Jupyter Notebook in conjunction with python and the “splinter” and “beautiful soup” modules, it is possible to write code that will control a web browser and automate the web-scraping process.  The purpose of this analysis was to automated web-scraping techniques to perform two different tasks.  The first task was to “scrape” the most recent news articles and summaries from redplanetscience.com and place the “scraped” data into a Python formatted list of dictionaries.  The second task was to “scrape” Mars weather data acquired by the Mars Curiosity Rover into a Pandas DataFrame for purpose of conducting further analysis.

## Results
Using python in a Jupyter Notebook in conjunction with the “splinter” and “beautiful soup” modules, a for loop was used to scrape the “title” and article “preview” information for the most recent news articles from redplanetscience.com and place the information in a list of dictionaries (See Figure 1). 

![]( https://github.com/Scruffy-Bearie/mars_challenge/blob/main/IMAGES/Fig1.png)

Using in a Jupyter Notebook in conjunction with the “pandas” module, it was possible to “scrape” weather data accumulated by the Mars Curiosity Rover into a Pandas DataFrame.  Once the scraped information was in a DataFrame, it was possible to use the “groupby” function to determine the number of months on the Martian Calendar and the “mean” function to determine the “Average Daily Minimum Temperature” and “Average Daily Pressure” for each month (See Figure 2).

![]( https://github.com/Scruffy-Bearie/mars_challenge/blob/main/IMAGES/Fig2.png)

With the data formatted as described above, it was possible to use the “matplotlib” module to produce bar graphs to plot both “Average Daily Minimum Temperature” and “Average Daily Pressure” as a function of Martian “month” for the sake of further analysis (See Figures 3 and 4 respectively).

### Figure 3: Mars Average Daily Minimum Temperature as a Function of Month
![]( https://github.com/Scruffy-Bearie/mars_challenge/blob/main/IMAGES/Fig3.png)

### Figure 4: Mars Average Daily Pressure as a Function of Month
![]( https://github.com/Scruffy-Bearie/mars_challenge/blob/main/IMAGES/Fig4.png)

Finally, the “terrestrial_date” column in the original DataFrame was converted to “datetime” format using the “datetime” module so that “daily minimum temperature” could be plotted as a function of “terrestrial date” for the sake of arriving at an estimate of the length of the Martian year as measured in Terran (Earth) Days (See Figure 5).

### Figure 5: Mars Minimum Daily Temperature as a Function of Terrestrial Date
![]( https://github.com/Scruffy-Bearie/mars_challenge/blob/main/IMAGES/Fig5.png)

## Analysis
### (i)	Number of Months in the Martian Year
Once the “scraped” weather data was placed into a pandas DataFrame and the “groupby” function was employed (See Figure 2), it was possible to determine that there are 12 months on the Martian calendar.

### (ii)	Number of Martian Days in the Data Set
According the information provided, the “sol” column in the original data set is the number of Martian days elapsed since the Curiosity Rover landed on Mars.  Given that there is 1 entry per day, the number of days worth of data in the data set is equal to the number of rows, or 1867.  However, the data set also indicates the first entry was made on “sol = 10” and the last entry was on “sol = 1977” meaning that a total of 1967 Martian days elapsed while data was being collected and that there were 100 days on which data was not collected.

### (iii)	Coldest and Warmest Months on Mars
Inspection of the “Average Minimum Daily Temperature as a Function of Month” plot (see Figure 3) made it possible to determine that the third month (Month 3) is the coldest month on Mars (lowest average minimum daily temperature  = -83.3 ⁰C) and that the eight month (Month 8) is the warmest month on Mars (highest average daily minimum temperature = -68.4⁰C).

### (iv)	Months With the Lowest and Highest Pressure
Inspection of the “Average Daily Pressure as a Function of Month” plot (see Figure 4) made it possible to determine that the ninth month (Month 9) has the highest average daily pressure (913.3) and that the sixth month (Month 6) has the lowest average daily pressure (745.1).

### (v)	Number of Terrestrial Days in a Martian Year
Assuming that Mars experiences seasons similar to Earth in a cyclical fashion, examination of the “Mars Minimum Daily Temperature as a Function of Terrestrial Date” plot (see Figure 5) made it possible to see that if Oct 1st 2012 was selected as a starting point (minimum daily temperature of approximately -75⁰C), that a fully cyclical pattern (or return to the same daily minimum temperature after 4 seasons) had occurred by Aug 1st 2014.  The total number of (terrestrial) days elapsed during this period is 669 meaning that the estimated length of the Martian year was found to be 669 terrestrial days.  This value compared favourably with the accepted value of 687 representing a 2.6% margin of error. 
