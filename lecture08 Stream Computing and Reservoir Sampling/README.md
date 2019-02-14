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

so this means we have a reservoir.

reservoir, a large natural or artificial lake used as a source of water supply.

it's kind like a pool.

So this corresponding to Page 10, when the size of sample is fixed.


## 4. how to do sampling on a stream?

## 5. Page 09

![](https://ws3.sinaimg.cn/large/006tKfTcly1g05r0cx1flj31io0u0guh.jpg)

For example, our dataset are consist of
U singleton and D pairs of duplicate elements.

Totally = U + 2D elements.

The if we sample 1/10 of the whole dataset, it will be

U/10 singleton and
d/100 pairs of duplicate elements,
18d/100 one of duplicate elements.

overall, it's U/10 + 2d/100 + 18d/100 = U/10 + d/5.

= (U+2D)/10

---

## 6. Page 10

![](https://ws2.sinaimg.cn/large/006tKfTcly1g05r5k2548j31sw0pq78v.jpg)

Assume the size of our samples are fixed.

if n < s, if the count of samples are larger than s, size of samples, we just put it in, else, we decide if replace one of the s elements we already have uniformly with p = s/n.

And at any time t, any element in the sequence x1 to xt has exactly s/n chance of being in the sample.

[TODO] Some prove here.

![](https://ws4.sinaimg.cn/large/006tKfTcly1g05syi7qoxj31ay0u07dm.jpg)

## 7. what is weighted reservoir sampling.


Each element, also has a weight.

why we want to assign them some weights? because, we want to sample more for those more important elements.





---


Other useful blogs/articles/papers

https://blog.cloudera.com/blog/2013/04/hadoop-stratified-randosampling-algorithm/
