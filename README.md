# Research
CMP_SC 4990: Undergraduate Research in Computer Science


# ImpacT

ImpacT helps students develop an understanding of the world, society, and self through authentic data in open datasets while learning IT topics such as programming, databases, web services, and data analytics. Students engage with social sciences topics through authentic, real world, impactful data used in activities, challenges, projects, assessments, and learning materials in information technology topics. The datasets, APIs, and sample code provided by ImpacT are defined to meet the needs of learners at different learning stages from beginner through expert and to address a broad range of social science topics.

Purpose and Objective:

An extensive need exists for datasets for use in teaching IT topics such as programming, databases, web services, and data analytics. The more data, the more diversity of data, and the more the data is designed for target audiences and educational purposes, the easier it is to create activities, challenges, projects, assessments, and learning materials for students based on data.

There is a lot of existing open data, but it is often not in a form that is easily understood and used by learners and teachers. Much of the data found when searching the web can be complex, stored in a form that is difficult to decode, and can take a lot of effort to understand. The goal of most open data projects is to provide the full, unfiltered, complex data so that tools can be applied to derive meaning for all kinds of intents and purposes. ImpacT seeks to match the complexity of the data to meet the needs of target learners from beginner to expert and to provide clear documentation. It also seeks to construct the datasets so they impact the students through the story the data tells.
Web searches can lead to data with intellectual property concerns and data that may be fictitious, misleading, or intentionally incorrect without the teacher or student knowing. Found data may not be real and valid and may not be usable in developing course materials or for students to use in their projects, or eventual apps provided to consumers. The datasets must be open and authentic/valid.

Time is wasted by educators trying to find “good” datasets that meet a need or transforming found datasets into forms that are usable in instruction and for particular intended purposes. Finding “meaningful” datasets takes even more time and effort. ImpacT seeks to deliver meaningful datasets, APIs, sample code, and documentation to make it faster and easier for teachers and students to develop instruction and learn IT topics while engaging with social sciences topics through meaningful data.

Intended Outcomes:
* Develop open, meaningful, real, and valid datasets that can be used to teach IT topics and engage students in developing an understanding of the world, society, and self through social science topics related to the data.
* Develop web services and application programming interfaces (APIs) that allow students to programmatically access the data for use in application development.
* Develop sample code that illustrates how to access, decode, and analyze data.
* Develop a web site portal and web services to host the data, documentation, sample code, and APIs.
*Deliver the above with no intellectual property restrictions other than requiring attribution via the copyright.

Benefits:
* The approach supports multidisciplinary learning. Students learn about social science topics while learning about information technology through the data and meaning it conveys.
* Saves teachers and students an enormous amount of time trying to find unrestricted, meaningful, real, and appropriately structured and documented datasets.
* The data is more interesting to students (and teachers!) than the normally available, fictitious datasets provided with textbooks or commercial learning materials.
* Provides students with richer experiences while studying IT.
* More data means more opportunities for meaningful and multidisciplinary learning to take place.

Examples:
* Want students to understand the impact of seatbelts? Provide them with some data to analyze that shows how death and injuries correlate with not wearing a seatbelt.
* Want students to see how socioeconomic status affects educational achievement, crime, and health, provide them with data that illustrates it.

# Twitter Sentiment Analysis
Sentiment Analysis is the process of predicting whether a piece of text indicates a positive, negative or neutral sentiment on the topic.

# Datasets
[Twitter Sentiment:](https://www.kaggle.com/kazanova/sentiment140) This dataset contains 1,600,000 tweets extracted using the twitter API. 

# APIs
[Tweepy:](https://www.tweepy.org/) An easy-to-use Python library for accessing the Twitter API.

[Twitter:](https://developer.twitter.com/en) Twitters developer website

# Sample Code
Main function to fetch tweets and parse them

    def get_tweets(self, query, count = 10): 
      
        # empty list to store parsed tweets 
        tweets = [] 
  
        try: 
            # call twitter api to fetch tweets 
            fetched_tweets = self.api.search(q = query, count = count) 
  
            # parsing tweets one by one 
            for tweet in fetched_tweets: 
                # empty dictionary to store required params of a tweet 
                parsed_tweet = {} 
  
                # saving text of tweet 
                parsed_tweet['text'] = tweet.text 
                # saving sentiment of tweet 
                parsed_tweet['sentiment'] = self.get_tweet_sentiment(tweet.text) 
  
                # appending parsed tweet to tweets list 
                if tweet.retweet_count > 0: 
                    # if tweet has retweets, ensure that it is appended only once 
                    if parsed_tweet not in tweets: 
                        tweets.append(parsed_tweet) 
                else: 
                    tweets.append(parsed_tweet) 
  
            # return parsed tweets 
            return tweets 
  
        except tweepy.TweepError as e: 
            # print error (if any) 
            print("Error : " + str(e)) 

# Useful Links
[Twitter Sentiment Analysis using Python](https://www.geeksforgeeks.org/twitter-sentiment-analysis-using-python/)

[Twitter Sentiment Analysis using NLTK, Python](https://towardsdatascience.com/twitter-sentiment-analysis-classification-using-nltk-python-fa912578614c)
