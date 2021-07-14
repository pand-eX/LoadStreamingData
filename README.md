# How do I load data in real time?

[![NPM](https://img.shields.io/npm/l/react)](https://github.com/pand-eX/LoadStreamingData/blob/main/LICENSE) 

# About the project

I will take as a basis that you saw the Project Data Warehouse in Cloud with Amazon Redshift, here I will explain quickly and directly how to perform a real-time data load (Streaming data) AWS offers some solutions that allow us to perform this type of task.


I'll use Amazon Kinesis Data Firehose it allows to consume, buffer, and process streaming data in real time, providing insights in seconds or minutes instead of hours or days. Remember to check the terms and pricing of any AWS product!



## Why?

why working with Streaming is always challenging to !!!

-This project is part of my personal portfolio, so I'll be happy if you could provide me with any feedback on the project, code, structure or anything you can report that could make me a better data engineer!

Email-me: henricao_7@yahoo.com.br

Connect with me at [LinkedIn](https://www.linkedin.com/in/henrique-castro-484269203//).


## Starting the project

There are 4 services that Amazon Kinesis offers 

-Data Stream

-Data Firehose Stream

-Data Analytics

-Video Stream


I'll use Firehose Stream for this project! Because I'm going to collect the streaming and I'm going to deliver them to Amazon Redshift.


-The service offered to AWS is so amazing that they in addition to allowing you to create streaming it allows you to use test data that they themselves are generating for you

![4](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/4.png)

In this process he speaks creates this table after you use this table to record your streaming and start capturing streaming !!! they provide amazing test data !!!

Here is the configuration of my Kinesis but this various according to your needs I will leave only as an example !!!

![5](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/5.png)


## Loading data streaming into the Redshift Cluster

![1](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/1.png)


- Take the data from the source and go to the streaming delivery will do some transformation process if I have configured if not it goes on (this will be the future, with the increase of data that is having in the world the process and transformation will be in real time does the analysis stores and proceeds to next) writes this in the s3 bucket uses the copy command and writes to the redshift cluster /\ basically was what I did in the batch but had not the streaming AWS basically automated the process for me now I can collect the data direct from the source and put this, store direct in your DW and you can still create the s3 Bucket backup because as the data is generated in Real time the volume is very large you usually discard this data after doing some kind of operation but in case you wanted to save you can use s3 that storage cost is much lower 


- This data is collected from the WEB through a JSON file it is processed by firehose written in s3 and then copied to Amazon Redshift and loaded into the table all in real time
 

![2](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/2.png)



![3](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/3.png)


- See that it generates some graphics with input bytes has little thing because I captured it for a short time. 


- This was an example of how we can capture data in real time and store directly in Redshift this can be given from sensors data from the internet of things IOT data generated from data web data through website clicks of selling website and the kinesis does it all for you.
