# 1. Collision

## 1. what is k-universal hashing family H?

![](https://ws3.sinaimg.cn/large/006tNc79ly1fzf7xq6dz8j31nq09w40q.jpg)

the question here is that, we just pick one hash function from a hash family, right?

For example, we want to insert key=a into a map, and h1(a) = 6, and h2(a) = 8, so when we want to retrieve a, and used h1 to put it, and when we want to access its value, how do we know it's h1(a) rather than h2(a)?

`#TODO` Again, not very clear about the physical meaning and the benefit of k-universal hashing family.

To avoid collision? To decrease the possibility of collision?

This problem is not very important. Cause finally we used linear probing.

![](https://ws4.sinaimg.cn/large/006tNc79ly1fzf855wexxj31rw0bqdij.jpg)

In this example, what is a0, a2 .. ak-1? In the course, professor changed k to be k-1, it's here, right?

What is P and R, why not just one? <br>
`mod P mod R == mod P*R` true or false?

False, the first one, the max value is limited by the min(P,R) while the later one, the max value could be P*R. 



---


## 2. how do you get this expected length of chain?


![](https://ws3.sinaimg.cn/large/006tNc79ly1fzf87e4ysfj318e0e4ac4.jpg)

So now, we want to insert m objects into an array of size n.

I think the expected length of a certain slot is
length = 1, p = <img src="https://ws1.sinaimg.cn/large/006tNc79ly1fzf8bqmv1rg304m01b0na.gif" width="200px"/>

BTW, (n 1) means pick 1 from n, it's a little not intuitive.


`#TODO`<br>
How to explain this 1 + (m-1)/n ?<br>
what is the physical meaning of $\alpha$?

![](https://ws1.sinaimg.cn/large/006tNc79ly1fzf8fvq0iij30dd096mx7.jpg)

So I plot this, n = 100, and we increase the m from 0 to 100, as we insert the new objects into this array, the expectation of the chain increased linearly.

---


![](https://ws4.sinaimg.cn/large/006tNc79ly1fzf8ijywrbj31t00cqac6.jpg)

In this slide, professor want to propose a better way to decrease the expected length of chain. I guess, here n means the number of inserted objects. Cause if n is the length of the array, it's constant, and it not reasonable to say, no matter how many objects you insert into this map, the expected length of the chain are same.


---

![](https://ws2.sinaimg.cn/large/006tNc79ly1fzf8oe3lblj31pu04mt9s.jpg)

when the number of objects in the map is same with the size of map.

very probably, the longest length is O(ln n/ ln ln n).


Okay, these two blocks, actually are talking about these things. 1. Assume the hash function is very random, the expected length of the chain are increasing linearly by the number of objects your inserted into the map. And the 2. with high probability, the length of longest list is O(ln n/ ln ln n).

The reason why we assume `m = n`, I guess is because, for those sparse map, the length of longest list should be shorter than O(ln n/ ln ln n), so it's the upper bound for both full map and sparse map.

---


![](https://ws1.sinaimg.cn/large/006tNc79ly1fzf97ouadaj31lm0meae9.jpg)


<img src="https://ws1.sinaimg.cn/large/006tNc79ly1fzf97ujydlj30u60lidif.jpg" width="450px"/>


---

This is a part of assignment .

![](https://ws1.sinaimg.cn/large/006tNc79ly1fzf98tdiwej31ra0cego0.jpg)

Prove that, if we use two hash function, we can decrease the longest list to be O(log log n).

`How? #TODO`

---

# 2. Linear Probing


![](https://ws2.sinaimg.cn/large/006tNc79ly1fzf9ajmk2bj31tq05q75t.jpg)

i don't understand what does 2-independence mean here?

what if we insert 1, and 3, their hash res are same. <br>
h(1) -> 0<br>
h(3) -> 0<br>
[1, 3]<br>
then we remove 1, and search 3, what will happen if we find 0 is empty, do we need to search its adjacent slots? `#TODO`



# 3. Cuckoo hashing





---
