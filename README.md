# Personal-dataset-Project

# Motivation
The question that I set out to answer would be whether the amount of too high temperatures in each county in Washington has any relationship with wildfires in our state from 2009 - 2013. I chose to go with two datasets from the Washington State Department of Health and went with the # of extremely hot days in each county and the # of wildfires in each county from 2009 - 2013. Oregon's wildfires that happened in September made me curious about the causes of wildfires in general. Suppose the global climate has anything to do with it, precisely the amount of extremely hot days. I decided to use our local data from our state to see any relationship between the two variables and their correlation.  

# Data Sources
I combined two datasets from the [Washington State Department of Health](https://www.doh.wa.gov/) website and stumbled upon groupings for the [# of extremely hot days per census block](https://fortress.wa.gov/doh/wtn/WTNPortal/#!q0=1019) from 2009 - 2013 and the number of [wildfires](https://fortress.wa.gov/doh/wtn/WTNPortal/#!q0=3586) in each county from 2009 - 2013. The derivation for the # of extremely hot days comes from the "number of days each year from 2000 onward that the maximum temperature exceeded the 99th percentile threshold at each station."(DOH) The derivation for the # of wildfires is just the sum of all the wildfires in each county. I downloaded five different datasets per year for the # of extremely hot days and five datasets for wildfires per county (all merged), all fitting within the yearly parameters. 

# Processing Steps
I gathered all of the five different data sets for the # of extremely hot days per year from 2009-2013, and they were all merged into one .csv file. I looked over the datasets by skimming all of the entries and tried to make sense of how the data is split. Since they are all split into census blocks, I had to make the data more comprehensible and more comparable to the # of wildfires data, as that dataset is split up by just county names and not census blocks. I needed to take the census blocks' steps to use the groupby() function and aggregating the data by just county name and taking the mean of all of the number of hot days over the number of census blocks per county. I could not just sum every day up for each county because that brings inaccurate results. The raw and processed data for extremely hot days consist of all five datasets and grouped county names with mean. For the second dataset (# of wildfires), raw data consisted of five data sets merged for each year from 2009-2013 and has repeated county names, # of burned acres, # of fires, and percent area burned. For the processed data, I just decided to use one column, and the one I chose would be the number of fires. On the python notebook, I decided to use the same strategy of processing the data, so it fits with the comparison of the other dataset by using the groupby() function for the county names, as well as aggregating # of fires burned by mean as well, to make the data more comparable to the other dataset given. The last step that I took would be merging both columns (avg # of extremely hot days and avg # of fires burned), making it easier to apply specific analytical tools to the new, trimmed dataset.

![main](https://user-images.githubusercontent.com/72293385/101267493-2e40ca80-370e-11eb-9b42-5131d6d479e4.PNG)

# Visualization
For my main visualization, I decided to go with a scatterplot to see the distribution and clustering of the two variables. I also added a line of best fit to get a better idea of the trend that the scatterplot has and show the correlation that the dataset has. This result did not fit my hypothesis of having a positive trend, as the trend seems to be negative and consists of a lot of marginal data points on the x-axis. The slope of the line is -0.18, AKA the correlation, meaning the two variables do not have a link with each other, and this might be a sort of generalization error, which might need more analysis more in-depth.

![Main_Visualization](https://user-images.githubusercontent.com/72293385/101267880-a3ae9a00-3712-11eb-8146-ab4954e0d5b5.PNG)

# Analysis
With the results that I got from the main visualization scatterplot, I decided to develop a different approach in analyzing the data that I have. I decided to split the data up into three different data frames to come up with a more specific conclusion of the data. 

![SplitPy](https://user-images.githubusercontent.com/72293385/101268207-7e6f5b00-3715-11eb-8b84-2a2fc108339b.PNG)

The categorical way I split the data up would be all three regions in Washington and the counties in the Western, Central, and Eastern parts of the state. I then calculated the correlations and made corresponding scatterplots with the line of best fit for each region...

![WesternWa](https://user-images.githubusercontent.com/72293385/101268299-4d435a80-3716-11eb-93bf-fc9ac0350f36.PNG)

Western Washington seems to have a positive trend with not that much significance due to the many marginal points that lie on the x-axis, rerouting the line of best fit, and making it flatter. Many Western region counties have a good portion of extremely hot days, but there seems not to be as many # of fires, influencing the result given. There could be many explanations for this, such as more humid weather because of the coast or other reasons for why this visualization is the way it is.

![CentralWa](https://user-images.githubusercontent.com/72293385/101268302-503e4b00-3716-11eb-8948-d2a345c59e41.PNG)

Central Washington has a stronger positive trend, but that may be because there are not as many Central Washington counties as the other split datasets. However, it could potentially make for other, more robust conclusions if more information is given for this region.

![EasternWa](https://user-images.githubusercontent.com/72293385/101268301-4e748780-3716-11eb-886b-4299804144f5.PNG)

Eastern Washington has a negative trend, but again, it is not enough to come up with an accurate conclusion as many of the data points are marginalized on the x-axis. 

Overall, I think many of these split datasets can say a lot regarding each set's generalization aspect. Each region has different settings, such as the number of trees and the humidity levels that can influence the # of fires in each region. The use of more data would be a better solution in coming up with a more accurate conclusion.

# Descriptions of Code and Materials
The raw data was collected from the sources described above and are uploaded in .csv form as Extremely_Hot_Days 2009-2013 and Wildfires_09-13. The processed data consists of relevant columns and county names by grouping as main.csv. The notebook used to make all of the visualizations and processing is uploaded as Personal Dataset Project Visualization.ipynb.

