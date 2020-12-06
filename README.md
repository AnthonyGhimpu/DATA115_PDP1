# Personal-dataset-Project

# Motivation
-The question that I set out to answer would be my personal wonder if the amount of extremely high temperatures in each county in Washington has any relationship with wildfires that took place in our state from 2009 - 2013. I chose to go with two datasets from thee Washington State Department of Health and went with the # of extreme hot days in each county as well as the # of wildfires in each county from 2009 - 2013. Oregon's wildfires that happened in September made me curious on the causes of wildfires in general, and if the global climate has anything to do with it, more specifically, the amount of extremely hot days. I decided to use our local data from our state to see if there is any relationship between the two variables, and if they correlate.  

# Data Sources
I combined two datasets from the Washington State Department of Health website and stumbled upon groupings for the # of extremely hot days per census block from 2009 - 2013 and the amount of wildfires in each county from 2009 - 2013. The derivation for the # of extremely hot days is based on the "number of days each year from 2000 onward that the maximum temperature exceeded the 99th percentile threshold at each station." The derivation for the # of wildfires is just the sum of all the wildfires that have occured in each county. I downloaded 5 different datasets per year for the # of extremely hot days  and 5 dataset for wildfires per county (all merged), all fitting within the yearly parameters. 

# Processing Steps
I gathered all of the data sets for five different datasets per year for the # of ectremely got days per year from 2009-2013 and they were all merged into one .csv file. I looked over the datasets by skiming all of the entries and tried to make sense on how the data is split. Since they are all split into census blocks, I had to use a method of making the data more comprehensible and more comparable to the # of wildfires data, as that dataset is split up by just county names and not census blocks. The steps that I needed to take for the census blocks was to use the groupby() function and aggregating the data by just county name and taking the mean of all of the amount of hot days over the amount of census blocks per county. I could not just sum every day up for each county, because that brings innaccurate results. The raw and processed data for extremely hot days consist of all five datasets and grouped county name with mean respectively. For the second dataset (# of wildfires) raw data consisted of also five data sets merged together for each year from 2009-2013 and has repeated county names, # of burned acres, # of fires, and percent area burned. For the processed data, I just decided to use one column, and the one I chose would be the number of fires. On the python notebook, I decided to use the same strategy of processing the data so it fits with the comparison of the other dataset by using the groupby() function for the county names, as well as aggragating # of fires burned by mean as well, to make the data more comparable to the other dataset given. The last step that I took would be merging both columns together, (avg # of extremely hot days and avg # of fires burned) making it easier to apply certain analytical tools to the new, trimmed dataset.

![main](https://user-images.githubusercontent.com/72293385/101267493-2e40ca80-370e-11eb-9b42-5131d6d479e4.PNG)

# Visualization
For my main visualization, I decided to go with a scatterplot in order to see the distribution and clustering of the two variables. I also added a line of best fit in oder to get a better idea of the trend that the scatterplot has, and also show the correlation that the dataset has. This result did not fit my hypothesis, as the trend seems to be negative and consist of a lot of marginal data points on the x-axis. The slope of the line is -0.18 AKA the correlation, meaning, the two variables don't really have a link with each other, and this might be a sort of generalization error, which might need more analysis that is more in depth.

![Main_Visualization](https://user-images.githubusercontent.com/72293385/101267880-a3ae9a00-3712-11eb-8146-ab4954e0d5b5.PNG)

# Analysis
With the results that I got from the main visualization scatterplot, I decided to come up with a different approach in analyzing the data that I have. I decided to split the data up into three different dataframes in order to come up with a more specific conclusion of the data. 

![SplitPy](https://user-images.githubusercontent.com/72293385/101268207-7e6f5b00-3715-11eb-8b84-2a2fc108339b.PNG)

The catagorical way I split the data up would be all three regions in Washington, and the counties that lay in the Western, Central, and Eastern parts of the state. I then calculated the correlations and made corresponding scatterplots with line of best fit for each region...

![WesternWa](https://user-images.githubusercontent.com/72293385/101268299-4d435a80-3716-11eb-93bf-fc9ac0350f36.PNG)

Western Washington seems to have a positive trend with not that much significance due to the many marginal points that lie on the x-axis, derouting the line of best fit, and making it flatter. Many of the counties in the Western region have a good portion of extremely got days, but there seems to not be as many # of fires, influencing the result given. There could be many explanations to this, such as more humid weather because of the coast or other reasons for why this visualization is the way it is.

![CentralWa](https://user-images.githubusercontent.com/72293385/101268302-503e4b00-3716-11eb-8948-d2a345c59e41.PNG)

Central Washington has a stronger positive trend, but that may be because that there are not as many counties in Central Washington than the other split datasets. However, it could potentially make for other stronger conclusions if more information is given for this region.

![EasternWa](https://user-images.githubusercontent.com/72293385/101268301-4e748780-3716-11eb-886b-4299804144f5.PNG)

Eastern Washington has a negative trend, but again, it is not enough to come up with an accurate conclusion as many of the data points are marginalized on the x-axis. 

Overall, I think many of these split datasets can say a lot when it comes to the gernalization aspect in each set, as each region has different settings, such as amount of trees, and the levels of humidity that can influence the # of fires in each region. The use of more data would be a better solution in coming up with a more accurate conclusion.


