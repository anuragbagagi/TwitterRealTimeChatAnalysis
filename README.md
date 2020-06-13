# Analyze Real time tweets

Extract a particular topic on the Twitter API and find out the respective sentiments associated related to the tweet topic. <br /> Store the data using elastic search indexing and visualize the sentiment on dashbaord using kibana


## Solution and Data Flow diagram

A python script is used to make API calls to Twitter using the Tweepy library and the tweets are streamed to a TCP port. <br />A selected topic is used to search time tweet. The python script is running on a windows environment. An another Spark-Streaming application reads the tweets from the port already defined, transform the data and save results in elastic search index. 

![Communication_Flow_Diagram](https://github.com/anuragbagagi/TwitterRealTimeChatAnalysis/blob/master/Communication%20Flow%20Diagram.jpg)

### Prerequisites
1. twitter app<br />
2. Anaconda <br />
3. Apache-Spark<br />
4. Elastic search<br />
5. kibana<br />

### Installing

Use the below link to install the requires tools<br />
link to follow for setting up a Twitter App:- https://iag.me/socialmedia/how-to-create-a-twitter-app-in-8-easy-steps/<br />
link to setup anaconda on windows: https://docs.anaconda.com/anaconda/install/windows/<br />
link to setup spark on windows(PySpark): https://medium.com/@GalarnykMichael/install-spark-on-windows-pyspark-4498a5d8d66c<br />
link to setup elastic search: https://www.elastic.co/guide/en/elasticsearch/reference/current/zip-windows.html<br />
link to setup kibana: https://www.elastic.co/guide/en/kibana/current/windows.html<br />
Instead of TCP port if someone wants to use kafka then use below link to setup kafka:https://dzone.com/articles/running-apache-kafka-on-windows-os

## Running the tests
Before running the script delete the existing elastic search data using below command:<br />
curl -XDELETE http://localhost:9200/index name

Add the required consumer_key, consumer_secret,access_token and access_secret to config file after registering and creating twitter app.

The tweet Python script and the Spark-streaming file, is executed in sequence and we will be able to see tweets being collected and dashboard is updated every 10 seconds.


## Acknowledgments

* https://www.eecs.yorku.ca/~papaggel/courses/eecs4415/docs/assignments/a3/a3.pdf<br />
* https://stackoverflow.com/questions/46762678/how-to-push-a-spark-dataframe-to-elastic-search-pyspark<br />
* https://www.toptal.com/spark/introduction-to-apache-spark<br />


