# Unresolved problems

## 1. how to calculate the number of filter to guarantee a FP?

# 0. Preview

The topics are Compressed Cache and Bloom Filters.

1. what is compressed cache?
2. what is bloom filters(布隆过滤器)?

A Bloom filter is a simple space-efficient randomized data structure for representing a set in order to support membership queries.<br>
A Bloom filter is a data structure designed to tell you, rapidly and memory-efficiently, whether an element is present in a set.<br>
Bloom filter 是一个数据结构，它可以用来判断某个元素是否在集合内，具有运行快速，内存占用小的特点。

It tells us that the element either `definitely is not in the set or may be in` the set.<br>
a query returns either "possibly in set" or "definitely not in set".

An empty Bloom filter is a bit array of m bits, all set to 0.

<img src="https://ws1.sinaimg.cn/large/006tNc79ly1fzfxswrsxcj30ko0303yn.jpg" width="250px"/>

Elements can be added to the set, but not removed.

To add an element, feed it to each of the k hash functions to get k array positions. Set the bits at all these positions to 1.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Bloom_filter.svg/2880px-Bloom_filter.svg.png" width="550px"/>

If the number in that position is already 1, it will still be 1.


### how to determine k. the trade-off.
The more hash functions you have, the slower your bloom filter, and the quicker it fills up. If you have too few, however, you may suffer too many false positives.

---


## Google chrome example

Given a lot of malicious URL that Chrome need to filter for the user, if we store all these malicious in the memory, it will cost a lot of memory.

## use a hash func to map each url to a bit vector

We can guarantee, if it's a malicious URL, we can stop it 100%. But if it's a good URL and the algorithm think it's malicious, we call this false positive. false means the judgement is wrong, positive means the prediction is positive, i.e., it's a malicious URL.

So for a single Hash function, the probability for FP(False Positive) is less than 1 - (1-1/R)^N. where, R is the number of slots, and N is the number of objects in this bit vector.

<img src="https://ws4.sinaimg.cn/large/006tNc79ly1fzgd2ocdjkj307w02uaa0.jpg" width="250px"/>

for this example, R = 6 and N = 2.

![](https://ws2.sinaimg.cn/large/006tNc79ly1fzgd5eqnpgj30aa06w74e.jpg)

so for R = 100, when we insert object from 0 to 100, the probability of false positive increased from 0 to 0.6. It's very high for the algorithm to misjudge.

## multiple hash function

if we use k different independent hash function.

The p of false positive will be decreased to


---

One problem of bloom filter, is that we cannot delete items.

Option1:
keep two bloom filters, one is for delete.

Option2:
use a count bloom filter.

How to combine two bloom filters. Just use a OR is their sizes are same. or just append the second one to the end of the first one. If we just `OR` them, more objects will be put into the same size bit-vector, so the p of false positive will be higher.

The advantage of this, is that we can do it in different machines and combine their result.

### Shrink bloom filter.

just `OR` the first half with the second half.

### Some questions to think about.

How to use bloom filter to find shared friends on Facebook?







## Reference

1. an online demo to explain bloom filter.
https://llimllib.github.io/bloomfilter-tutorial/

http://citeseer.ist.psu.edu/viewdoc/download;jsessionid=6CA79DD1A90B3EFD3D62ACE5523B99E7?doi=10.1.1.127.9672&rep=rep1&type=pdf





---
