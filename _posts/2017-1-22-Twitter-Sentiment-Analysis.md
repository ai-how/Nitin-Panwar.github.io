---
layout: post
title: Twitter Sentiment Analysis
published: true
---

Learning new things are always exciting. Today i will be sharing about Twitter sentiment analysis but first we need to get old data. Using Twitter API it is not possible to get older tweets. To get older data i am using the [I'm using Jefferson utility](https://github.com/Jefferson-Henrique/GetOldTweets-python). Clone this repository in your local machine and run below command to get 6000 tweets from 1-12-2015 to 2-12-2015 of #ChannaiFloods.

```
python Exporter.py --querysearch "ChennaiFloods" --since 2015-12-1 --until 2015-12-2 --maxtweets 6000
```

Top 10 users

```
import pandas as pd
import nltk 
tweet_df =pd.read_csv("output_got.csv")
users = tweet_df["username"].tolist()
fdist2 = nltk.FreqDist(users)
fdist2.plot(10)
```

![Imgur](http://i.imgur.com/8a0uHsk.png)

### Text Pre-processing
All tweets are processed to remove unnecessary things like links, non-English words, stopwords, punctuation’s, etc. First you need to download stopword corpus in your computer.Start NLTK Downloader and download all the data you need.

```
import nltk
nltk.download()
```
