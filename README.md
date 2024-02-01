# Using NLP to Distinguish Between Two Gaming Subreddits

## Data Used

overwatch.csv - Data from Overwatch subreddit\
apexlegends.csv - Data from apexlegends subreddit\
subredditdata.csv - Merged dataset from both subreddits

## Problem Statement

Those who game online, generally speaking, like to compare gaming communities. Two popular games with fairly active communities are Overwatch and Apex Legends. A group of friends who play both games have asked you as a data scientist to create a model that will be able to predict what community made a post based on what the post says so that they can look at its predictions in between games. 

## Data Dictionary

|Feature|Type|Description|
|---|---|---|
|title|string|Title of the post|
|selftext|string|Full-length text of the post|
|subreddit|string|Name of the subreddit where the post came from|
|created_utc|float|Time when the post was created|
|name|string|Name of the user that created the post|
|overwatch|boolean|Determines whether post was in positive class "overwatch" or not|

## Modeling Summary

The feature used to predict what subreddit each post is from was selftext. This was used due to its significantly greater mean string length, which helped to provide more datapoints with which to help classify the data. There were some high-occurring words in the selftext data, but this did not prove to harm the accuracy of the models. The data was transformed using two different methods (Count Vectorizer and TF-IDF Vectorizer) and input into two different models (Logistic Regression and Multinomial Naive Bayes) in order to test which model provided the most reliable predictions.

## Conclusions

While all of the models beat the baseline accuracy score, the model that predicted the subreddits of the posts best was the Logistic Regression model with data transformed with the TF-IDF Vectorizer method. Overall, all of the models were more likely to predict something would be in the Apex Legends subreddit when it was actually in the Overwatch subreddit, but not to predict that something would be in the Overwatch subreddit when it was actually in the Apex Legends subreddit. Ultimately, the final model predicts the subreddit where a post came from only about 65% of the time, which is fairly low, but this is likely due to a high rate of similar words being used and users not using a particularly high number of words unique to each game in their posts and the games being similar in style and community.