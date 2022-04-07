
# Part A 
# Top 10 Economies in the World
### Project definition 

This is a project about extracting data from an API and compiling it into a CSV file for data analysis. 

###Data Extraction 

For this project, my group and I decided to scrape data from Investopedia.com and investigate the countries that have the best economies in the world. We used *BeautifulSoup* to parse data and decided to focus on the top 10 countries to give our readers a more simplified and organized view to compare the top 10 countries and their economical data by way of a dataframe. We also used *Pandas* to convert the list of dictionaries that we obtained from our data extration  into a table. We took our final results and exported them into a *CSV file*.

#Part B 
#Annual Subway Ridership in NYC - 2019 vs. 2020
###Project definition 

My team an I chose to analyze the dataset of Annual Subway Ridership in NYC, specifically focusing on the data between 2019 and 2020 and taking a look at the major components and variables that could be the reason behind any major discrepancies or decreasing behaviors across subway ridership between the two years given the start of the pandemic in 2020.

### Libraries and data analysis. 

We used the following libraries: 
1. *pandas* library to work with out table data. 
2. *numpy* library to work with our numerical data. 
3. *matplotlib.pyplot* library to create our plots. 
4. *seaborn* library to create our plots. 

We found our data set in the MTA of NYC website here: https://new.mta.info/agency/new-york-city-transit/subway-bus-ridership-2020 and downloaded it as a CSV to use the data for this project. We then proceeded to create our data frame which we called `read_data` to remove the white space from the fields : `'Station', 'Boro','2015','2016', '2017', '2018','2019', '2020','2019-2020 Change', '2019-2020 Change %'`
 
After doing this we looked for empty cells but we didn't had any using the following code `df.isna().sum()` and then we went on to looking for the unique station names in NYC and noticed that all the stations are unique and the total amount of stations is 424 using the following code `df.Station.value_counts()`. We also saw by using `df.Boro.value_counts()` that Brooklyn is the borough with the most stations at 157 stations, followed by Manhattan with 121 stations, Queens with 78 stations and lastly The Bronx with 68 stations, these findings we were able to plot by using the *seaborn* package in a bar chart for ease of interpretation. 

![alt text](https://github.com/mariapereyras/analysis-world-economies-/blob/main/images%20/BarPlot.png "Hello")


We also found by using `df.describe()` the summary of the most important metrics for the subway riders data per year and were able to obtain the mean, min, max, etc., to interprete this data easily we plotted a scatterplot by borough with the values from 2019 - 2020 percentage change, from this plot we can interprete that Queens had the most prominent change if rider counts across all its stations with a 0.46% change in ridership from 2019 to 2020 and Brooklyn with a -0.85% change in ridership from 2019 to 2020. 

![alt text](https://github.com/mariapereyras/analysis-world-economies-/blob/main/images%20/Scatterplot.png "Hello")


lastly, we calculated the riders per borough in 2019 by using a lambda function: 
`g = data.groupby('Boro')`
`g.apply(lambda x: x[x['Boro'] == 'Bx']['2019'].sum())`
and the max riders in 2020 to calculate the percentile change in ridership. We found that the change between the max amount of riders in these 2 years was -68% in any given station. We also looked for the percentage change to compare the 2 years and the difference was minimal at -0.062%. 

### Conclusion 

Given that the difference of annual ridership between 2018 and 2019 was so insignificant, and no variable stuck out as being a deciding factor in total annual counts, we believe that the reason there was such a decrease between 2019 and 2020 was due to Covid, where the majority of usual annual subway riders were now staying home more frequently.


