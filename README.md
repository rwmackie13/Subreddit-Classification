# Project 3 - Web APIs and NLP

**Problem**

Using reddit, scrape posts from two subreddits in order to classify which subreddit the post is from. I chose the r/nfl andr/CFB subreddits as they are two of the most heavily used subs and there will be plenty of dataa we can gather.  Hopefully the results of this project can help users decide which sub to submit to if their post is caught in between r/nfl and r/CFB.

## Executive Summary

**Contents:**

[Data Scraping](http://localhost:8888/lab/tree/Documents/DSI_coursework/Submissions/Projects/project_3-master/01_Data_Scraping.ipynb)
 - Used pushshift.io API to collect data
 - Limited to 100 posts per request
 - Collected 2,000 posts from each subreddit

[Data Cleaning](http://localhost:8888/lab/tree/Documents/DSI_coursework/Submissions/Projects/project_3-master/02_Data_Cleaning.ipynb)
 - Checked for nulls in our dataframe
 - Checkd for duplicates among our posts
 - Combined our cfb and nfl dataframes and binarized our target variable

[Pre-Processing and Modeling](http://localhost:8888/lab/tree/Documents/DSI_coursework/Submissions/Projects/project_3-master/03_Pre_Processing.ipynb)
 - Multinomial Naive Bayes, Single Decision Tree, Random Forest, and SVM models were tested using gridsearch with both CountVectorizer and TfidfVectorizer

## Conclusion

**Findings**

- I found the simple naive bayes to produce the best results out of the models tested. Using CountVectorizer and MultinomialNB, I achieved the best accuracy scores (train / test scores: 0.9743 / 0.933).

- Support Vector Machines improved the most with the addition of unique stopwords (up from ~.88 to ~.93 - I would like to test this model out with more stopwords removed(only added 5 to the default) and certain special characters in place as well as testing different specific parameters.

**Model Improvements** 

- Collecting more training data should help some of the overfit in the models.  Did notice some cross-posting in the subreddits (posts being shared in each of r/CFB and r/nfl) - I fortunately did not really run into this issue with the data that was scraped, but can see this being an issue with a larger dataset.

- Editing our stopwords to remove additional words that are not unique to each subreddit should improve our scores as well as testing out more specific gridsearch parameters for each model.  
