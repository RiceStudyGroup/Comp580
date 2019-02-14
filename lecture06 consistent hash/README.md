


## 1. what is consistent hashing?

Traditionally, if we want to change the number of slots, we need to remap all keys. So this is the problem we want to solve here.
here, if we cache the content on several servers, and when we change the number of server, add or remove some of them, we need to remap all the cache unless we use something like consistent hashing.

use consistent hashing, we only need K/n items to be re-shuffled when the number of slots/nodes change.
K is the number of keys, and n is the number slots.

The physical meaning if K/n is that assume you assign these keys averagely on these servers, you just need to move keys on one machine.

>usually, we will cache the website to disk so that it can respond faster and also, is beneficial to the internet.
less web traffic, congestion, and dropped packet.

`CDN`
content delivery network, 内容分发网络（英语：Content delivery network或Content distribution network，缩写：CDN）是指一种透过互联网互相连接的计算机网络系统，利用最靠近每位用户的服务器，更快、更可靠地将音乐、图片、影片、应用程序及其他文件发送给用户，来提供高性能、可扩展性及低成本的网络内容传递给用户。


http://theory.stanford.edu/~tim/s17/l/l1.pdf



## 2. what is dropped packet?

## 3.

>what if the cache can be shared by many users, for example, all the users on Rice Network.
