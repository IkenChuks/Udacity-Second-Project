# Udacity-Second-Project

## Data Wrangling
## WRANGLE ANALYSIS REPORT: 'WERATEDOGS'

> My goal in this project was to wrangle 'WeRateDogs' twitter data in order to deliver more accurate analyses, assessments, conclusions and visualizations.
My data wrangling process can be highlighted under the following headers:
data gathering
data assessment
data cleaning
data re-purposing

> I was given 3 datasets to work with: 'Enhanced Twitter Archive', 'Image Prediction File' and 'Additional Data via Twitter API'.
The data gathering stage involved extracting the required data from each of these files using techniques specific to each file type and source.

> For the 'Enhanced Twitter Archive' which was given as a csv(comma separated value) file, we simply imported pandas and read the data into a dataframe df_1. For the 'Image Prediction File', the 'requests' library had to be imported as well as 'os' in order to read the data of the 'image prediction' tsv(tab separated value) file from the url given. The additional twitter API was queried by importing 'tweepy' and the resulting json data was read into dataframe df_3.

> Each of the dataframes df_1, df_2 and df_3 were assessed to determine quality and tidiness issues. Specifically, missing values, data types, data frame structures, capitalization issues, wrong entries, et cetera, were investigated in each dataframe and I came up with 8 quality issues and 2 tidiness issues. The .info(), .sample(), .value_counts() and isnull() methods were invaluable to my assessment at this point.

> On identifying the issues, cleaning proceeded with dfcop_1-a copy of df_1 (copies of all data frames were created: dfcop_1, dfcop_2 and dfcop_3 for the cleaning process). Assessment showed that some 'name' entries were entered as a letter or 2. These were replaced with 'None'. The 'timestamp' column was in string datatype and this was changed to datetime format using panda's .to_datetime() method. For more compatibility of this method, the 'timestamp' column was first stripped of unnecessary data '+0000'.

> Dfcop_2 had capitalization inconsistency and unwanted character(underscore) issues which were easily removed from its dog breed columns 'p1', 'p2' and 'p3' using .capitalize() and .replace() methods respectively.Dfcop_3 had to be narrowed down to seldf_3 dataframe which is the filtered dfcop_3 for more selective useful information. The selected columns had to be named, unwanted characters(commas) had to be removed from entries and 'retweet_count' and 'favorite_count' entries had to have their data type changed from string to integers. These were all successfully done adopting the required methods and procedures.

> Structurally, we identified 2 issues(tidiness issues) in dfcop_1 and dfcop_3. Columns 'doggo', 'floofer', 'pupper' and 'puppo' all represented dog stages and yet each occupied a column in the dataframe dfcop_1. We adopted the .melt() function to merge all the columns into 2 called 'dog_stage' and 'dog_stage_result', which mention the dog stage and determine if true, false or none respectively. For dfcop_3 tidiness issue, we discovered that most columns were redundant and typically contained the required information in their adjacent columns. Hence, entries were appropriately selected with code.

> Finally, all useful data frame information were merged using dfcop_1, dfcop_2 and seldf_3 to give our master dataframe 'twitter_archive_master'. This was read into a csv file of the same name using the .to_csv() method. I concluded by re-purposing the master dataframe to give my insights on the project; and plotted a graph showing the seemingly proportional relationship between favorite count and retweet count.
