current state [23/25]

Stream Estimation 1: Count-Min Sketch (Generalized Bloom Filters).


## 1. what is stream estimation?



## 2. what is count min sketch?

### 2.1 what is sktech?

![](https://ws1.sinaimg.cn/large/006tKfTcly1g06xrvowvgj31tc054goc.jpg)

from https://courses.cs.washington.edu/courses/cse522/14sp/lectures/lect04.pdf

## 3. what is generalized bloom filters?

## 4. what is heavy Hitters Problem?

heavy means frequent here.

![](https://ws2.sinaimg.cn/large/006tKfTcly1g05vqp9ss8j31m40c2jue.jpg)

`for example, we want know what are the top-50 phrases say upto four words in the last year? ``

![](https://ws4.sinaimg.cn/large/006tKfTcly1g05vupbgwqj31so07owhv.jpg)



https://www.coursera.org/lecture/advanced-algorithms-and-complexity/heavy-hitters-problem-wCILS

https://www.cs.utah.edu/~jeffp/teaching/cs5955/L12-Heavy-Hitters.pdf

https://www2.cs.duke.edu/courses/fall18/compsci531/LabLectures/lab5.pdf

Then we start to talk about power law

## 5. What is power law?

Maybe we can make use of Power Law: Real word data follows power law. Some things are repeated all the time, most things occur rarely.


![](https://ws4.sinaimg.cn/large/006tKfTcly1g05wj7msflj30xq0ii74y.jpg)

## what if we use a hash map to count them?

![](https://ws2.sinaimg.cn/large/006tKfTcly1g06pb15p3bj322809wgmu.jpg)


For the situation above, s is heave and r is small, it will be a good estimation for s, because large + small ![](https://ws1.sinaimg.cn/large/006tKfTcly1g06pd06oabj300u00u3yd.jpg) large.

![](https://ws3.sinaimg.cn/large/006tKfTcly1g06pdhf8x7j322g08swfk.jpg)

This one is also okay, because both s and r are not heavy, then we don't care about their count.

![](https://ws1.sinaimg.cn/large/006tKfTcly1g06pe2tbr8j322a08emy8.jpg)

We need to pay attention to this one, because both s and r are heavy and we want to know their count, but the HashMap store their sum, i.e. count[s or r], rather than count[s] and count[r].

So this is what we try to avoid.

![](https://ws3.sinaimg.cn/large/006tKfTcly1g06phrmyyrj31re0peqam.jpg)

Here R is the capacity of such a hashmap.

So the expectation error, i.e.
abs(real count of s minus hashmap[s]) < Sum of count / size of hashmap.


<font color=red>don't get the last sentence, </font>`in power law, if s is head then c_s = f\Sigma some fraction of everything`

Count of head = ??

## 6.  Page 18

Firstly review the Markov Inequality.

![](https://ws2.sinaimg.cn/large/006tKfTcly1g06ub7quasj30qk04gmxk.jpg)

For just on hash function, the expected error is

Sum of count / (size of hashmap, which is R)

Then Pr[error > 2 * expected error] < 1/2

If we use d hash function, Pr[error > 2 * expected error] < (1/2 ** d)

---

## 7. Page 19.

When to increase d (number of hash functions)? When to increase R (or the range)?

## 8. Page 20.

![](https://ws1.sinaimg.cn/large/006tKfTcly1g06vabt6k5j31p00e4780.jpg)

still not sure what is f here.

![](https://ws4.sinaimg.cn/large/006tKfTcly1g06wwlnglwj31ua0s2jyc.jpg)

what is the physical meaning of ![](https://ws2.sinaimg.cn/large/006tKfTcly1g06wx5ualdj300u00y745.jpg) here?

what about ![](https://ws1.sinaimg.cn/large/006tKfTcly1g06wxgzayfj300q0120sl.jpg)?

![](https://ws2.sinaimg.cn/large/006tKfTcly1g06wy8r9acj30c003emx8.jpg)

what is union bound trick here?
what does failure mean here?
fall outside of c_s and c_s + 2 ![](https://ws1.sinaimg.cn/large/006tKfTcly1g06wxgzayfj300q0120sl.jpg)![](https://ws1.sinaimg.cn/large/006tKfTcly1g06wzvj6cuj300u01c745.jpg) ?

What is N here? The number of all elements?
So to guarantee for all the elements, the failure probability is less than ![](https://ws2.sinaimg.cn/large/006tKfTcly1g06wx5ualdj300u00y745.jpg), we need such size of memory?

is this what the current page want to say?

---

## 9. How to identify top-k?

just need to maintain an extra heap, when update the count of an element, remove it from heap and add it.

this is easy.

space k
time

![](https://ws1.sinaimg.cn/large/006tKfTcly1g06x6e58qwj31bw04yabj.jpg)

## 10. what is turnstile model?

<img src="https://static.grainger.com/rp/s/is/image/Grainger/2XHW9_AS01?$mdmain$" width="250px"/><img src="http://virtualworldcommunications.com/wp-content/uploads/2018/03/tripod-turnstile.jpg" width="250px"/>

This is turnstile.

assume a vector v, who has N elements.

V = [v_1, v_2 ... v_N]

but we cannot afford O(N) space.

![](https://ws1.sinaimg.cn/large/006tKfTcly1g06xm7p2vhj31jw0u0jzy.jpg)

<font color=green>don't understand what this is about</font>












---
