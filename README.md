## What's Up With Kanye West?
Originially I wanted to take Kanye's tweets from 2010 to 2012 and use that for the "old_kanye" data set and use tweets from 2017 to present for the "current_kanye" data set but Kanye is Kanye and deletes his tweets all the time so the oldest tweets I can extract are from early April 2018 and one tweet from 2014. So I will just have to run a sentiment analysis on the data I have and won't be able to compare old and new tweets

### Method:
1. I'm going to extract Kanye's tweets and insert them in a table in a mysql database
    (json, tweepy, mysql_connector)
2. Query specific data to make my data set
    (pandas, mysql_connector)
3. Clean the data
    (pandas, nltk, bs4, re)
4. Calculate Sentiment Values
    (textblob)
5. Visualize the data
    (wordcloud, sklearn, pyplot, matplotlib)
6. Asess the data

### Tools:
### To extract Data from Twitter:
- tweepy: twitters API that allows me to grab tweets
- json: allows me to change the extract tweets, which comes in "tweepy.models.ResultSet", then dumps it into a
  json string, then loads it into a list of dictionaries (each dictionary is a tweet containing a Tweet Object)
  
  "The Tweet object has a long list of ‘root-level’ attributes, including fundamental attributes such as 'id',
  'created_at', and 'text'. Tweet objects are also the ‘parent’ object to several child objects. Tweet child
  objects include user, entities, and extended_entities. Tweets that are geo-tagged will have a place child
  object."
  https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object.html
  
#### To Store Data:
- mysql: allows me to connect to database insert rows of data into my database

#### To Extract Data from mysql:
- mysql_connector: allows me to connect and pull data from my database
- pandas: to manipulate the data

#### To clean Data:
- re: helps me extract meta-characters and patterns (twitter handles, urls, encoded HTML, etc)
- bs4: decodes HTML to general text
- nltk: tokenizes words

#### To make the analysis I am going to use a few important libraries such as: 
- NLTK(Natural Language Toolkit): has an array of useful functions for natural language processing. 
- TextBlob: to help us calculate sentiment
- Word Cloud Library: to create some summary visualisations of our tweets
- matplot: to make visualizations
- sklearn: to build a matrix of token counts
