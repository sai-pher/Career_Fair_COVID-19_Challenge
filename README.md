# Problem Description

At the end of December 2019, there were reports of an acute respiratory syndrome in the Chinese Wuhan municipality.  
The outbreak spread quickly to other parts of China as well as to other countries in Asia, Australia, Europe, North America and Africa.  
In February, the novel coronavirus was named severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2) and the disease associated with it is now referred to as COVID-19.  
Since 31 December 2019 and as of 4 March 2020, 93,076 cases of COVID-19 have been reported, including 3,202 deaths.  
The outbreak is still rapidly evolving.  
For comparison, in the 2014-2015 Ebola outbreak in West Africa, over 28,000 cases were reported and more than 11,000 people were reported to have died of the disease.

In this coding challenge, you will process some data related to the ongoing COVID-19 outbreak.

## Task 1 
You have been provided with a log file (in CSV format) of data on the number of newly confirmed cases and deaths of COVID-19 by country and by date since December 2019.  
You have also been provided with a log file (in CSV format) of population data of countries.  
You are to write a programme which determines answers to the following questions:

1.	Which country has the highest number of infections to date?  How many infections have been recorded in that country?
2.	Which country has the second highest number of infections to date? How many infections have been recorded in that country?
3.	Which country has the highest infection rate (ratio of number of infections to population) to date?  What is the infection rate?
4.	What is the overall death rate (ratio of number of deaths to number of infections) for COVID-19?
5.	Which country has the highest death rate (ratio of number of deaths to number of infections)?  What is the death rate for that country?
6.	In which countries is the number of new infections per day on the rise (i.e. a positive trend over the most recent 1 week of data)?  
7.	Of the countries above (from f), which country has the steepest increase?
8.	In which countries is the number of new infections per day decreasing (i.e. a negative trend over the most recent 1 week of data)? 
9.	Of the countries above (from h), which country has the steepest decrease?
10.	Of the countries above (from h), for which country did the number of infections per day peak the earliest?  
When did the number of infections per day peak, for this country?

## Task 2
You have been given a third file with a list of time series data corresponding to a portion of one of the country’s new confirmed cases data.  
However, the data is not labelled so you do not know which country the data corresponds to, or what dates it corresponds to.  
Write a programme to determine which country the data corresponds to, and what the starting date of the data is.

Note that, for both tasks, your program will be tested with different data from what has been provided to you.  
As such, it is important that you write your program such that it adheres to the guidelines described in this document, 
so that your code can be run with a different input file without re-compiling your code.

# Program Execution Specifications
Your programs can be written in either Python or Java.  In either case, you should write your program such that it can be executed from the command-line, taking the filenames as command-line parameters.

For task 1, your programme should be run from the command line as follows:
`<interpreter> <programme> <covid_data> <population_data>`

|where: | |
|---| ---|
|`<interpreter>`| 	is the name of the Python interpreter or Java interpreter,|
|`<programme>`| 	is the name of your programme,|
|`<covid_data>`| 	is the name of the file containing the time series data of Covid cases and deaths by country, and|
|`<population_data>`| 	is the name of the file containing the population of various countries| 

For task 2, your programme should be run from the command line as follows:
`<interpreter> <programme_name> <covid_data> <partial_time_series>`

where the first two parameters have the same meaning as above, and

| | |
|---| ---|
|`<covid_data>`| 	is the name of the file containing the time series data of Covid cases and deaths by country, and|
|`<partial_time_series_file>`| contains the partial time series data that you are trying to match to the data in the <covid_data> file.|

The format of the input files are described in the next section.

Your programme should write its results to an output file whose format is described later in this document.

## Input File Formats

All input files are CSV (comma-separate-value) files.  
Note that CSV files are simply plain text files in which the data values on each line are separated by commas. 
 You can read such files in your Java or Python program like you would read any text file.  
 You can view such files with a text editor (such as Notepad).  
 You can also use Excel to view such files in a nice tabular format.

The `covid_data` file is structured as follows: 
-	Line 1 has the column headers
-	Line 2 onwards has the data.  The columns are as follows
    
    1.	DateRep – the date
    2.	CountryExp – the name of the country. All the data is linked with a specific country, with one exception described as “Cases on an international conveyance Japan”.  
    3.	NewConfCases – the number of new confirmed cases of COVID-19 on that date in that country.
    4.	NewDeaths – the number of deaths due to COVID-19 on that date in that country.
    5.	GeoId – a code representing the country

The population_data file is structured as follows: 
•	Line 1 has the column headers
•	Line 2 onwards has the data.  The columns are as follows:
1.	Country – the country
2.	Country_Code – A code for the country
3.	Population – the population of the country
4.	Year – the year that the population data dates from

For task 2, the partial time series file also has a .csv extension, but it has only one column of data, representing the number of newly confirmed cases of COVID-19 in an unspecified country, for an unspecified period of time. 

Note that the data files provided are simply samples.  Your code will be tested on these and other data files with the same format, but which could have fewer or more data points than the sample input files that have been provided.  As such, you need to write your code to be general enough to work with any number of rows of data.

