## what is pseudoranom number generator

seed based. deterministic and will give the same sequence if the seed is same.

## what is hash function?

input is an object, or instance, output an index between 0 and N

h(O) <img src="http://www.i2symbol.com/images/symbols/math/element_of_u2208_icon_256x256.png" width="10px"/> [0 - N]

## what is a perfect hash?

if o1 != o2, then h(o1) != h(o2)
O(1) search


## what is universal hashing?

![](https://ws4.sinaimg.cn/large/006tNc79ly1fzokwt6mr6j31n00ii0wz.jpg)

![](https://ws1.sinaimg.cn/large/006tNc79ly1fzaffepq6qj316e07ymyv.jpg)


In mathematics and computing universal hashing (in a randomized algorithm or data structure) refers to selecting a hash function at random from a family of hash functions with a certain mathematical property. This guarantees a low number of collisions in expectation, even if the data is chosen by an adversary. Many universal families are known (for hashing integers, vectors, strings), and their evaluation is often very efficient. Universal hashing has numerous uses in computer science, for example in implementations of hash tables, randomized algorithms, and cryptography.

<img src="https://ws4.sinaimg.cn/large/006tNc79ly1fzakd1jn6ej30sg03mjrp.jpg" width="250px"/>

## what is hash family H?

<img src="https://ws4.sinaimg.cn/large/006tNc79ly1fzah95r75jj30u408adgz.jpg" width="250px"/>

### how to deal with collision ?

chaining

open addressing

### what is the expected value of searching time with N array size and m objects inserted?

1 + (m-1)/N

---

linear probing, quadratic probing, double hashing.
