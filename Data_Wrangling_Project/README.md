# (WeRateDogs Twitter Data Visualization)
## by (Martin Ikpe)


## WeRateDogs Twitter Dataset
INTRODUCTION:

The dataset that we will be wrangling (and analyzing and visualizing) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.

DATA GATHERING: Data gathering involves searching and genrating data across several different sources and file formats and organize the data in your programming environment. Below are the various files gathered from sources for this Project:

Twitter_archive_enhanced.csv: This file was downloaded from Udacity's server by manually clicking on the download button. It was upaded to the Jupyter Notebook Workspace and read into a pandas Dataframe.

Image_predictions.tsv: This file was downloaded programmatically using the Requests library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv and was read into the pandas dataframe.

Tweet_json.text: This file was meant to be gotten from Twitter API, query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file. However, it was downloaded programmatically using the Requests library and the following URL:https://video.udacity-data.com/topher/2018/November/5be5fb7d_tweet-json/tweet-json.txt from Udacity's server due to issue encountered signung up the twitter account. The tweet_id, retweet_count and the favorite_count were read line by line into a pandas DataFrame.

Assessing Data: This involes inspecting the dataset for Data quality issues (i.e. issue with the content) and Lack of tidiness(i.e structural issues). The below issues were detect visually by scrolling through the dataset and programmatically by using code:

Quality issues

1.Using original twitter_archive Data and not retweeted data

2.Missing Data (in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp)

3.p1/p2/p3 columns has incorrect formating (some starts with capital letter while other starts with smaller)

4.Inconsistent decimal places or precision values

5.Ratings datatype should be float not integer (rating_numerator and rating_denominator)

6.Dividing the rating_numerator by rating_denominator to form the rating column

7.Inaccurate name column (a, an, all, the, this, by, not, such)

8.Erroneous Datatype (timestamp)

9.Changing the tweet_id datatype from integer to object since it won't be use for calculations

Tidiness issues

1.splitted Dog stage into four columns instead one column (doggo, floofer, pupper, puppo). 2.Merge the twitter_archive Dataframe with image_pred Dataframe.

Cleaning Data: This involes fixing the quality and tidiness issues detected during Data assessment. Below are the steps taken to fix the issues:

Quality issues

Dropping all retweeted Data to avoid duplicates
Dropping the columns in twitter_clean dataframe with missing values as the are no going to be useful
Converting the p1/p2/p3 to Title case
Converting the values to 8 decimal places for consistency
Converting the rating_numerator and rating_denominator to float datatype.
Dividing the rating_numerator by the rating_denominator and assigning the value to a new column rating
Dropping words that are not Dog names which are in small letters
Converting assigned timestamp column from object datatype to datetime datatype.
Changing the tweet_id datatype from integer to object
Tidiness issues

Combining doggo, floofer, pupper and puppo clumns into one column called dog_stage
Merging the twitter_archive Dataframe with image_pred Dataframe.
The cleaned Dataset was stored in a different file called twitter_archive_master.csv for data analysis and visualization.


## Summary of Findings

A thorough investigations were carried out and we were able to get some insight into the dataset. 
We have more Pupper stage Dogs than others.
The Pupper stage Dogs were rated more than other dog's stage.
The Puppo stage Dogs were most people favourites than others.
Findings from the Chart:
1. The Pie Chart shows the total number of ratings received by these stages.The Pupper (youngest) Stage recieved the largest number of tweet counts, followed by Doggo (The more experienced and oldest), Puppo (the teenage/older dog), and Floofer (Dogs with excessive Fur).
2. The Bar Chart shows us the Dogs with the best ratings in each of these four dog stages. A Dog in Pupper stage got the highest rating of about 2.7 rating, followed by two other Dogs with the same rating of 1.4 each, one from Doggo and the other from puppo. The last is another Dog from Floofer stage with rating of 1.3.
3. The Puppo stage Dogs are the most favorite Dogs as the have the largest favorite counts, followed by the Doggo, Pupper and Floofer. This means that people prefers the Puppo stage Dogs to every other Dog stages.
4. There was a correlation between the first and the second algorithms used to predict if an images tweeted belongs to a paricular Dog's breed or not. The confident level (the level at which we are rest assured that the image is a dog breed)for the first algorithm is 95% while the confident level for the second is 1%.
As first algorithm tends to its confident level of 95%, the second algorithm moves away from itsconfidence level of 1%. And as the second algorithm approaches its confident level the first moves away from its confident level.
