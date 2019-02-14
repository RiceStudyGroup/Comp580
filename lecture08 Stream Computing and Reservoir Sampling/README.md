Stream Computing and Reservoir Sampling

## 1. what is stream computing?

data stream is some day we don't know in advance, can be consider as infinite.
For example, google queries, twitter feeds.

What is twitter feeds?


it's like a stream, new data will be put into this stream and you cannot store the entire stream accessibly.

while we want to use a limited memory to do some calculation, for example:

- Google wants to know what queries are more frequent today than yesterday
- Yahoo wants to know which of its pages are getting an unusual number of hits in the past hour
- look for trending topics on Twitter, Facebook

![](https://ws1.sinaimg.cn/large/006tNc79ly1g03eg43s40j31qk0lkgrh.jpg)



## 2. what is sampling?

Assume we have a stream dataset, ![](https://ws3.sinaimg.cn/large/006tNc79ly1g03hm9yh8rj30hi02mjrk.jpg)

but we don't know the size of this stream, i.e., n.

so we cannot say, pick 1 of 10, cause it might exceed the size of our memory.


![](https://ws1.sinaimg.cn/large/006tNc79ly1g03k9j2c2aj30nm03074n.jpg)

what is sampling bias?

## 3. what is reservoir sampling?

## 4. how to do sampling on a stream?





---
