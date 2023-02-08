# Use Python to develop a Twitter Data Crawler and perform analysis (April 2022)

__Background:__

>_"We are living on this planet as if we had another one to go to" - Terri Swearingen, Goldman Environmental Prize in 1997_

Greta Thunberg, a teen activist from Stockholm to the global climate leader now, was the youngest individual ever named [TIME magazine’s Person of the Year in 2019.](https://time.com/person-of-the-year-2019-greta-thunberg-choice)

What started was an individual climate change protest by the then 15-year-old in August 2018 to pressure the Swedish government to meet the goals of an international treaty on climate change. She wore a blue hoodie and sat outside the parliament building alone, holding a sign that said “Skolstrejk för klimatet” (School Strike for Climate). Thousands had since joined her and the “Fridays for Future” movement was borned. Now, millions of young people worldwide have joined her movement. 

![image](https://user-images.githubusercontent.com/120662583/217272893-5468e860-1775-4f7e-b52e-2af414760086.png)

# Project Overview

__Problem Statement:__ Those who don’t take the climate crisis seriously are a part of the problem!

__Objective:__ Evaluate the sentiment and attitudes of Greta Thunberg's tweets towards climate change and her impact on youth climate strikes.

# Resources

- __Project Interface__: Juypter Notebook
- __Python Version__: 3.9.6
- __Packages:__ Tweepy, Pandas, NumPy, ReGex, Matplotlib, WordCloud, TextBlob, NLTK, Itertools, Collections, Pillow, SQLAlchemy, Pyscopg
- __Database:__ PostgreSQL
- __Others__: Twitter Developer Platform; Elevated Access, [Greta Thunberg's Twitter account](https://twitter.com/GretaThunberg)

# Database Schema 

The specifications of the data crawler were: 
- To collect the user's profile information.
- To collect the user's social network information.
- To collect tweets from a Twitter user using two keywords

As the database schema, data structure design and data storing were to be done in PostgreSQL, we connected SQLAlchemy to the database via Jupyter notebook. The required data were stored in Pandas DataFrame and subsequently loaded to PostgreSQL.

![image](https://user-images.githubusercontent.com/120662583/217277549-11207ec3-2130-447a-8eca-add671bdd76c.png)

# Pre-processing of the collected tweet for analysis
Raw tweets contain a lot of opinions and are highly unstructured, hence we pre-processed these tweets using: 
- Regular Expressions library as a helper function to clean the tweets  
- Convert the text to lowercase so that it will not affect unique word counts
- Using NLTK stop words to remove all the insignificant words _(excluded 'not' from stop words since the omission will alter the text's context)_
- Tokenise the tweets to interpret the text meaning by analyzing the sequence of the word

The noise reduction in the tweets improves the performance of data analysis and removes unrelated textual content. 

# Analysis from Sentiment Extraction 

### __1. What are the most commonly used words in Greta's Tweets?__

We ran our first analysis on word frequency counts to understand how often words are being used in the user’s tweets. Leveraging on the Collection and Itertools package, we formed a DataFrame of 15 most commonly used words and plotted them in a horizontal bar chart. 

![image](https://user-images.githubusercontent.com/120662583/217288503-1e45437c-7d42-4e4e-a329-a9a5bda2373a.png)


### __2. Sentiment Analysis: Visualising with Word Cloud__

To better visualise the textual data, our second analysis used Word Cloud to get an overview of the words mentioned in the user’s tweets. These words were sized according to their frequency of occurrence and arranged in random order. We also shaped our word cloud by masking it against a .png photograph of our Twitter user.

![image](https://user-images.githubusercontent.com/120662583/217289871-ec903415-9f59-407c-9480-9583fef93c2f.png)


### __3. Sentiment analysis: Measuring opinions using polarity__
Our third and last analysis measured tweets using sentiment scores. Using the integrated sentiment analysis function in TextBlob, it returned the numeric values for polarity and subjectivity of a tweet. These scores for our dataset were stored into a Pandas DataFrame and plotted on a scatter plot. 

![image](https://user-images.githubusercontent.com/120662583/217290760-d8d9b863-55d0-4b98-8d2b-f83c573dd751.png)


### __4. Sentiment Analysis: Interpreting the sentiment score__
We further counted the number of positive, neutral and negative tweets and extracted the percentages. These figures were organised and plotted on a pie chart to give a quick comparison on the user’s sentiments at large. 

![image](https://user-images.githubusercontent.com/120662583/217291216-2dcf04c2-9c49-4eb2-988f-2632145a95bb.png)

# Limitations
- Limited number of tweets returned by Twitter user_timeline endpoint 
- Unable to conduct a cause-and-effect analysis of Greta’s tweets against number of youth strikes
- Limited data to make climate change impact in comparison to sentiments analysis

# Appreciation

A big shoutout to my team mates for the support, motivation and dedication displayed while we strive to do our best to showcase our new learnings from the Business Intelligence and Data Analytics Bootcamp while leveraging on our past work experiences in this 2-week long interim project. 

Thank you team! 

![image](https://user-images.githubusercontent.com/120662583/217453746-9293223b-3efc-4e93-ab91-1f1f0ee21900.png)

