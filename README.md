## What's Up With Kanye West?
Ever since I was in middle school I've been a huge Kanye West fan. I'm talking about pink-polo, white sunglasses and backpack Kanye...the old Kanye. I don't want to get tangled into the political drama that's going on with Kanye and his relationship with Trump; however, I am concerned for Kanye's mental health since he publicly stated he's depressed. It's understandable though, he's got a lot going on his plate from being a husband to Kim K, fathering three beautiful children, running his fashion line, and other "dope shit". It seemed like he was a lot happier back when he was young and choppin' up beats and interuppting Taylor Swift at award shows...or maybe that's just what I want to believe.

### Hypothesis:
I hypothesize that Ye was significantly happier and more positive back in his early career than the current yeezy we all know today.

### Side Note:
Unfortunately Kanye only joined twitter in 2010 which was after a lot of his big albums, so I decided to take tweets from 2010 to 2012 (before he started dating Kim K) and use that for the "old_kanye" data set and use tweets from 2017 to present for the "current_kanye" data set 

### Update (after extracting all of Ye's tweets):
Kanye is Kanye and deletes his tweets all the time so the oldest tweets I can extract are from early April 2018 and one tweet from 2014. So I will just have to run a sentiment analysis on the data I have and won't be able to compare old and new tweets...bummer 

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
To extract Data from Twitter:
- tweepy: twitters API that allows me to grab tweets
- json: allows me to change the extract tweets, which comes in "tweepy.models.ResultSet", then dumps it into a
  json string, then loads it into a list of dictionaries (each dictionary is a tweet containing a Tweet Object)
  
  "The Tweet object has a long list of ‘root-level’ attributes, including fundamental attributes such as 'id',
  'created_at', and 'text'. Tweet objects are also the ‘parent’ object to several child objects. Tweet child
  objects include user, entities, and extended_entities. Tweets that are geo-tagged will have a place child
  object."
  https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object.html
  
#### To Extract Data from twitter:
- tweepy: twitter client authentication and requests to get tweets
- json: to transfer tweet objects to dictionary

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
