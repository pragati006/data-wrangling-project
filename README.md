# data-wrangling-project
## Gather data
Initial step of Data wrangling is data gathering.In this project data was gathered from different sources
Following are the source of data:
1) url - image-predictions.tsv file was downloaded from an url
2) download - twitter-archive-enhanced.csv file was downloaded
3) json - Few of the information was gather from tweeter json using the tweet id present in the above file
Pandas DataFrame was created from each source of data which would be used in the next step of Assessing
## Assess data
Data was assessed visually as well as programatically(using python info(), describle() methods)
The following quality and tidy issues were identified:
#### Quality
1) 'datetime', 'dog_stage', 'source', 'tweet_id', 'in_reply_to_status_id', and 'in_reply_to_user_id' fields have incorrect datatype
2) 'name' field with incorrect dog's name.
3) Tweets are without images
4) 'rating_numerator' and 'rating_denominator' field has incorrect values
5) Rating information is not available even in the text field .
6) Retweets info is present in the twitter_archive_df dataframe which is not required
7) '&' in 'text' field is entered as '&'.
8) source values are not readable values.
#### Tidiness
1) Join image_predictions_df and tweet_df dataframes to twitter_archive_df dataframe
2) 'stage' variable in four columns: doggo, floofer, pupper, puppo
## Clean data
Before starting the cleaning process a copy of the original dataframes were taken.
First, issues related to tidiness were handled:
1) Single variable for dog_stage was created instead of four variables
2) Other two dataframes were appended to twitter_archive_df dataframe
Then issues related to quality were handled:
1) 'datetime', 'dog_stage', 'source', 'tweet_id', 'in_reply_to_status_id', and 'in_reply_to_user_id' fields were updated with correct datatype.
2) 'name' field with incorrect dog's name were updated with correct names from the text field else written as 'NaN'
3) Tweets without images were removed
4) 'rating_numerator' and 'rating_denominator' fields were updated with correct values from the 'text' field.
5) Tweets with incorrect rating information or information not available even in the text field were removed
6) Retweets info which is not required were removed
7) '&' in 'text' fields were replaced with '&'
8) Source values were updated to a more readable value.
## Store data
Before analysing the data, the dataframe was stored in a file called 'twitter_archive_master.csv'
## Analyze data
Initially a new dataframe was created with only few fields required for analysis.
Following are the fields of interest for analysis:
1) Source field : Count of entries for each source was plotted.
2) retweet_count: Count of retweet over a period of time was plotted.
3) favorite_count: Count of favorites over a period of time was plotted.
4) rating_numerator and rating_denominator: rating ratio was calculated and plotted over a period of time.
